
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
<p>Add Hostname and Domain Name</p>
<a href="https://ibb.co/KwrZLwr"><img src="https://i.ibb.co/vYj5QYj/1.png" alt="1" border="0" /></a>
<br/>

<p>Click --> Next --> Choose your hardware, base memory, processors.
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
<br/>
<a href="https://ibb.co/M75HdHK"><img src="https://i.ibb.co/6FJSQSG/2.png" alt="2" border="0" /></a>
<br />
<br />
Now that everything is installed, we are ready to start the project.
<br/>
<a href="https://ibb.co/J7bN0M4"><img src="https://i.ibb.co/gTXGHBp/3.png" alt="3" border="0" /></a>
<br />
<br />




<h3>Step 3 - Configure Initial Windows VM Setup</h3>
<p>Before we begin scanning with Nessus, we actually need to make it more vulnerable!</p>
<p>Say what?!</p>
<br />
<p>We want to actively seek to remediate these vulnerabilities.</p>
<br />
<p>A few things we must do are:</p>
<p>1) Turn off security updates</p>
<p>2) Turn off the firewall</p>
<br />
<p>This is very important to do as Nessus can accurately identify any vulnerabilities or
weaknesses so we can improve our VM security.
</p>
<br />
Go to:
<p>Start > Settings > Update & Security > Pause Update for 7 days > Advance Options > Change to later date</p>
<a href="https://ibb.co/qDsKNYN"><img src="https://i.ibb.co/rQ6Yx2x/4.png" alt="4" border="0" /></a>
<br />
<br />
<p>Go back to:</p>
<p>Update & Security > View update History > Uninstall updates</p>
<a href="https://ibb.co/r3BVjwT"><img src="https://i.ibb.co/HCcjSH1/5.png" alt="5" border="0" /></a>
<br />
<p>Uninstall updates</p>
<a href="https://ibb.co/RyXkbMS"><img src="https://i.ibb.co/rsBR0Lt/6.png" alt="6" border="0" /></a>
<br/>
<p>You can uninstall updates this way to:</p>
<p>Control panel > Programs > Programs and Features > Installed Updates</p>
<a href="https://ibb.co/6YNvgzp"><img src="https://i.ibb.co/5T2YBmz/7.png" alt="7" border="0" /></a>
<br/>
<p>Delete all Installed updates and restart the system.</p>
<a href="https://ibb.co/kKRRf4H"><img src="https://i.ibb.co/7vww5nY/8.png" alt="8" border="0" /></a>
<br/>
<br/>
Type: wf.msc
<br/>
<p>Next we need to turn off all Windows Firewall settings. This is because Nessus won't be able to reach its destination.</p>
Do the following:
<p>Go to Start > Windows Defender Firewall > Advanced settings > Windows Defender Firewall Properties  > Domain Profile > Firewall state > Off > Apply</p>
<p>Go to Start > Windows Defender Firewall > Advanced settings > Windows Defender Firewall Properties  > Private Profile > Firewall state > Off > Apply</p>
<p>Go to Start > Windows Defender Firewall > Advanced settings > Windows Defender Firewall Properties  > Public Profile > Firewall state > Off > Apply</p>
<p>Restart System.</p>
<a href="https://ibb.co/FJ8YHJ9"><img src="https://i.ibb.co/3WSFRWw/9.png" alt="9" border="0" /></a>
<br/>
<a href="https://ibb.co/0CNm4FG"><img src="https://i.ibb.co/6Hhr91W/10.png" alt="10" border="0" /></a>
<br/>
<a href="https://ibb.co/ryj3SCN"><img src="https://i.ibb.co/cTBwHGV/11.png" alt="11" border="0" /></a>
<br/>
<p>Last step we have to ensure that the VM is on the same network as the Nessus machine that will perform the scan.</p>
<p>In VirtualBox click Devices > Network > Network Settings > Bridged Adapter </p>
<p>Why a bridged adapter?</p>
<p>With bridged networking, the virtual machine has direct access to an external Ethernet network.</p>
<p>The virtual machine must have its own IP address on the external network.</p>
<p>If your host system is on a network and you have a separate IP address for your virtual machine (or can get an IP address from a DHCP server), select this setting. </p>
<p>Other computers on the network can communicate directly with the virtual machine.
</p>
<br/>
<a href="https://imgbb.com/"><img src="https://i.ibb.co/5YQ7p2T/12.png" alt="12" border="0" /></a>
<br/>
<p>To confirm we are on the same network, we can try a simple ping test.</p>
<p>Open a command prompt application or type cmd in the search box and run the command prompt as administrator.</p>
<p>Type ipconfig --> IP address --> 192.168.0.105</p>
<p>This will present you with a configuration of your network adapter, such as IP addresses of our VM, subnet mask, default gateway.</p>
<p>What we are going to do now is ping our VM IP address from our local machine to see that we can connect to our VM from our local machine.</p>
<p>Using Windows Powershell as Administrator:</p>
<p>Type ping 192.168.0.105 (or your VM IP address)</p>
<p>If we get a reply back that means the connection is good.</p>
<br/>
<a href="https://ibb.co/348nntQ"><img src="https://i.ibb.co/gmXxxsh/13.png" alt="13" border="0" /></a>


