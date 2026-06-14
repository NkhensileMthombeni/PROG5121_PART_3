The purpose of the application is to demonstrate the use of fundamental programming concepts learned throughout the module, including:

Variables and Data Types
Classes and Objects
Methods
Decision Structures
Loops
Arrays and ArrayLists
String Manipulation
File Handling
JSON Storage
Unit Testing with JUnit
Version Control using GitHub

The application allows users to:

Register an account
Log into the system
Send messages
Store messages
Disregard messages
Generate message hashes and IDs
Search stored messages
Delete messages
Generate reports
Save messages to JSON files
Features Implemented
Part 1 – Registration and Login
User Registration

The user is required to enter:

First Name
Last Name
Username
Password
South African Cell Phone Number
Username Validation

The username must:

Contain an underscore (_)
Be no more than 5 characters long

Example:

kyl_1
Password Validation

The password must:

Be at least 8 characters long
Contain at least one uppercase letter
Contain at least one number
Contain at least one special character

Example:

Password@1
Cell Phone Validation

The cellphone number must:

Contain the South African international code (+27)
Be correctly formatted

Example:

+27838968976
Login

Users can log in using the credentials created during registration.

Successful login message:

Welcome John Smith it is great to see you again.
Part 2 – Sending Messages

After successful login, the user is welcomed to ChatApp.

Welcome to ChatApp.

The user is presented with a menu:

1. Send Messages
2. Show Recently Sent Messages
3. Quit
4. Stored Messages
Message Information

Each message contains:

Item	Description
Message ID	Auto-generated 10-digit number
Recipient	South African phone number
Message	Message text
Message Hash	Auto-generated hash
Message Count	Auto-incremented number
Message Length Validation

Messages may not exceed:

250 characters

Success:

Message ready to send.

Failure:

Message exceeds 250 characters.
Message Hash

The application automatically creates a hash using:

First 2 digits of Message ID
:
Message Number
:
First Word
Last Word

Example:

00:0:HITONIGHT
Message Actions

Users can:

Send Message
Disregard Message
Store Message

Outputs:

Message successfully sent.
Press 0 to delete the message.
Message successfully stored.
Part 3 – Stored Messages

The application stores messages in separate collections.

Sent Messages

Contains all successfully sent messages.

Stored Messages

Contains messages saved for later.

Disregarded Messages

Contains deleted/disregarded messages.

Additional Features
Display Stored Messages

Displays all stored messages.

Display Longest Message

Finds and displays the longest stored message.

Search by Message ID

Allows the user to search for a message using its ID.

Search by Recipient

Displays all messages associated with a recipient number.

Delete by Message Hash

Removes a message using its hash.

Display Report

Displays:

Message Hash
Recipient
Message

for all sent messages.

JSON Storage

Messages selected as "Store Message" are saved to a JSON file.

Example:

{
  "messageID":"1234567890",
  "recipient":"+27838968976",
  "message":"Hello there"
}
Classes Used
QuickChatApp

Main application class responsible for:

Running the application
Displaying menus
Managing user input
Login

Handles:

Username validation
Password validation
Cell phone validation
Registration
Login authentication

Methods:

checkUserName()
checkPasswordComplexity()
checkCellPhoneNumber()
registerUser()
loginUser()
returnLoginStatus()
Message

Handles:

Message creation
Message IDs
Message hashes
Message validation
Message actions

Methods:

checkMessageID()
checkRecipientCell()
createMessageHash()
sentMessage()
printMessages()
returnTotalMessages()
storeMessage()
MessageManager

Handles:

Sent messages
Stored messages
Disregarded messages
Searching
Deleting
Reporting

Methods:

addMessage()
displayStoredMessages()
getLongestMessage()
searchMessageID()
searchRecipient()
deleteMessage()
displayReport()
Testing

JUnit 5 was used to test the application.

The following tests were implemented:

Login Tests

 Username validation

 Password validation

 Cell phone validation

 Successful login

 Failed login

Message Tests

 Message length validation

 Recipient validation

 Message ID creation

 Message hash generation

 Send message

 Store message

 Disregard message

MessageManager Tests

 Longest message

 Search by recipient

 Delete message

 Sent messages array

 Stored messages array
