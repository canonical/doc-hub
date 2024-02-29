This short How-to will guide you through the creation and basic configuration of a public room on the Ubuntu Matrix homeserver. This guide assumes you are using the Element desktop client.

## Private room creation

1. Click on the "All rooms" icon on the top left of your Element desktop client. This icon is represented by a house, and can be found below the user avatar.
2. Click on the + Icon on the left of **"Home"** and  below the compass icon used to search for rooms. Select "New Room". 
   >  :warning: It is important to ensure you are **on your home screen** when clicking on the `+` icon. Otherwise, it will try to create a room _inside_ of the space you're currently in. This will fail in the Ubuntu space. If you want to add a room to one of our spaces, then first create the room outside of the space, and then follow the guide [How-to publish and list rooms and spaces](https://ubuntu.com/community/communications/matrix/rooms-spaces).
3. In the "Name" field, you type the display name of the room. This name can contain upper and lower case characters, spaces, and can be changed later.
4. The "Topic" field is for the description of your room. This field is optional and can be filled later.
5. In the dropdown, select "Private room (invite only)".
6. The last but most important choice to make is about end-to-end encryption.
   >  :warning: The recommendation is to toggle encryption off before creating the room. Disabling encryption later on is not possible. Enabling encryption will cause issues with bots, bridges, and overall lower the user experience of your room.
7. Double-check your settings, then click on "Create room".


## Room configuration: General Settings

1. After your room is created, click on the room name dropdown on the top of your Element desktop client, and select "Settings".
2. In the "General" settings, you can change "Room Name", "Room Topic", and add a "Room image".
3. In the "General" settings, you can also check your published addresses, and local addresses. If you cannot enable the "Publish this room to the public in the `ubuntu.com`’s room directory?", please note this is intended behavior. Check steps in the "Room publishing and listing under spaces" section to complete this task.

## Room configuration: Security & Privacy settings

* In the "Security & Privacy" settings, you can change your room from Private to Public, or Space members.
   > :warning: Please **never enable encryption** for public rooms. You cannot turn it back off, and it gives a lot of issues with public rooms.


## Room publishing and listing under spaces

Please check [How-to publish and list rooms and spaces](https://ubuntu.com/community/communications/matrix/rooms-spaces) if you'd like to:

* Protect your room from abuse
* Publish your room in the server directory
* Add your room to the Ubuntu Community space


## Learn more

Congratulations! Your private room is now ready! If you would like to learn more about the Ubuntu Matrix homeserver, you can check our documentation: https://ubuntu.com/community/communications/matrix