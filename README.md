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

<img src="https://i.imgur.com/F7DhzQS.png" height="80%" width="80%"  alt="Active Directory" />

This will open a new window where I will first be asked for the users to whom I want to delegate control:

<img src="https://i.imgur.com/6y4xkun.png" height="80%" width="80%"  alt="Active Directory" />

To avoid mistyping the user's name, I can write "phillip" and click the Check Names button. Windows will autocomplete the user for me.

<img src="https://i.imgur.com/iIFjB3j.png" height="80%" width="80%"  alt="Active Directory" />

Click OK, and on the next step, select the following option:

<img src="https://i.imgur.com/rFeb1sB.png" height="80%" width="80%"  alt="Active Directory" />

Click next a couple of times then click finish, and now Phillip should be able to reset passwords for any user in the sales department.

<img src="https://i.imgur.com/q4stXi6.png" height="80%" width="80%"  alt="Active Directory" />

We could attempt to go to Active Directory Users and Computers to try and test Phillip's new powers, but he doesn't really have the privileges to open it, so I'll have to use other methods to do password resets. In this case, I will be using Powershell to do so:

<img src="https://i.imgur.com/LnhwzGe.png" height="80%" width="80%"  alt="Active Directory" />

Since I wouldn't want Sophie to keep on using a password I know, I can also force a password reset at the next logon with the following command:

<img src="https://i.imgur.com/BZEolow.png" height="80%" width="80%"  alt="Active Directory" />

Next I'm going to Log into Sophie's account with the new password and retrieve a flag from Sophie's desktop. First I'll use rdp in linux to log in remotely:

<img src="https://i.imgur.com/oMjyufS.png" height="80%" width="80%"  alt="Active Directory" />

Then I'll sign in with the password I created:

<img src="https://i.imgur.com/xrgd7xk.png" height="80%" width="80%"  alt="Active Directory" />

The system is forcing me to change the password just like I told it to in the powershell script:

<img src="https://i.imgur.com/u03ItWi.png" height="80%" width="80%"  alt="Active Directory" />

Creating a new password:

<img src="https://i.imgur.com/R52ofc4.png" height="80%" width="80%"  alt="Active Directory" />

Finally, I'm sign in! I'll click on the flag text file to view the flag.

<img src="https://i.imgur.com/W6jVtUH.png" height="80%" width="80%"  alt="Active Directory" />

<h3>Managing Computers in AD</h3>
By default, all the machines that join a domain (except for the DCs) will be put in the container called "Computers". If we check our DC (Domain Controller), we will see that some devices are already there:

<img src="https://i.imgur.com/P6MBy4E.png" height="80%" width="80%"  alt="Active Directory" />

We can see some servers, some laptops and some PCs corresponding to the users in our network. Having all of our devices there is not the best idea since it's very likely that you want different policies for your servers and the machines that regular users use on a daily basis.

Since I am tidying up my AD, I'll create two separate OUs for Workstations and Servers. I will be creating them directly under the thm.local domain container. In the end, I will have the following OU structure:


<img src="https://i.imgur.com/EemDJ55.png" height="80%" width="80%"  alt="Active Directory" />

Next, I'll move the personal computers and laptops to the Workstations OU and the servers to the Servers OU from the Computers container. Doing so will allow me to configure policies for each OU later.

<img src="https://i.imgur.com/EemDJ55.png" height="80%" width="80%"  alt="Active Directory" />


<img src="https://i.imgur.com/EemDJ55.png" height="80%" width="80%"  alt="Active Directory" />


<img src="https://i.imgur.com/EemDJ55.png" height="80%" width="80%"  alt="Active Directory" />


<img src="https://i.imgur.com/EemDJ55.png" height="80%" width="80%"  alt="Active Directory" />


