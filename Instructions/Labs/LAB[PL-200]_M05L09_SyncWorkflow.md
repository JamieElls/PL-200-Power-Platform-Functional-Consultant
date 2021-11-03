---
lab:
    title: 'Lab 5.9: Create a Synchronous Workflow'
    module: 'Module 5: Build Power Automate flows'
---

Module 5: Build Power Automate flows


## Lab 5.9: Practice Lab – Create a Synchronous Workflow

### Important Notice (Effective November 2020):
Common Data Service has been renamed to Microsoft Dataverse. Some terminology in Microsoft Dataverse has been updated. For example, entity is now table and field is now column. 

While the application is in the process of updating its user experience, some references to terminology like the Common Data Service (now **Dataverse**), entity (now **table**), field (now **column**), and record (now **row**) may be out of date. Please keep this in mind as you work through the labs. We expect to have our content fully up to date very soon. 

For more information and for a complete list of affected terms, please visit [What is Microsoft Dataverse?](https://docs.microsoft.com/en-us/powerapps/maker/common-data-service/data-platform-intro#terminology-updates)

Scenario
---

As a functional consultant at Contoso, you are you continuing to work on a
model-driven Knowledge Admin app for your client Fabrikam. Your client has
requested a modification to prevent users from deleteing active questions. You
can’t use a Microsoft Power Automate cloud flow as these flows only run after an event has occurred. In this lab, you will create a synchronous workflow triggered by the Delete event but processed before the deletion has occurred.

## Exercise 1 – Create Microsoft Power Automate workflow

In this exercise, you will create a synchronous workflow that will run when a Knowledge Question is deleted. This
workflow will check the status and prevent deletion if the status is not Inactive.
### Task 1 – Create a flow

 [] 1.  Navigate to <https://powerautomate.com>.
|    demo                                              | demo |
| ------------------------------------------------- | ---- |
| <input type="checkbox" disabled checked /> works  |      |
| <input type="checkbox" disabled /> works here too |      |
<ul>
    <li><input type="checkbox" checked> First task</li>
    <li><input type="checkbox"> Second task</li>
</ul>
- [x] test

- [ ] 1.  Make sure you have your **Practice** environment selected.

1. [ ]  Select **Solutions** and click to open the **Common Data Services Default
    Solution.**

1. [ ] From the left hand menu, select **Flows.** (If you get a pop-up here, just
    choose your country/region and select **Get started.**)

1.  Click **+ New Automation / Process / Workflow**.

1.  In the new workflow flyout enter **Prevent delete question** for the display name select **Knowledge Question** for the table 
Deselect **Run workflow in the background** 
Click **Create**.

1.  The workflow designer opens 
In the options area, change The scope to **Organisation**
Deselect **record is created** And select **Record is deleted**
Hide The process properties to focus on the process steps.
Click **Add step / Check condition**
Click **Type a step description here** , type **Check that question is Inactive** 
Click condition **Click to configure**.  
1. Select **Knowledge question** in the first drop down select **Status** in the second drop down  
Select **does not equal** in the third drop down 
Select **Inactive** from the pick list and click **OK** 
Click **Save and close**
1. Click on **Select this row** and click **Add step / Stop Workflow** 
1. Change workflow status to **Cancelled** click **Set properties**, for the status message value type **Active knowledge questions cannot be deleted**. Then click **Save and close** 
Activate the workflow , click **Activate**

### Task 2 - Test the workflow
Add a knowledge question name **Delete Test**. Click **Save**. Now delete the newly created question. 
You should get a business process error with your message.
Deactivate the question and repeat the Delete. It should now be deleted.


