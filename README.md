# Active Directory Essentials

During this task, I'll assume the role of the new IT admin at THM Inc. 

<h3>Active Directory Users and Computers</h3>
To configure users, groups or machines in Active Directory, we need to log in to the Domain Controller and run "Active Directory Users and Computers" from the start menu:

<img src="https://i.imgur.com/VyTIEZs.png" height="80%" width="80%"  alt="Active Directory" />

This will open up a window where you can see the hierarchy of users, computers and groups that exist in the domain. These objects are organised in Organizational Units (OUs) which are container objects that allow you to classify users and machines. Checking our machine, we can see that there is already an OU called THM with four child OUs for the IT, Management, Reasearch and Development, and Marketing and Sales departments.

<img src="https://i.imgur.com/Qv2uq4M.png" height="80%" width="80%"  alt="Active Directory" />

I'm going to right-click the THM OU and create a new OU under it called Students.

<img src="https://i.imgur.com/iW4dPVY.png" height="80%" width="80%"  alt="Active Directory" />

<img src="https://i.imgur.com/lKf1Cyb.png" height="80%" width="80%"  alt="Active Directory" />

<h3>Managing Users in Active Directory</h3>
My first task as the new domain administrator is to check the existing AD OUs and users, as some recent changes have happened to the business. I have been given the following organisational chart and am expected to make changes to the AD to match it:

<img src="https://i.imgur.com/KdiXMUS.png" height="80%" width="80%"  alt="Active Directory" />

<h4>Deleting extra OUs and users</h4>
The first thing I notice is that the Reasearch and Development department doesn't appear in the chart. I've been told it was closed due to budget cuts and should be removed from the domain. By default, OUs are protected against accidental deletion. To delete the OU, I need to enable the Advanced Features in the View menu:

<img src="https://i.imgur.com/rjoY3gK.png" height="80%" width="80%"  alt="Active Directory" />

This will show us some additional containers and enable me to disable the accidental deletion protection. To do so, I'll right-click the OU and go to Properties: 

<img src="https://i.imgur.com/j0UHhCf.png" height="80%" width="80%"  alt="Active Directory" />

There will be a checkbox in the Object tab to disable the protection:

<img src="https://i.imgur.com/V4kMBOD.png" height="80%" width="80%"  alt="Active Directory" />

The Reasearch and Development department has been deleted:

<img src="https://i.imgur.com/yevLnve.png" height="80%" width="80%"  alt="Active Directory" />

<h4>Delegation</h4>
We will delegate control over the Sales OU to Phillip. To delegate control over an OU, you can right-click it and select Delegate Control:

<img src="https://i.imgur.com/Kkeh167.png" height="80%" width="80%"  alt="Active Directory" />




