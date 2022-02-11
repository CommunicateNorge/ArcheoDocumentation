# Users

- [Users](#users)
  - [About users](#about-users)
  - [User administration](#user-administration)
  - [User role](#user-role)
  - [User Groups](#user-groups)

## About users

All subscriptions need at least one user the owner. Users are personally and based on an email address as the username. A user may have different roles and rights per subscription and may be member of many subscription.

## User administration

All users are listed, with the possibility to filter this list. Each user has a Role, that sets its user rights
![img](https://archeodocstorage.blob.core.windows.net/images/Users-User-Administration.png)

The menu far right makes it possible to delete a user from the subscription. Note that the user is not delete from Arche as hole, but only from this subscription.

![img](https://archeodocstorage.blob.core.windows.net/images/Users-User-Delete.png)

## User role

Archeo supports four predefined roles:

| Role          | Description |
| -----------       | ----------- |
| Owner         | The owner of the subscription. A subscription may have more than one owner, and an owner has by default the rights of the Administrator and AllMessageRights|
| Administrator       |An Administrator has by default the rights from AllMessageRights. The administrator has the rights to open the administrator UI and can administrate the service|
| AllMessageRights | This role gives the members the right to see all transactions and messages for the subscription|
| User            | This role has by default no rights and the user groups this user is a member of defines its rights  |

## User Groups

Select one or multiple user groups for this user. Go to [user groups](user%20Group.md) to se how to create and assign rights per group.
