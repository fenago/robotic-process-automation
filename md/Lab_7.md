<img align="right" src="./logo.png">



Lab 7. Handling User Events and Assistant Bots
-----------------------------------------------------------



In UiPath, there are two types of Robot that are used for automating any
process. One is the back office Robot, which works in the background. It
works independently, which means it does not require inputs from users
or any user interaction. The other one is the **Front Office
Robot**, which is also known as an **Assistant
Robot**.

This lab deals with front office bots.
Here, we will learn the different ways in
which events in the automation process can be triggered---by a simple
press of a key, click of the mouse, and so on. To make things clearer,
we will take examples of monitoring various events.

We will cover the following topics in this lab:


-   What are assistant bots?
-   Monitoring system event triggers
-   Monitoring image and element triggers
-   Launching assistant bots on a keyboard event


What are assistant bots?
------------------------------------------



Assistant Robots are front office Robots that require some user
interaction. In this case, the automation will run only when a certain
event or user action is triggered.

Trigger events are basically commands to tell the Robot to start its automation process.

For example, say I want some text to be typed into the Notepad
application. In particular, I want the Robot to type into the Notepad
once I click on the text area (clicking being the trigger activity in
this case) in the Notepad application.

Let us look at the following steps to understand more:


1.  **Drag and drop the Monitor events activity**: Here, we
    drag and drop a ****`Monitor events`** **activity from
    the **`Activities`** panel inside which the trigger events will
    work; otherwise it will show you an error. The **`Monitor events`**
    activity looks like this:



![](./images/1c699d59-1dad-407b-a5e2-6ef86e8f34e2.png)



2.  **Drag and drop the trigger activity of choice**: In the
    drop trigger area, drag and drop the trigger activity that you want.


There are a lot of trigger activities shown in the **`Activities`**
panel. In this case, we will choose the
****`Click Trigger`**** activity:


![](./images/fc8e26c9-cb8c-4ad3-8d37-8135f3ddaeb8.png)



3.  **Create workflow inside the Monitor events activity**:
    Now inside the **`Event handler`** space in the
    ****`Monitor events`****activity, we have to create the
    workflow or the set of tasks we are required to do once the trigger
    activity works. In this case, we are using
    the****`Type into`****activity. Indicate the blank area
    of a Notepad window:



![](./images/7566b414-5158-4eca-9a39-2cd52e788486.png)


This was an overview of how assistant bots work.



Monitoring system event triggers
--------------------------------------------------



 There are three
system trigger events---**`Hotkey Trigger`**,
**`Mouse Trigger`**, and **`System Trigger`**:


![](./images/5973e24d-23f3-421f-8746-9d6c0e9e96e8.png)


Though all three triggers are used for triggering activities, they are
used differently as explained in the following section.


### Hotkey trigger



Hotkey trigger works for shortcut keys. Suppose we want a certain workflow to work once the user presses the
[*Alt*] + [*F4*] keys or any other shortcut key.
In such a case, we will use the
**`Hotkey trigger`**:



![](./images/ac89a46c-66fa-4327-bbe0-517d778b65bd.png)




### Mouse trigger



This is used when we want to trigger events
on performing a mouse action (left-click, right-click, or middle-click)
as shown in the following screenshot:


![](./images/247ad6c7-1c8d-46ec-b4a3-f948905ae548.png)


As shown in the screenshot, we can select the type of click with which
we want to trigger events. We can also use other special keys with mouse
actions as shown.



### System trigger



This is the last type of system trigger activity. A system trigger is
used to trigger events on mouse actions,
keyboard actions, or both, all of which we can select from the
**`Properties`** panel. We can also select the action to be performed,
that is, forwarding the event or blocking the event as shown in the
following screenshot:


![](./images/d8654481-9da6-4781-b3d9-f0ef6f6777e4.png)



Monitoring image and element triggers
-------------------------------------------------------



