Lab 1: Creating a Basic Process
===============================

This tutorial teaches you how to create a basic process in Studio and run it on your machine. 
The example opens a browser, loads a certain web page and refreshes the browser.


#### Lab Solutions
Lab solution(s) are present in `Solution\Lab01` folder.

#### Projects
The main types of project supported by UiPath Studio are as follows:

![](./images/c925603f-3cbd-4330-a2e7-0bfe253c537b.png)

#### The user interface
When you first open UiPath Studio, you are directed to the page shown in the following screenshot:

![](./images/20a4ad67-d83b-48e1-b3f6-a23471a62064.png)


Let’s begin.

1.  In the HOME Backstage view, click **Process** to
    create a new project. The **New Blank Process** window is displayed.

![](./images/afd15b4-new_blank_process.png "Click to close...")

2.  In the New Blank Process window:
    -   Enter a name for the new project and a description that
        summaries what you are aiming to do with this automation
        project.
        **Note:** The project name cannot exceed 128 characters, and the description cannot exceed 500 characters.
    -   Select the location where to create the project.
    -   Select **Windows - Legacy** for the **Compatibility** option and **VB** for **Language**.

3.  Click **Create**. The new project is opened in Studio.

4.  Click on `Main.xaml` file to open Designer UI.

5. Open `Google Chrome` and navigate to `https://www.uipath.com/product/studio`. You can use any supported browser, but make sure the required UiPath extension is installed.

6.  In the **Activities** panel, search for **Use Application/Browser**
    and drag it to the **Designer** panel. Notice that the activity is
    automatically added inside a **Sequence**.

![](./images/browser.png)


7. In `Use Application/Browser`, click **Indicate application to automate**, and then move the mouse pointer to the browser page you just opened. When the window is highlighted, click anywhere in the browser page.

8. The `Use Application/Browser` activity is updated, the URL is added to the Browser URL field, and a screenshot of the window appears inside the activity.

9.  From the **Activities** panel, add a **Navigate browser** > **Refresh** to the **Do** container of the **Use Application/Browser** activity.

![](./images/browser2.png)

10. Close the chrome tab where uipath URL was opened before starting the next step.

11. In the ribbon, click **Run File** or use the **Ctrl + F6** shortcut to execute the project.

**Note:** When the execution is completed, notice that the URL was displayed in browser and webpage was refreshed as well.

![](./images/output.png)