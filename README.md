#### ReadMe.md

The local_crud_module provides simple database-like access to local 
storage for modern browsers using angular.

#### Description


This simple CRUD service is used for browsers that support the JavaScript
localStorage object. No attempt is made to support browsers that do not
provide this built-in functionality. The code can be modified as needed,
no attribution necessary. There are plenty of places for hooks, such as 
broadcast events, where UI and other commands may be included. The _canStore
property and the initStore() and _testLocalStorage() functions determine
if the CRUD functions are available. The create and update methods can be
modified to ensure that it is possible to create a localStorage entry before
it is written. In other words, update is operationally like create here, but
the business logic provides alternative application paths if needed.

manageLocalCRUD(whatAction, whatObj) is used to access localStorage:

whatAction can be "create", "retrieve", "update" or "delete"
whatObj can be a String or JavaScript object, depending on whatAction value

For Create and Update, whatObj is an object with a key and value property.
The key is a string, and the value is any valid JavaScript Object type

create:
	manageLocalCRUD('create', {
		key:"StringName", value:"String Value"})
	OR
	manageLocalCRUD('create', {
		key:"ObjectName", value:{"Property":"Value"}})
update:
	manageLocalCRUD('update', {
		key:"StringName", value:"String Value"})
	OR
	manageLocalCRUD('update', {
		key:"ObjectName", value:{"Property":"Value"}})

For retrieve and delete, the whatObj value is a string which refers to the 
String and Object key names from the create and update methods.

retrieve:
	manageLocalCRUD('retrieve', 'StringKeyName')
delete:
	manageLocalCRUD('delete', 'StringKeyName')



This page was last updated October 12, 2014.