With an image trigger, the events will
occur once the user has clicked on a certain image that is indicated in
the **`Click Image Trigger`** activity.

By clicking on **`Indicate element on screen`**, we have to select an
image that will trigger the event when
clicked.

In the **`Element Trigger`**, there are two activities that come into
play. These are **`Click Trigger`** and **`Key Press``Trigger`** as
shown in the following screenshot:


![](./images/737e245c-650b-4564-9034-a3b08801a12f.png)



-   The ****`Click trigger`**** activity is used to trigger
    events when a user simply clicks on a UI element:



![](./images/feed991b-9e8b-448a-b9a3-2b869305ce2a.png)



-   The ****`Key press trigger`**** activity is used when we
    need to trigger events by pressing a certain key or by selecting the
    image on the screen to trigger events:



![](./images/8b7ee6f6-d32d-49fb-a16c-85d2b683c713.png)



### An example of monitoring email



To make things clearer, we will monitor a send email
event through Gmail. The steps are listed as
follows:


1.  **Open the browser and browse to www.gmail.com**: To do
    this, drag and drop the **`Open browser`**activity. In the required
    field for the address, enter`www.gmail.com`:



![](./images/8bf015db-a289-4afe-8152-33d5f80919b4.png)



2.  **Getting username and password**: After typing in the
    address, we have to ask the user for a username and password. For
    this, we will use the ****`Input dialog`**** activity as
    shown in the following screenshot. We have dragged and dropped two
    ****`Input dialog`**** activities to ask the user for a
    username and password respectively. Until the user types in each
    dialog and presses okay, the Robot will not work:



![](./images/5fc9f9e0-de4e-4fb4-b146-94480f3e9396.png)


Once the user types in the **`username`** and **`password`**, we save
these details into two variables: `user` and `pass`.
You can convert their values into a variable by going to the
**`Input dialog`** property in the **`Properties`** panel. Just
right-click on the empty text box of the **`Resul`**t property and
choose **`Create``Variable`**. We have named it **`user `**as shown in
the following screenshot:


![](./images/2efc3552-3edc-469a-90fb-1d47b3d789c8.png)



3.  **Entering a username and password**: We shall use the
    **`Type into`**activity to enter a username and password by
    indicating the respective fields for typing in the username and
    password.


Once the user enters the username and password, he needs to login which
he can either do by clicking on the login button or by pressing the
[*Enter*] key on the keyboard.  We will use the
**`Send hotkey`** activity to send the [*Enter*] key (as
shown in the following screenshot). By doing so, the login button is
clicked:


![](./images/927ce57d-8c53-4a34-b115-1d9079859760.png)



4.  **Trigger the send email event with a Hotkey trigger**:
    Our next step is to trigger the send mail event. Here, pressing the
    [*Enter*]key will be the trigger. On pressing it, the
    Robot performs the rest of the send email task. For this, we will
    use the Hotkey trigger activity. We first have to drag and drop
    the**`Monitor events`**activity as trigger activities only work
    under it:


![](./images/a8f67ea0-5191-4e08-b0e9-f7f658180552.png)


Since we are using the **`Hotkey trigger`**, we have dropped the
**`Hotkey trigger`** activity in that area:


![](./images/d0860922-e00e-47b1-8807-3ef6129950bc.png)


In the area for the **`Event handler`**, we need to give the sequence of
steps for sending the mail, which will involve several steps. For this,
we have created a workflow showing all the steps to be followed to send
an email. This ranges from clicking on Compose mail to clicking on the
Send button as explained in the following steps.


5.  **Ask the user for the email ID of the recipient, the subject of
    the email, and its body**: Our next step is to ask the
    user for details. We will use three Input dialogs, one for the email
    ID, one for the subject, and one for the content.


As shown in the screenshot, we have used an Input dialog to obtain the
recipient\'s email ID:


![](./images/b4ec436f-a346-4182-8a54-a2fe722495dd.png)


