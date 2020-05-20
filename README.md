ACD and Call Queuing: simple call center
=========

![ACD](http://hsto.org/files/34b/626/77c/34b62677c7834f6aab08d55f9f30fbe2.png "ACD & Call Queues")

This project contains a [VoxEngine] scenario and the Web client for call center operators. It uses the [ACD module] to process inbound calls by putting them in a queue and forward them to operators serving the queue. This README file describes how to use the provided files to launch the application. The only thing you need to start building your audio conferencing is a Voximplant developer account - you can get it for free at https://voximplant.com/sign-up

Quickstart
----
After you successfully created and activated your VoxImplant developer account you need to login into VoxImplant admin interface and complete these steps to build simple call center with one queue for inbound call processing:
- Create a new VoxImplant application called `callcenter` at https://manage.voximplant.com/applications, its full name will look like `callcenter.youraccountname.voximplant.com`
- Beint within this newly created application, create a couple of application users on the **Users** tab, i.e. `operator1` , `operator2`, etc.
- Create a queue on the **Queues** tab, call it `MainQueue`
![Queue](https://wpcdn.voximplant.com/wp-content/uploads/2014/11/NewQueue-1024x561.png "Queue")
- Switch to the **Scenarios** tab and create a new scenario using the file from VoxEngine folder of the project (ACD.js) at 
- Buy a phone number at https://manage.voximplant.com/numbers and assign it to `callcenter` application
- Specify one rule for the application, it will be used to launch the scenario:

    - Name: **InboundCalls**, Pattern: **phone number you've bought**, Assigned scenario: **ACD**. It will handle all inbound calls going to the phone number. 

    
### Using the web application
Just upload the file from the WebApp folder to your web server and change the ACCNAME variable value in the html file to your Voximplant account name, then you can log in using users credentials (your specified while created application users in Voximplant Control Panel). Inbound calls to the phone number you've bought will go to the queue we created and to operators will be serving the queue.

Version
----
1.0

[VoxImplant]:http://voximplant.com
[VoxEngine]:https://voximplant.com/docs/introduction/introduction_to_voximplant/capabilities_and_components/voxengine
[ACD module]:https://voximplant.com/docs/references/voxengine/acdrequest
