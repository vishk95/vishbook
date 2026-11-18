---
title: "Relationships in Salesforce"
---

# Types of Relationships in Salesforce

## Lookup Relationships

- like master-detail relationships, except they don’t support sharing or roll-up summary fields.

When you create a lookup relationship, you can set these options:

- Make the lookup field required for saving a record, requiring it on the corresponding page layout as well.
- What to do if the lookup record is deleted?
1. Clear the value of this field
1. Don’t allow deletion of the lookup record that’s part of a lookup relationship
1. Delete this record also (only for custom object) - 
A cascade-delete bypasses security and sharing settings, which means users can delete records when the target lookup record is deleted even if they don’t have access to the records.
- If the parent record in a lookup relationship is deleted, the field history tracking for the child record doesn't record the deletion.
- You can't delete an object or record in a lookup relationship if the combined number of records between the two linked objects is more than 100,000.

## Master-Detail Relationship

- Closely links objects together.
- Roll-up summary field is available.
- Behaviors of master-detail relationships:
    - Deleting a master record also deletes related detail and subdetail records.
    - By default, records can’t be reparented, Administrators can select the Allow reparenting option in the master-detail relationship definition.
    - Owner field on the detail and subdetail records isn’t available and is automatically set to the owner of the master record. Custom objects on the detail side of a master-detail relationship can't have sharing rules, manual sharing, or queues, as these require the Owner field.
    - Detail and subdetail records inherit security settings and permissions from the master record. You can’t set permissions on the detail record independently.
- Each custom object can have up to 2 master-detail relationships and up to 40 total relationships.
- You cannot create a new Master-Detail relationship on an existing custom object if records already exist. You must first create a Lookup relationship, populate the lookup field with data in all records, and then change the relationship type to Master-Detail.

## Consideration Lookup to Master Detail

- but only if the lookup field in all records contains a value.
- All child records must have the parent lookup value as it is mandatory to have in MDR.
- Child record will inherit the Record Owner of the Master record.
- Reports are unusable.

## Consideration Master Detail to lookup

- No roll up summary on master-detail
- custom object on the “detail” side, changes the organization-wide default for the object to public read/write.

## Many-to-Many Relationships

You can use master-detail relationships to model many-to-many relationships between any two objects.

A custom object with two master-detail relationships is a custom junction object.

How to create many-to-many relationships:

- Create the junction object.
- Create the two master-detail relationships.
- Customize the related lists on the page layouts of the two master objects.
- Don’t launch the custom tab wizard. Junction objects don’t need a tab.

Junction object records are deleted when either associated master record is deleted and placed in the Recycle Bin. If both associated master records are deleted, the junction object record is deleted permanently and can't be restored.

Sharing access to a junction object record is determined by a user's sharing access to both associated master records and the Sharing Setting option on the relationship field. For example, if the sharing setting on both parents is Read/Write, then the user must have Read/Write access to both parents in order to have Read/Write access to the junction object. If the sharing setting on both masters is Read-Only, a user with Read-Only rights on the master records would have Read access to the junction object.

The junction object records inherit the value of the Owner field from their associated primary master record. Because objects on the detail side of a relationship don’t have a visible Owner field, this is only relevant if you later delete both master-detail relationships on your junction object.

In a many-to-many relationship, a user can't delete a parent record if there are more than 200 junction object records associated with it and if the junction object has a roll-up summary field that rolls up to the other parent. To delete this object, manually delete junction object records until the count is fewer than 200.

You can't create a many-to-many self-relationship, that is, the two master-detail relationships on the junction object can't have the same master object.

## Self-Relationship

## External Relationships

## Hierarchical Relationships
