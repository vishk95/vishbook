---
title: "Asynchronous Apex"
---

# Queueable Apex

To start a long-running operation and get an ID for it.

To pass complex types to a job.

To chain jobs.

- Advanced and enhanced version of future methods.
- A class structure that the platform serializes for you, a simplified interface without start and finish methods and even allows you to utilize more than just primitive arguments.
- called by a simple System.enqueueJob() method, which returns a job ID that you can monitor.
- System.enqueueJob(queueable, asyncOptions) method where you can specify the maximum stack depth and the minimum queue delay in the asyncOptions parameter.
        AsyncOptions asyncOptions = new AsyncOptions();
        asyncOptions.MaximumQueueableStackDepth = depth;
        System.enqueueJob(new FibonacciDepthQueueable(null, null), asyncOptions);
- Apex allows HTTP and web service callouts from queueable jobs, if they implement the Database.AllowsCallouts marker interface. In queueable jobs that implement this interface, callouts are also allowed in chained queueable jobs.

Advantages:

- Getting an ID for your job.
- Using non-primitive types, sObjects or custom Apex types.
- Chaining jobs.

Syntax:

```java
public class SomeClassName implements Queueable {
    public void execute(QueueableContext context) {
        // awesome code here
    }
}
```

Execute:

- ID jobID = System.enqueueJob(new SomeClassName());\
- Using the System.enqueueJob(queueable, delay) method ignores any org-wide enqueue delay setting.

Queueable Apex limits:

- The execution of a queued job counts once against the shared limit for asynchronous Apex method executions.
- You can add up to 50 jobs to the queue with System.enqueueJob in a single transaction. When chaining jobs, you can add only one job from an executing job with System.enqueueJob, which means that only one child job can exist for each parent queueable job. Starting multiple child jobs from the same queueable job is a no-no.
- No limit is enforced on the depth of chained jobs, which means that you can chain one job to another job and repeat this process with each new child job to link it to a new child job. However, for Developer Edition and Trial orgs, the maximum stack depth for chained jobs is 5, which means that you can chain jobs four times and the maximum number of jobs in the chain is 5, including the initial parent queueable job.

**Queueable Apex** **Questions**

1. What happens to queueable jobs if Apex transaction rolls back?
1. How to track queueable jobs, Where?
1. Which data types can be passed?
1. How many queueable can be added in single transaction

# Scheduled Apex / Apex Scheduler

To schedule an Apex class to run on a specific schedule.

- Implement the Schedulable interface for the class, then specify the schedule using either the Schedule Apex page in the Salesforce user interface, or the System.schedule method.
- The scheduler runs as system—all classes are executed, whether the user has permission to execute the class or not.
- One execute method that must be implemented. Must be declared as global or public.
- You can also use the Schedulable interface with batch Apex classes.
- An easier way to schedule a batch job is to call the System.scheduleBatch method without having to implement the Schedulable interface.
- To stop execution of a job that was scheduled, use the System.abortJob method with the ID returned by the getTriggerID method.
- All asynchronous calls made after the startTest method are collected by the system. When stopTest is executed, all asynchronous processes are run synchronously.
- System.scheduleBatch method to schedule a batch job to run one time at a specified time in the future. This method is available only for batch classes and doesn’t require the implementation of the Schedulable interface.

Limits:

- 100 scheduled Apex jobs at one time.
- The maximum number of scheduled Apex executions per a 24-hour period is 250,000 or the number of user licenses in your organization multiplied by 200, whichever is greater.

# Batch Apex

For long-running jobs with large data volumes that need to be performed in batches, such as database maintenance jobs.

For jobs that need larger query results than regular transactions allow.

- write an Apex class that implements the Salesforce-provided interface Database.Batchable and then invoke the class programmatically.
- 3  methods that must be implemented.
- public (Database.QueryLocator | Iterable<sObject>) start(Database.BatchableContext bc) {}
- If you use a QueryLocator object, the governor limit for the total number of records retrieved by SOQL queries is bypassed.
- public void execute(Database.BatchableContext BC, list<P>){}
- public void finish(Database.BatchableContext BC){}
- Use the Database.executeBatch method to programmatically begin a batch job. Take 2 para
- 1. An instance of a class that implements the Database.Batchable interface.
- 2. An optional parameter scope. This parameter specifies the number of records to pass into the execute method.
- If the start method of the batch class returns a QueryLocator, the optional scope parameter of Database.executeBatch can have a maximum value of 2,000. If set to a higher value, Salesforce chunks the records returned by the QueryLocator into smaller batches of up to 2,000 records.
- If the start method of the batch class returns an iterable, the scope parameter value has no upper limit. However, if you use a high number, you can run into other limits.
- System.scheduleBatch method to schedule a batch job to run once at a future time.
- String cronID = System.scheduleBatch(batchclassinstance, 'job example', 60);
- To use a callout in Batch Apex, Database.AllowsCallouts have to be specified in the class definition.
- Database.Stateful, only instance member variables retain their values between transactions.
- Static member variables don’t retain their values and are reset between transactions.

## Best Practices in Batch Apex

- Stateful should be used with the class definition if instance member variables or data across job transactions need to be shared. Otherwise, at the start of each transaction, all member variables are reset to their initial state.
- Methods that are declared as future aren’t allowed in classes that use the Database.Batchable interface.
- All Database.Batchable interface methods that are used must be defined as global or public.

## Limits in Batch Apex

1. Up to five queued or active batch jobs are allowed for Apex.
1. Cursor limits for different Force.com features are tracked separately. For example, you can have 50 Apex query cursors, 50 batch cursors, and 50 Visualforce cursors open at the same time.
1. A maximum of 50 million records can be returned in the Database.QueryLocator object. If more than 50 million records are returned, the batch job is immediately terminated and marked as Failed.
1. If the start method returns a QueryLocator, the optional scope parameter of Database.executeBatch can have a maximum value of 2,000. If set to a higher value, Salesforce chunks the records returned by the QueryLocator into smaller batches of up to 2,000 records. If the start method returns an iterable, the scope parameter value has no upper limit; however, if you use a very high number, you may run into other limits.
1. If no size is specified with the optional scope parameter of Database.executeBatch, Salesforce chunks the records returned by the start method into batches of 200, and then passes each batch to the execute method.Apex governor limits are reset for each execution of execute.
1. The start, execute, and finish methods can implement up to 10 callouts each
1. The maximum number of batch executions is 250,000 per 24 hours.
1. Only one batch Apex job’s start method can run at a time in an organization. Batch jobs that haven’t started yet remain in the queue until they’re started. Note that this limit doesn’t cause any batch job to fail and execute methods of batch Apex jobs still run in parallel if more than one job is running

**Questions** **Batch Apex**

1. Can we call batch from future
1. Can call future from batch
1. can we call batch from batch

# Future Methods

When you have a long-running method and need to prevent delaying an Apex transaction.

When you make callouts to external Web services.

To segregate DML operations and bypass the mixed save DML error.

- A benefit of using future methods is that some governor limits are higher, such as SOQL query limits and heap size limits.
- future methods must be static methods, and can only return a void type
- parameters must be primitive data types, arrays of primitive data types, or collections of primitive data types.
- The reason why sObjects can’t be passed as arguments to future methods is because the sObject can change between the time you call the method and the time it executes.
- extra parameter (callout=true) to indicate that callouts are allowed.

```java
global class FutureClass
{
    @future
    public static void myFutureMethod()
    {
         // Perform some operations
    }
}
```