<br></br>
<h3>Step 4 - Install Tenable Nessus </h3>
<p>Now that our Windows machine is setup, we are ready to download and install Nessus a powerful network vulnerability scanner.</p>
<p>Go to this website link to download the program. www.tenable.com/products/nessus/nessus-essentials</p>
<br/>
Fill out the registration form and enter your email address. Click the get started button.
<br/>
<p>Get your activation code in your email. </p>
<p>Choose the appropriate version and plaftform, whether it is Mac, Linux or Windows. For me, I have chosen Windows 64 bit.</p>
<p>Click > Download and then accept the license agreement.</p>
<br/>
<a href="https://ibb.co/ZTJHTrJ"><img src="https://i.ibb.co/bd3HdV3/14.png" alt="14" border="0" /></a>
<br />
<br />

<a href="https://imgbb.com/"><img src="https://i.ibb.co/Kyxq4mj/15.png" alt="15" border="0" /></a>
<br />
<br />
<p>Once downloaded execute and open executable file. The Nessus file will be downloaded onto your local host.</p>
<br/>
Confirm OK > Click Next
<p>Set your default destination</p>
<br/>
<br />
<a href="https://imgbb.com/"><img src="https://i.ibb.co/mNQP15G/16.png" alt="16" border="0" /></a>
<br />
<br />
<a href="https://imgbb.com/"><img src="https://i.ibb.co/kcLFJ9w/17.png" alt="17" border="0" /></a>
<br />
<br />
<a href="https://imgbb.com/"><img src="https://i.ibb.co/0V0HtNd/18.png" alt="18" border="0" /></a>
<br />
<br />
<a href="https://imgbb.com/"><img src="https://i.ibb.co/SdCLZ6q/19.png" alt="19" border="0" /></a>
<br />
<br />
<a href="https://ibb.co/LhPrL9K"><img src="https://i.ibb.co/zH5FyPd/20.png" alt="20" border="0" /></a>
<br />
<br />
<a href="https://imgbb.com/"><img src="https://i.ibb.co/k2HrbMQ/21.png" alt="21" border="0" /></a>
<br />
<br />
<a href="https://imgbb.com/"><img src="https://i.ibb.co/mGFWHDL/22.png" alt="22" border="0" /></a>
<br />
<br />
<a href="https://imgbb.com/"><img src="https://i.ibb.co/R6hMvwJ/23.png" alt="23" border="0" /></a>
<br />
<br />
<a href="https://imgbb.com/"><img src="https://i.ibb.co/tZS0hPC/24.png" alt="24" border="0" /></a>
<br />
<br />
<a href="https://imgbb.com/"><img src="https://i.ibb.co/dPPn1qJ/25.png" alt="25" border="0" /></a>
<br />
<br />
<a href="https://imgbb.com/"><img src="https://i.ibb.co/6RBHC8R/26.png" alt="26" border="0" /></a>
<br />
<br />
<a href="https://ibb.co/MSHNh5P"><img src="https://i.ibb.co/PjyCYz1/27.png" alt="27" border="0" /></a>
<br />
<br />


