<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system, osTicket.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)
- osTicket
- MySQL
<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- [Creating a Virtual Machine from Scratch](https://github.com/jbflores95/Virtual-machine)


<h2>Installation Steps</h2>

![image](https://github.com/user-attachments/assets/945c462d-1d1e-4a3e-be25-74133e026be4)

<p>

</p>
<p>
Before starting this project, we must create a VM in Azure. Log in to the VM using RDP( Remote Desktop Protocol). The link is under the List of Prerequisites.
</p>
Next, we take the osTicket Installation Files and copy and paste them into the VM browser. Download and open the file.
<br />

<p>


![osticket2](https://github.com/user-attachments/assets/89c0becb-1b04-4f80-86e6-43dc1baf1d78)![3](https://github.com/user-attachments/assets/d7945e5d-3cd2-453b-bcfa-b44fef2e45f9)

Next, we're going to click and drag this file to the Desktop. Don't open.
</p>
Once it's on your Desktop, right-click and click Extract All.
<p>

</p>
<br />

![4](https://github.com/user-attachments/assets/d342670d-9046-41a7-9b69-44fefa70a5a7)

<p>

  ![5](https://github.com/user-attachments/assets/8bc99dce-f42d-4bd9-b507-35eace860703)

</p>
<p>

  ![6](https://github.com/user-attachments/assets/1e2676e1-7354-461b-9b19-3b1606087a3b)

Make sure the folder you are extracting says "osTicket-Installation-Files", once confirmed, click Extract.

Next, we are going to enable ISS with CGI. We start by going to the Start Menu, type in Control Panel and open that up. Cick Uninstall a program.

</p>
Then we click Turn Windows features on or off.
</p>
<br />

![7](https://github.com/user-attachments/assets/5ca6dcae-bf3b-4d7c-87d5-e35259853ff4)

</p>
<p>
This opens up Windows Features, where we click on Internet Information Services, expand it by clicking the white box with the  + sign. Next, expand World Wide Web services, then Application Development Features.

</p>
Make sure you click on CGI, then click Ok. Hit close after it installs.
</p>
<br />

![8](https://github.com/user-attachments/assets/8cfdcd72-1b0a-4bd0-8d38-f491e9979c58)

![10](https://github.com/user-attachments/assets/1f992dd1-d56f-4e90-a12d-e7a6ce2bb3a4)


</p>
<p>
Head back to the osTicket Installation files and open up PHP Manager for ISS_V1.5.0. Just hit Next and Yes for anything that comes up, and then click close when it installs.
</p>
Just like we did with PHP Manager, install (rewrite_amd64_en-US) and click yes and next to everything, then click finish.
</p>
<br />

![11](https://github.com/user-attachments/assets/3643405a-86ca-4d1a-87ab-6b7df577651a)

![13](https://github.com/user-attachments/assets/469b8516-fb3e-489f-978c-482fbcc3f451)

</p>
<p>
Next, we create a directory on the Windows C Drive called PHP. To do this, just right-click anywhere on the white space, scroll down to New > Folder. Then, name it PHP.

</p>
Heading back to osTicket Installation Files, right click  (php-7.3.8-nts-Win32-VC15-x86) and click Extract all. Hit Browse, then navigate to the C drive and click on PHP, then hit Extract.

</p>
Next, we install VC_redist.x86.exe. Hit install, then hit yes if anything pops up. Then hit close.
</p>
<br />

![14](https://github.com/user-attachments/assets/29e1766a-ba70-4e07-9577-05b86ae61171)


![15](https://github.com/user-attachments/assets/2fb7bafe-7c34-4ce4-af5b-9deb61d2a0b8)
![16](https://github.com/user-attachments/assets/2b6b8b2f-dab3-42f4-9d37-ce95ef1b2ff7)

</p>
<p>
After we get Redist installed, we install MySQL-5.5.62-win32, which is a database where all our data is going to be collected on osTicket. Just like the others, hit yes and next to everything. Make sure you click on Typical, then Install.
</p>
Launch and hit Finish. Hit Next, then make sure Standard Configuration is checked, then hit Next until u get to the User and Password. !!!There, we type in ROOT for the user and Capital ROOT for the password. Don't mess this part up!!! Hit Next, Execute, and then finish.
</p>
<br />

![17](https://github.com/user-attachments/assets/3eeedba5-4e15-45aa-b374-116f14b69f51)

</p>
<p>
We're getting there, I swear, bear with me. Now we open up ISS as an Admin by going to the Start menu and typing is, right click ISS and click run as administrator. We're going to register PHP from within ISS, which means we're making the web server aware of the existence of PGP on the computer. 
</p> 
Now double click PHP manager
</p>
<br />

![18](https://github.com/user-attachments/assets/4cac81f2-b7a8-4e96-8a41-70da9ecee050)
![20](https://github.com/user-attachments/assets/fac7eb4a-8a78-4c84-9248-b865f46c8ccc)

</p>
<p>
Now click on "Register New PHP version", click on the dots and navigate to the C drive and click on PHP.

</p>
Select php-cgi and click Open, then hit Ok.
</p>
<br />

![21](https://github.com/user-attachments/assets/fa3e67f8-b3ab-4ef2-96c5-e5c00516f26e)
![22](https://github.com/user-attachments/assets/2d9c907c-5e1d-4bca-b6f6-e45520513561)


</p>
<p>
Now we need to reload ISS to restart the web server. To do this right right-click osTicket-vm and then select Stop.
</p>
Wait a few seconds, then right-click osTicket-vm again, then select Start.
<br />

</p>
<p>

</p>
<br />

![23](https://github.com/user-attachments/assets/516bf07a-56ec-43e1-a1d3-6769f7fc52dd)
![24](https://github.com/user-attachments/assets/9183f3c4-3d2e-45d7-a9e8-08ede5a4ce32)

</p>
<p>
Head back to the osTicket Installation Files, right-click osTicket-v1.15.8zip, then click on Extract all. Hit Extact again when the pop up appears and wait for it to complete.
</p>
Now you see  it made another folder at the top.
</p>
<br />

![25](https://github.com/user-attachments/assets/038b9de6-8b5d-47bd-81b2-4c8e975a3a33)
![26](https://github.com/user-attachments/assets/9c553028-9965-46be-a70e-3b0bd2c7e1e8)
![27](https://github.com/user-attachments/assets/d9048db4-e21c-4729-a6c1-d506998a7472)

</p>
<p>

You can now see the new folder after it completes. We will come back to this.
</p>
We navigate back to the C Drive and we open inetpub. Then we open up the wwwroot folder.
<br />

</p>

![28](https://github.com/user-attachments/assets/d7537967-8c5a-4a23-aabd-ae03e71fb869)
![29](https://github.com/user-attachments/assets/0fedd5a1-6d77-4436-91c1-2b4e53aae65f)

<p>
Now, drag the upload folder from osTicket-v1.15.8; it should be next to scripts, but I already did this. You can see that the upload folder is in the wwwroot folder.
</p>
Rename the upload folder to osTicket, make sure it's spelled exactly how I typed it here, it will mess up things later on if you don't.

</p>
We need to reload ISS again like we did before. Refer back up above if you have forgotten how to do so.
<br />
</p>

![30](https://github.com/user-attachments/assets/cd3299af-0200-4033-9b6f-35ee801ed331)
![31](https://github.com/user-attachments/assets/280a67ea-453d-4f22-afcd-0b9a894d0984)

</p>
<p>
In ISS expand osticket-vm, then Sites > Default Sites, click on osTicket. On the right-hand side, click on Browse*:80(HTTP)
</p>

Now if you got this on your screen "OsTicket Installer", " Thank you got choosing osTicket", you are on the right track!
</p>
Were almost there, you can see were missing some extensions. Time to get down and dirty and fix these problems. 
</p>

![32](https://github.com/user-attachments/assets/1ef6ac25-6531-4d6e-bd8f-c76256bec2e7)
![33](https://github.com/user-attachments/assets/4ad1fb0a-fcf6-4e5e-b3a5-7cff45fe2ecf)

<p>
Go back to ISS, in ISS go to  sites -> Default -> osTicket then double PHP manager. Click “Enable or disable an extension.”
</p>
<br />

![34](https://github.com/user-attachments/assets/3e790651-4c3b-40d1-8ffd-36695bc7633a)![35](https://github.com/user-attachments/assets/b461c785-8267-47c7-a87c-9a1c2a701cdb)
![36](https://github.com/user-attachments/assets/44061e9c-55c5-4f58-a3a0-edad7ad3bd28)

</p>
<p>
Now we're going to enable some extensions by right-clicking each of them. Enable php_imap.dll, then php_intl.dll, and lastly php_opcache.dll
</p>
<br />

![37](https://github.com/user-attachments/assets/73eebe6e-9090-4c1d-817a-793bc3572729)

</p>
<p>
Head back to the osInstaller and hit refresh on the website, you should now see some checkmarks for more extensions. Two more to go. Lets do this!
</p>
<br />


![38](https://github.com/user-attachments/assets/b114074e-6770-47cb-a461-93b671f80195)![39](https://github.com/user-attachments/assets/bffc6f37-d660-4356-b84d-e575a3375830)
![40](https://github.com/user-attachments/assets/120d9e0d-6245-43e7-9cef-09c64d8d2f7e)


</p>
Head back to Windows C Drive, go to inetpub, then wwwroot. Now click on osTicket then include and scroll down to ost-sampleconfig.php.
</p>
Right click ost-sampleconfig.php and click on rename, rename it to ost-config.php.
</p>
<br />

![41](https://github.com/user-attachments/assets/6c36b798-b79a-4ce7-954b-71c4582695f8)![42](https://github.com/user-attachments/assets/5abc17fe-cc27-445b-91ee-a86cfdc6d7b3)


</p>
<p>
Right-click ost-config.php and  click Properties.
</p>
Navigate to Security and click Advanced.

</p>
Click Disable inheritance.
</p>
<br />

![43](https://github.com/user-attachments/assets/46f210f3-a307-4367-abd7-8bfa53d38e2d)
![44](https://github.com/user-attachments/assets/e8280688-4bfc-445d-a097-2f43300f83ac)
</p>
Click on Remove all inherited premissions from this object,
</p>
Click Add.
<p>
  
</p>
<br />

![45](https://github.com/user-attachments/assets/8fd2f343-604f-400a-a843-8d83aa40a34c)
![46](https://github.com/user-attachments/assets/cdd9a72b-e3b0-4e50-893f-419a1f91fb49)
![47](https://github.com/user-attachments/assets/c1c5a5c3-3d8a-4488-b2ee-9338d5d80784)


Now, click on Select a principal and type in everyone. Click on Domain names so that  everyone has access. You should not do this in a real work environment because of security issues but its fine for this lab.
</p>
Then click on Full Control and hit ok.
</p>
<br />

![48](https://github.com/user-attachments/assets/1ec000bf-64c6-4162-b0cd-4bcb84e80654)![49](https://github.com/user-attachments/assets/a7413099-f40e-4a17-982b-76e1b6b9f2b8)


<p>
Make sure it says ost-config.php on top, and make sure all the info is correct as well. Click Apply and then Ok.
</p>
Click Ok for the next one too.
</p>
<br />

![50](https://github.com/user-attachments/assets/96f1c774-07ac-4d43-b549-381f1dc34f2d)


Back to the osInstaller on your browser, click Continue. Here we don't need any specific name or default Email, I just used my name.
</p>
Under Admin user, you can enter your first and last name, just make sure the email here is different from the one above.
</p>
For Username, you can put "adminuser", Password: "Password1", don't forget this. You can write it down.
<br />
</p>

![51](https://github.com/user-attachments/assets/52443f82-1839-4cd9-a54b-9d80e8d8e05a)![52](https://github.com/user-attachments/assets/59b40426-4637-4f41-8b45-c9a278f48af5)



<p>
The finish line is here. Go back into osTicket-Installation-Files and install HeidiSQL. HeidiSQL is just an application that allows us to make a connection to our database and lets us configure it. Just like the other ones, just hit Next and hit install. Finish and hit skip to launch HeidiSQL
</p>
In HeidiSQL, we are going to make a connection to our database and then set up a database for osTicket to use. With that in mind, click on New.
</p>
SUPER IMPORTANT HERE! The user will be lowercase root, and the password is ROOT in uppercase. Don't mess this part up. CLick Open
<br />
</p>

![53](https://github.com/user-attachments/assets/819bb33b-9963-4da7-815b-653f31da6aa6)
![54](https://github.com/user-attachments/assets/a8e3aec5-7c87-43c5-8a7e-3a65e0847937)


</p>
<p>
This opened a connection to our database. Now, right-click Unnamed, scroll down to Create new, and click on Database.
</p>
Name this "osTicket", just like the password, make sure it's exactly how I spelled it. You can now click Ok.
</p>
<br />

![55](https://github.com/user-attachments/assets/e677e861-c904-4d63-b7d0-387a4be022cf)![56](https://github.com/user-attachments/assets/400bb983-1116-4352-b3a3-8726d25b191b)

</p>
<p>
Back to the osInstaller in your browser, scroll down to Database Settings and insert the Database, Username, and Password.
</p>
MYSQL Database: osTicket
</p>
MySQL Username: root
</p>
MySQL Password: ROOT
</p>
After you insert those in just click Install Now.
</p>
Bravo! Your next screen should say Congratulations. osTicket has now been installed. That took a hot minute, huh? Pat yourself on the back if this only took you one try; you deserve it.
<br />
</p>

![57](https://github.com/user-attachments/assets/5cecc6f5-19d6-44e0-aea2-affe5319ffca)

</p>
<p>
Now you can log into osTicket help desk. This is what your screen should look like if we click on this link. You can copy and paste this into your browser. 
</p>
http://localhost/osTicket/scp/login.php
</p>
<br />


<h3>Final Thoughts</h3>

You and I have successfully installed osTicket. This was a blast, dont you think? From configuring the environment to troubleshooting common setup issues, the process deepened my skills in server setup, database integration, and web applications. This project challenged me to apply both technical knowledge and problem-solving skills. Knowing how to deploy and configure tools like osTicket is directly applicable to real-world IT roles. I could easily see this being useful in a help desk environment or small business support team.
