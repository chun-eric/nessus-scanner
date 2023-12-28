
<h1>Tenable Nessus Vulnerability Scanner and Remediation -- Home Lab Project</h1>


<h2>Description</h2>
This project consisted of a configured Windows virtual machine (vm) on VirtualBox that has a whole bunch of outdated software and vulnerabilities purposely installed.  
<br/>
<br/>

The goal of this project is to conduct a comprehensive vulnerability scan using Tenable Nessus configured to include credentialed scans and to showcase effective remediation strategies to 
address the identified vulnerabilities.  
<br />


<h2>Languages or Utilities Used</h2>
- <b>Tenable Nessus Vulnerability Scanner</b> 


<h2>Environments Used </h2>
- <b>Windows 10 ISO</b>
- <b>Oracle Virtual Box</b> 

<br/>
<br/>
<h2>Program walk-through:</h2>

<p align="center">
<h3>Step 1 - Download Windows Image</h3>
<p>Why do we have to download a windows image? What is it even? </p>
<p>A Windows image, in simple terms, is like a snapshot or a picture of the Windows operating system and the programs installed on it at a specific point in time.  </p>
It's a complete package that contains all the files and settings needed to set up or restore a Windows computer to a particular state.
<br/>
<br/>
We want to use this windows so we can install it in VirtualBox which is a virtual machine. 
<br/>
<br/>
Virtual machines if configured correctly are like another computer within our computer and wont affect the host machine.
<br/>
<br/>
We need to download a windows image from this URL:
<br/>
https://www.microsoft.com/en-us/software-download/windows10




<br></br>
<h3>Step 2 - Download and Install Windows ISO image on VirtualBox</h3>
First download VirtualBox
<br />
https://www.virtualbox.org/
<br/>
<br/>
After downloading the program, go through the installation process.
<br/>
<br/>
Add your VM name, add folder and ISO image.
<br/>
<br/>
Check --> Unattended Guest OS Install Setup.
<br/>
Complete Username and Password.
<br/>
<br/>
Add Hostname and Domain Name
<br/>
<p>
 Click --> Next --> Choose your hardware, base memory, processors.
</p>
<p>Click --> Next --> Choose your virtual hard disk.</p>
Click --> Next --> Install the computer.
<br/>
<br/>
Voila! The installation is complete.
<br/>
<br/>
Add guest additions because we can change screen resolution for our vm.
<br/>
<br/>
In VirtualBox:
<br/>
Devices > Upgrade Guest Additions
<br/>

<img src="1" height="80%" width="80%" alt=""/>
<br />
<br />
Now we are ready to start the project.
<br/>
<img src="2" height="80%" width="80%" alt=""/>
<br />
<br />




<h3>Step 3 - Configure Initial Windows VM Setup</h3>
<img src="https://i.imgur.com/62TgaWL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select the disk:  <br/>
<img src="https://i.imgur.com/tcTyMUE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Enter the number of passes: <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Confirm your selection:  <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />



<h3>Step 4 - Install Tenable Nessus </h3>
<img src="https://i.imgur.com/62TgaWL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select the disk:  <br/>
<img src="https://i.imgur.com/tcTyMUE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Enter the number of passes: <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />



<h3>Step 5 - Configure Nessus for Scanning </h3>
<img src="https://i.imgur.com/62TgaWL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select the disk:  <br/>
<img src="https://i.imgur.com/tcTyMUE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Enter the number of passes: <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />



<h3>Step 6 - Our First Nessus Initial Scan (without Credentials) </h3>
<img src="https://i.imgur.com/62TgaWL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select the disk:  <br/>
<img src="https://i.imgur.com/tcTyMUE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Enter the number of passes: <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />




<h3>Step 7 - Configuration of Credential Scan </h3>
<img src="https://i.imgur.com/62TgaWL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select the disk:  <br/>
<img src="https://i.imgur.com/tcTyMUE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Enter the number of passes: <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />



<h3>Step 8 - Nessus Credential Scan </h3>
<img src="https://i.imgur.com/62TgaWL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select the disk:  <br/>
<img src="https://i.imgur.com/tcTyMUE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Enter the number of passes: <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />



<h3>Step 9 - Installation of Vulnerable Software </h3>
<img src="https://i.imgur.com/62TgaWL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select the disk:  <br/>
<img src="https://i.imgur.com/tcTyMUE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Enter the number of passes: <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />



<h3>Step 10 - Advanced Nessus Scanning for Vulnerable Software </h3>
<img src="https://i.imgur.com/62TgaWL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select the disk:  <br/>
<img src="https://i.imgur.com/tcTyMUE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Enter the number of passes: <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />



<h3>Step 11 - Remediation of Vulnerabilities </h3>
<img src="https://i.imgur.com/62TgaWL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select the disk:  <br/>
<img src="https://i.imgur.com/tcTyMUE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Enter the number of passes: <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />



<h3>Step 12 - Conclusion and Final Scan Check </h3>
<img src="https://i.imgur.com/62TgaWL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Run the scan again to check for any vulnerabilities:  <br/>
<img src="https://i.imgur.com/tcTyMUE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Enter the number of passes: <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