<br></br>
<h3>Step 5 - Configure Nessus for Scanning </h3>
<br/>
<br />
<a href="https://ibb.co/6B6ftf0"><img src="https://i.ibb.co/L542g2d/28.png" alt="28" border="0" /></a>
<br />
<br/>
<br />
<a href="https://ibb.co/xLP1btR"><img src="https://i.ibb.co/RbZ3KkV/29.png" alt="29" border="0" /></a>
<br />
<br />
<br/>
<br />
<a href="https://ibb.co/wCnPLQ8"><img src="https://i.ibb.co/ft3ySNZ/30.png" alt="30" border="0" /></a>
<br />
<br />
<br/>
<br />
<a href="https://ibb.co/3SbhHd2"><img src="https://i.ibb.co/F817t32/31.png" alt="31" border="0" /></a>
<br />
<br />
<br/>
<br />
<a href="https://ibb.co/KmGZC4T"><img src="https://i.ibb.co/4JfyBvh/32.png" alt="32" border="0" /></a>
<br />
<br />
<br/>
<br />
<a href="https://ibb.co/gyFW8kB"><img src="https://i.ibb.co/NxnNqcH/33.png" alt="33" border="0" /></a>
<br />
<br />
<br/>
<br />
<a href="https://ibb.co/3fqhyLV"><img src="https://i.ibb.co/ZHPT6kv/34.png" alt="34" border="0" /></a>
<br />
<br />
<br/>
<br />
<a href="https://ibb.co/CK94qHg"><img src="https://i.ibb.co/SwmH23b/35.png" alt="35" border="0" /></a>
<br />
<br />
<br/>
<br />
<a href="https://ibb.co/QdM9WVX"><img src="https://i.ibb.co/PQgx2yt/36.png" alt="36" border="0" /></a>
<br />
<br />
<br/>
<br />
<a href="https://ibb.co/KWwrH1D"><img src="https://i.ibb.co/njCLSWB/37.png" alt="37" border="0" /></a>
<br />
<br />
<br/>
<br />
<a href="https://ibb.co/bHKJSxN"><img src="https://i.ibb.co/LQZ5LM9/38.png" alt="38" border="0" /></a>
<br />
<br />


<br></br>
<h3>Step 6 - Our First Nessus Initial Scan (without Credentials) </h3>
<br/>
<br />
<a href="https://ibb.co/0tjHYHm"><img src="https://i.ibb.co/YZ7HfHP/39.png" alt="39" border="0" /></a>
<br />
<br />
<br/>
<br />
<a href="https://ibb.co/FqXKSX4"><img src="https://i.ibb.co/dJtrdt4/40.png" alt="40" border="0" /></a>
<br />
<br />
<br/>
<br />
<a href="https://ibb.co/hHPqB1y"><img src="https://i.ibb.co/Y8zrcT3/41.png" alt="41" border="0" /></a>
<br />
<br />



<br></br>
<h3>Step 7 - Configuration of Credential Scan </h3>
<br/>
<br />
<a href="https://ibb.co/cNt6xwk"><img src="https://i.ibb.co/Jz2vCqm/42.png" alt="42" border="0" /></a>
<br />
<br />
<br/>
<br />
<a href="https://ibb.co/rpLjN5B"><img src="https://i.ibb.co/5jz0wsQ/43.png" alt="43" border="0" /></a>
<br />
<br />
<br/>
<br />
<a href="https://ibb.co/3Fb2zrv"><img src="https://i.ibb.co/Lgym5kr/44.png" alt="44" border="0" /></a>
<br />
<br /><br/>
<br />
<a href="https://imgbb.com/"><img src="https://i.ibb.co/Bccnbyz/45.png" alt="45" border="0" /></a>
<br />
<br /><br/>
<br />
<a href="https://ibb.co/rZFh8b6"><img src="https://i.ibb.co/wKBqGJW/46.png" alt="46" border="0" /></a>
<br />
<br /><br/>
<br />
<a href="https://ibb.co/vzxx0NL"><img src="https://i.ibb.co/LpzzVT9/47.png" alt="47" border="0" /></a>
<br />
<br /><br/>
<br />
<a href="https://ibb.co/z4W5nRb"><img src="https://i.ibb.co/S3Dxsn0/48.png" alt="48" border="0" /></a>
<br />
<br /><br/>
<br />
<a href="https://ibb.co/CP08jBT"><img src="https://i.ibb.co/dmKMNBz/49.png" alt="49" border="0" /></a>
<br />
<br />
<br />
<a href="https://ibb.co/xsLQ5f7"><img src="https://i.ibb.co/JdtPkys/50.png" alt="50" border="0" /></a>
<br />
<br />