We now save the user input email ID inside a variable called
`name` (you can easily create a variable by pressing
[*Ctrl*] + [*K*] inside the **`Output`** box in
**`Properties`**):


![](./images/60cea9a7-75ab-4751-91c3-a285c1a259fe.png)


In the second **`Input dialog`**, we will ask the user to input the
subject for the email:


![](./images/83252609-4063-424e-b336-ff1b1784fc45.png)


The output, that is, the response entered by the user, is saved as a new
variable called `Subject?` as shown in the following
screenshot:

![](./images/c524fb43-d881-4a5d-815f-482e6cc39dac.png)


In the third input dialog, the user has to input the message/mail he or
she wants to send:


![](./images/9e032d76-2712-499b-a9ff-6b3bac8e2090.png)


We shall store the user output as a variable called `message`:


![](./images/1b907775-3f86-4801-8d94-cfe92875b9c0.png)



6.  **Type in the details**: Now that we have all the
    details that are required for sending the
    mail, our next step will be to type into the required fields for
    sending the email. We will use the **`T``ype Into`**activity for
    this step:



![](./images/90d92ee7-eeb7-4a0d-9636-01e11cd0d60b.png)


Drag and drop the **`Type into`** activity. Then, double-click on it and
indicate the area where you want to type the email ID. Since we have
saved the email ID as a variable, `name`, we enter this in the
field provided, as shown in the following screenshot:


![](./images/ae627c49-18f3-4642-b299-2e98763fdc06.png)


Our next requirement will be to indicate the area where we want to type
the subject of the mail. Since we have saved the subject as a
variable, `Subject`, we enter this in the field provided as
shown in the following screenshot:


![](./images/0ec00a6e-ce9a-4ebe-8ca1-f504004be378.png)


Now you are required to indicate the area where you want to type the
message/mail as indicated in the screenshot. Since we have saved the
content of the mail to be sent as a variable, `message`, we
enter this in the field provided as shown in the following screenshot:


![](./images/9f36b241-402c-4ebd-aa3b-c21c23aeaeae.png)



7.  **Click on Send and confirm if successfully sent**: Our
    final step is to click on the **`Send`**button so that the mail is
    sent and the process is completed. In order to click on
    the**`Send`**button, we will use the**`Click`**activity and indicate
    the**`Send`**button. Doing so enables the Robot to easily recognize
    where to click:



![](./images/5a45e5cf-e603-4890-9f9d-3bcd767b7273.png)


If you want, the Robot can also give a notification once the mail is
sent. For this notification we will use the
****`Message box`**** activity, which will display the
message, **`message is sent`**, as shown in the following screenshot.
When the message is displayed, and after the user has pressed **`OK`**,
the whole workflow will terminate since all
of the steps have been executed:


![](./images/19664443-f027-42ce-9586-1d9b490bbdff.png)




### Example of monitoring a copying event and blocking it



Let us take an example of monitoring a copying event and blocking it. In this example, we have an
Excel file from which we want the data to be
copied as soon as the user presses the [*Enter*] key:


1.  **Drag and drop the Monitor events activity and the drop trigger
    activity into it**: Drag and drop the
    ****`Monitor events`****activity. Double-click on it:



![](./images/d9944165-4d9c-4dbd-bb3a-54f16449bd8f.png)


Drag and drop the **`Hotkey trigger`** activity and select the
[*Enter*] key from the drop-down list, as shown in the
screenshot:


![](./images/e257d89a-9dcc-41c6-a16b-344a7f7cce9c.png)



2.  **Drag and drop an Excel application scope inside the Event handler
    portion**: We are required to drop an activity under
    **`Event Handler`**. In our case, the activity is copying data from
    Excel and pasting it. When we drag and drop
    the****`Excel application scope`****activity inside
    the**`Event handler`**and double-click on it, we see that first we
    have to browse to the Excel file from which we want to copy the
    information:



![](./images/7b4323cd-3452-4748-9e83-8b65e538212d.png)


