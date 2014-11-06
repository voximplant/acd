ACD and Call Queuing: simple call center
=========

![ACD](http://hsto.org/files/34b/626/77c/34b62677c7834f6aab08d55f9f30fbe2.png "ACD & Call Queues")

This project contains [VoxEngine] scenario and web interface for web application for call center operators. It uses [ACD module] to process inbound calls, put them in a queue and forward them to operators serving the queue. This README file describes how to use the provided files to launch the application. The only thing you need to start building your audio conferencing is VoxImplant developer account - you can get it for free at https://voximplant.com/sign-up

Quickstart
----
After you successfully created and activated your VoxImplant developer account you need to login into VoxImplant admin interface and complete these steps to build simple call center with one queue for inbound call processing:
- Create new VoxImplant application called `callcenter` at https://manage.voximplant.com/#applications, its full name will look like `callcenter.youraccountname.voximplant.com`
- Create application users at https://manage.voximplant.com/#users, i.e. `operator1` , `operator2`, etc.
- Create queue at https://manage.voximplant.com/#queues , call it `MainQueue`
![Queue](https://wpcdn.voximplant.com/wp-content/uploads/2014/11/NewQueue-1024x561.png "Queue")
- Create skill at https://manage.voximplant.com/#skills , call it `SomeSkill` and specify the queue and users created before
![Skill](https://wpcdn.voximplant.com/wp-content/uploads/2014/11/Skill-1024x504.png "Skill")
- Create new scenario using the file from VoxEngine folder of the project (ACD.js) at https://manage.voximplant.com/#scenarios
- Buy a phone number at https://manage.voximplant.com/#numbers and assign it to `callcenter` application
- Specify one rule for the application, it will be used to launch the scenario:

    - Name: **InboundCalls**, Pattern: **phone number you've bought**, Assigned scenario: **ACD**. It will handle all inbound calls going to the phone number. 

    
### Using the web application
Just upload the file from the WebApp folder to your web server and change ACCNAME variable value in the html file to your VoxImplant account name, then you can log in using users credentials (your specified while created application users in VoxImplant Control Panel). Inbound calls to the phone number you've bought will go to the queue we created and to operators will be serving the queue.

Version
----
1.0

[VoxImplant]:http://voximplant.com
[VoxEngine]:http://voximplant.com/help/faq/what-is-voxengine/
[ACD module]:http://voximplant.com/docs/references/appengine/Module_ACD.html