<br></br>
<h3>Step 8 - Nessus Credential Scan </h3>
<br/>
<br />
<br />
<a href="https://ibb.co/HqhVRzJ"><img src="https://i.ibb.co/rHdmq6W/51.png" alt="51" border="0" /></a>
<br />
<br />
<br />
<br />
<a href="https://ibb.co/7jT3K1R"><img src="https://i.ibb.co/n6VXjLn/52.png" alt="52" border="0" /></a>
<br />
<br />
<br />
<br />
<a href="https://ibb.co/LR3MgW2"><img src="https://i.ibb.co/fFsbN5P/53.png" alt="53" border="0" /></a>
<br />
<br />


<br></br>
<h3>Step 9 - Installation of Vulnerable Software </h3>
<br/>
<br />
<br />
<a href="https://imgbb.com/"><img src="https://i.ibb.co/Jx60P2j/54.png" alt="54" border="0" /></a>
<br />
<br />
<br />
<br />
<a href="https://imgbb.com/"><img src="https://i.ibb.co/5KGrsXm/55.png" alt="55" border="0" /></a>
<br />
<br />
<br />
<br />
<a href="https://ibb.co/HdXC9m3"><img src="https://i.ibb.co/vYDhM2R/56.png" alt="56" border="0" /></a>
<br />
<br />
<br />
<br />
<br />
<a href="https://ibb.co/jZDNXb5"><img src="https://i.ibb.co/7NKfmjz/57.png" alt="57" border="0" /></a>
<br />
<br />
<br />
<br />
<br />
<a href="https://imgbb.com/"><img src="https://i.ibb.co/k5XMqv6/58.png" alt="58" border="0" /></a>
<br />
<br />
<br />
<br />
<br />
<a href="https://imgbb.com/"><img src="https://i.ibb.co/txTNWK5/59.png" alt="59" border="0" /></a>
<br />
<br />


<br></br>
<h3>Step 10 - Advanced Nessus Scanning for Vulnerable Software </h3>
<br />
<br />
<a href="https://ibb.co/sj8VQnP"><img src="https://i.ibb.co/SNF30bx/60.png" alt="60" border="0" /></a>
<br />
<br />
<br />
<br />
<a href="https://ibb.co/ChBsMnC"><img src="https://i.ibb.co/t8BPxbj/61.png" alt="61" border="0" /></a>
<br />
<br />
<br />
<br />
<a href="https://ibb.co/vZPnV3T"><img src="https://i.ibb.co/Ch7GmbY/62.png" alt="62" border="0" /></a>
<br />
<br />
<br />
<br />
<a href="https://ibb.co/Lr3dnLy"><img src="https://i.ibb.co/68k0g3S/63.png" alt="63" border="0" /></a>
<br />
<br />
<br />
<br />
<a href="https://ibb.co/ZKKjrRr"><img src="https://i.ibb.co/1KKgNYN/64.png" alt="64" border="0" /></a>
<br />
<br />




<br></br>
<h3>Step 11 - Remediation of Vulnerabilities </h3>
<br />
<br />
<a href="https://ibb.co/Wnj4vR6"><img src="https://i.ibb.co/F6CL4dK/65.png" alt="65" border="0" /></a>
<br />
<br />
<br />
<br />
<a href="https://imgbb.com/"><img src="https://i.ibb.co/sb7c76M/66.png" alt="66" border="0" /></a>
<br />
<br />
<br />
<br />
<a href="https://imgbb.com/"><img src="https://i.ibb.co/DR4qC83/67.png" alt="67" border="0" /></a>
<br />
<br />
<br />
<br />
<a href="https://ibb.co/Sy6ZLnc"><img src="https://i.ibb.co/MSgJXVf/68.png" alt="68" border="0" /></a>
<br />
<br />
<br />
<br />
<a href="https://ibb.co/HqbnZRj"><img src="https://i.ibb.co/VTz26bs/69.png" alt="69" border="0" /></a>
<br />
<br />
<br />
<br />
<a href="https://ibb.co/BgW72YN"><img src="https://i.ibb.co/THjnMNL/70.png" alt="70" border="0" /></a>
<br />
<br />
<br />
<br />
<a href="https://ibb.co/NVjxGKT"><img src="https://i.ibb.co/tmsB1DL/71.png" alt="71" border="0" /></a>
<br />
<br />




<br></br>
<h3>Step 12 - Conclusion and Final Scan Check </h3>
<br />
<br />
<a href="https://ibb.co/hXSFNwM"><img src="https://i.ibb.co/TKsMGdT/72.png" alt="72" border="0" /></a>
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