As shown in the screenshot, we have selected an Excel file whose name is
`movies`; now we want to copy this file\'s content.


3.  **Use the Read Range activity, extract the data and paste it into a
    new Excel file**: Now, inside the **`Do`**activity, drag
    and drop the****`Read Range`****activity to read all the
    data from this Excel file. We will keep
    this extracted data in a variable named`movies`, as shown
    in the screenshot:



![](./images/cca0a6e6-609a-4c5b-b25c-c25fc629fd80.png)


 

We have read the data from the Excel file. Next, we want to keep it in a
variable. For this, just click on the **`Read Range`** activity and go
to the **`Properties`** panel. Then create a variable by pressing
[*Ctrl*] + [*K*] and name it `movies`:


![](./images/7b4e5eb0-0665-46b6-8a76-a6a6bdb3d144.png)



4.  **Append to another Excel file**: Now, since we have
    all the data saved, we can just drag and
    drop another Excel application scope. Then we will indicate the file
    that we want to append this data to. In the **`Do`**activity, just
    drag and drop the**`Append Range`**activity. Select the input as the
    variable we declared earlier, that is,`movies`as shown in
    the screenshot:



![](./images/aa3477b4-103e-4d3a-899b-dc4ca0204ee5.png)



5.  **Block the triggered event**: Now, in order to block
    triggered events you can select the `EVENT_BLOCK`event as
    the event type from the properties of the trigger in
    the**`Properties`**panel as shown in the following screenshot:



![](./images/73e401ce-9786-40c1-a7cc-4cf7c5c79ab6.png)



Launching an assistant bot on a keyboard event
----------------------------------------------------------------



Let us say we want our assistant bot to start automating only when we trigger an event. For example, the user wants
his Robot to open and start typing in the Notepad window when he presses
[*Alt *]+ [*W*]. This can be achieved using the
Hotkey trigger. Also, inside the Event handler, just create or record
the sequence of steps to be followed. The
detailed procedure has been explained in the following sections:


1.  **Drag and drop the Monitor events activity**: In this
    step, we will just drag and drop the
    ****`Monitor events`****activity into the workflow. When
    we double-click on it, it will look like this:



![](./images/241bed03-c87c-4cf6-9fb3-9a6a110554da.png)



2.  **Drag the Hotkey trigger activity**: In the next step,
    we will use the **`Hotkey trigger`**activity for the user to start
    the automation process. Assign[*Alt*]+[*W*]to
    the hotkey so that, when the user presses this hotkey, the event
    will be executed:



![](./images/3e3c01c4-1015-4086-a9b6-0ea54008ba38.png)



3.  **Open Notepad and type into it**: Our final step is to
    record the sequence of the steps to be performed. In this case, this
    is to open Notepad and then type into it. For that just use the help
    of the **`Desktop`**recorder. First, we double-click on the Notepad
    application in the window as shown in the screenshot. Select
    the**`ClickType`**as ****`CLICK_DOUBLE`****from
    the**`Properties`**panel:



![](./images/16f0e9bb-8ca8-41ed-8c70-0dd8d10901c8.png)


After that, we record the typing action and close the Notepad window.
Then click on **`Do not Save`** because you do not want to save your
file. The sequence is shown in the following
screenshot:


![](./images/a65147a1-a31a-472d-b202-60b9f58b0275.png)



**Note:**

We have also indicated the anchor to recognize the correct button to be
clicked (in this case, the close window button\'s anchor is the maximize
button). This makes it easier for the Robot to find the UI element.


Now, on pressing [*Alt*] + [*W*] the
Robot will start executing the sequence.


Summary
-------------------------



In this lab, we learnt about the assistant bot\'s utility. We also
covered all the monitoring events that can be used to trigger actions
and also saw examples of them. Once your automation program is made,
there may still be problems that you are likely to face while executing
it. To handle such scenarios, we will learn about Exception Handling in
the following lab.

