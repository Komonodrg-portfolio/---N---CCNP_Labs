### [Cybersecurity](https://github.com/Komonodrg-portfolio/Cybersecurity) | [Networking](https://github.com/Komonodrg-portfolio/Networking) | [Data Science (AI)](https://github.com/Komonodrg-portfolio/AI) | [Media Creation](https://github.com/Komonodrg-portfolio/MediaCreation) | [Mission](https://github.com/Komonodrg-portfolio/Mission/)

---
---

# 🌐 CCNP Labs (Encore 350-401)

This repo project demonstrates my self study prep of CCNP comptetencies using **EVE-NG (Emulated Virtual Environment Next Generation)** in preperation for certification acquisition. It showcases that not alot of financial resourcs are needed in order to pursue your education goals in becoming a competent CCNP level Network Engineer.   With a labtop of 16GB  (recommended) of ram, this platform allows training from anywhere in the world.

---

## 📌 Goals
To illustrate a cost effective platform to  allow for the practice and self study in Network Engineering via providing the ability to:

- Design and emulate a complex network topology
- Practice configuration of Cisco routers, Layer 2/3 switches, and firewalls
- Test routing protocols (OSPF, EIGRP, BGP)
- Implement VLANs and inter-VLAN routing
- Simulate internet connectivity with NAT/PAT
- Prepare for CCNA/CCNP certification as well as network automation

---

## 🧰 Tools & Technologies

| Tool       | Purpose                              |
|------------|--------------------------------------|
| EVE-NG     | Network Emulation Platform           |
| Cisco IOU / Dynamips | Router & Switch Emulation         |
| SD-WAN    | Overlay network implementation over core underlay routing          |
| Linux  / Windows VMs  | Host Simulation and network automation                     |
| Wireshark  | Packet Capture and Analysis          |

---

---

## 🔧 Webpage Navigation

Rather then creating a individual repo per lab on github, I decided to employ the use of jupyter notebooks for each lab.  You can view individual labs via the folder hierachy on this page:

<img src="images/Page1.png" width="800"/>



### Prerequisites

Please view my [EVE-NG setup tutorial](https://github.com/Komonodrg-portfolio/---N---Home_Lab_Networking) for lab environment setup.  For L3 (Router) and L2 (Switch) files, there are 2 main flavors commonly used:
- IOL (contains less features, but requires less system resources to run allowing more nodes to run successfully)
- vIOS (more feature rich, requiring more system resources to run)

<details>
 <summary><h4>a)  IOL Image Setup</h4></summary>
  <br> 
 
```
Place IOL image files on EVE-NG in folder /opt/unetlab/addons/iol/bin folder location 
  └─ Also place license generation file.py in same folder
  └─ Change execution permission on the file via: sudo chmod +x <filename>
  └─ 1) Copy License information generated
  └─ 2) Paste contents into iourc file you'll create via: nano -c iourc > Ctrl + X > Enter to save

IOL images should now run successfully after starting and able to console into
```
<p float="center">
  <img src="images/IOL1.png" width="325" />
  <img src="images/IOL2.png" width="325" />
  <img src="images/IOL3.png" width="345" />

</details>
<details>
 <summary><h4>b) Download Hypervisor (VMWare)</h4></summary>
  <br> 
  For this lab, we will run EVE-NG as a virtual machine from within a <a href="https://chatgpt.com/share/68cb87a6-3580-800b-a816-6c42bfab1272/">hypervisor</a> (type 2).  Both Linux and Windows versions are free, but require <a href="https://support.broadcom.com/">signing up for a broadcom account</a> first:<br>
  <br>
<p align="center">
 <img src="images/VMWareInstall1.png" alt="Image 1" width="43%" style="margin-right: 10px;"/>
 <img src="images/VMWareInstall2.png" alt="Image 1" width="45%" style="margin-right: 10px;"/>
 <img src="images/VMWareInstall3.png" alt="Image 1" width="45%" style="margin-right: 10px;"/>
 <img src="images/VMWareInstall4.png" alt="Image 1" width="45%" style="margin-right: 10px;"/>
 <img src="images/VMWareInstall5.png" alt="Image 1" width="45%" style="margin-right: 10px;"/>
</p>  
<br>
Once the installation file downlods successfully, proceed with installation of VMWare:</br><br>

</details> 
<details>
 <summary><h4>c) Install VMWare Workstation</h4></summary>
  <br> 
  
**Windows:**  Navigate to where the file downloaded, and double click it to start the installer...

**Linux:** A few extra steps are needed prior in order to get this installation completed:
<br>
Open up **Terminal** to install VMWare:
<br>
<br>

| Step    | Command |
|---------|---------|
| 1) Install required dependencies | `sudo apt install build-essential linux-headers-$(uname -r)` |
| 2) Navigate to download location  | `cd ~/Downloads` |
| 3) List files in Downlaods folder  | `ls` |
| 4) Make installation file executable  | `chmod +x VMWare...bundle` |
| 5) Run installation file  | `sudo ./VMWare...bundle` |
<br>
<p align="left">
 <img src="images/VMWareInstall6.png" alt="Image 1" width="60%" style="margin-right: 10px;"/>
 <br>
 <p align="left">
 <img src="images/VMWareInstall7.png" alt="Image 1" width="60%" style="margin-right: 10px;"/>

 ---

 <p align="center">
 <img src="images/VMWareInstall8.png" alt="Image 1" width="45%" style="margin-right: 10px;"/>
 <img src="images/VMWareInstall9.png" alt="Image 1" width="45%" style="margin-right: 10px;"/>
 <img src="images/VMWareInstall10.png" alt="Image 1" width="45%" style="margin-right: 10px;"/>
 <img src="images/VMWareInstall11.png" alt="Image 1" width="45%" style="margin-right: 10px;"/>
</p>  




  

 
</details> 


### 1. Install EVE-NG VM in VMWare
Follow the [official EVE-NG installation guide](https://www.eve-ng.net/index.php/documentation/) to learn bare-metal setup or continue on to see how to set it up in VMware.<br>
<br>
Whether you are running it on Windows or Linux (Mint), the setup process is pretty much the same:<br>
<br> 
a) Download EVE-NG & Required Components<br>

Navigate to [EVE-NG Download page](https://www.eve-ng.net/index.php/download/) and download both: <br>

- **EVE-NG CE.iso**<br> 
- **Client Side Tools** (Windows/Linux)
  
 <img src="images/EVENGVM1.png" width="400"/><img src="images/EVENGVM1.png" width="400"/><br>
 
b) Create VM (Virtual Machine)<br>

In VMWare, click `file` >  `New Virtual Machine...`  > ...

<img src="images/EVENGVM3.png" width="400"/>  <img src="images/EVENGVM4.png" width="400"/> <br> 

... Click `Browse`, navigate to where the EVE-NG.iso file is downloaded and select it before proceeding to `Next`.<br> 

<img src="images/EVENGVM5.png" width="400"/>  <img src="images/EVENGVM6.png" width="400"/>
<img src="images/EVENGVM7.png" width="400"/>  <img src="images/EVENGVM8.png" width="400"/><br>
<img src="images/EVENGVM9.png" width="400"/>  <img src="images/EVENGVM9a.png" width="400"/><br>
<img src="images/EVENGVM10.png" width="400"/><br>
<br> 

c) Power on EVE-NG VM<br>

Select the EVE-NG instance in VMWare and click `start`, the VM will power up, ask a few setup questions through menus (select default selections through menus until installation completes)<br> 

It will reboot twice during installation, just be patient and you will eventually be met with an IP address to use to login via your PC browser:

<img src="images/EVENGVM11.png" width="400"/> <img src="images/EVENGVM12.png" width="400"/> 

<details>
 <summary><h4><em><b>🛠️  "Troubleshooting..."</b></em></h4></summary>
 <br> 
<em>From within VM Window, there is an error message that neither virualization platforms "Intel VT-x or AMD V were found", as the option when creating the VM was greyed out.  Even after re-ensuring the enabling of Virtualization in the BIOS, I still had the same error:<br>
<br>
 <img src="images/EVENGVMFix1.png" width="400"/> 
 
 Doing a quick ask of [CHATGPT](https://chatgpt.com/share/68d1a482-7b64-8000-a8bc-3f4b402d31bf) provided steps to assist in resolving the issue.<br>
 
 Don't be afraid to lean on the benefits AI provides, as referring to the documentation can make it hard to find a solution to  specific issues you may run into.  After applying recommended fixes:<br>
 <br>
  <img src="images/EVENGVMFix2.png" width="400"/> <img src="images/EVENGVMFix3.png" width="400"/>

 Later in this guide, we will be adding devices to topologies, like this.  Without the fix, I was not able to access the devices for configuration.  Now it presents the option to telnet to the device:<br>
 <br>
 <img src="images/EVENGVMFix4.png" width="400"/>
 
 </em><br>
<br>

</details>




Click in VM window, login (press `ENTER` to get login prompt) and update your EVE-NG VM:  <br>

| Login    | Password |
|---------|---------|
| `root` | `eve`|
| `admin` | `eve`|

To update EVE-NG VM, after logging in, enter command:

```bash
apt update & apt upgrade -y
```

<img src="images/EVENGVM15.png" width="400"/> <img src="images/EVENGVM16.png" width="400"/><br>

d) Install Client Tools<br>

**Windows:** Navigate to the folder where the Windows Client Tools.exe is located, double click it to run it (click `Next` through each component install):

<img src="images/ClientWIN1.png" width="400"/> <img src="images/ClientWIN2.png" width="400"/><br>

**Linux:** The [instructions](https://github.com/SmartFinn/eve-ng-integration) for linux (mint/debian) involve a few more steps:

From **Terminal** enter:

```
wget -qO- https://raw.githubusercontent.com/SmartFinn/eve-ng-integration/master/install.sh | sh
```
-OR-
```
sudo add-apt-repository ppa:smartfinn/eve-ng-integration
sudo apt-get update
sudo apt-get install eve-ng-integration
```
Next, install required dependencies:
```

# Required dependencies
sudo apt install python3 telnet

# Recommended dependencies
sudo apt install wireshark ssh-askpass vinagre

# Optional dependencies (if you need Docker)
sudo apt install docker.io
```

<img src="images/ClientLINUX1.png" width="400"/> <img src="images/ClientLINUX12.png" width="400"/><br>

<img src="images/Dependencies1.png" width="400"/> 



e) Login to EVE-NG webgui<br>


Confirm you are able to access EVE-NG by opening up a web brower (Firefox/Chrome) and typing in the IP Address given by EVE-NG VM:
<p float="center">
  <img src="images/EVENGVM13.png" width="400" />
  <img src="images/EVENGVM14.png" width="400" />

### 2. Import Cisco Images into EVE-NG

a) Setup OS (Operating System) for file transfer between host and VM<br>

In order to be able to use devices (routers/switches) in your lab topologies, their image files must first be added to EVE-NG:

**Windows:** Download and install [WinSCP](https://winscp.net/eng/download.php)

<img src="images/WINSCP1.png" width="400"/> <img src="images/WINSCP2.png" width="400"/><br>

During Setup...Select `Typical Installation` > `Commander Style` > `Install` > `Finish`<br>
Enter in the login information for EVE-NG to connect to your VM from WinSCP, which will allow to transfer files to it.<br>
<br>

**Linux:** Unlike Windows, Linux Mint's default file explorer has the SFTP capability to allow direct communication with EVE-NG by clicking on navigation bar and typing in:<br>

```
sftp://<yourIPAddress>
```

<img src="images/FileTransfer1.png" width="400"/> <img src="images/FileTransfer2.png" width="400"/><br>

In order to allow for two pane look, much like WINSCP or Filezilla (provides ease for drag and drop), from `File Explorer` > click `View` > select `Extra Pane` -OR- press the key  `F3`:

<img src="images/FileTransfer3.png" width="400"/> 

... with access to EVE-NG file system, we are now ready to upload Cisco images.  You can find some practice images in the `ios/` folder in this repo.

Per [instructions from official documentation](https://www.eve-ng.net/index.php/documentation/howtos/howto-add-cisco-vios-from-virl/):

b) Uploading Format<br>

To upload any image (router, switch, firewall, windows, linux, etc) you must navigate to location in EVE-NG file system to upload image files into created folders, each with a particular [folder name prefix](https://www.eve-ng.net/index.php/documentation/qemu-image-namings/).  For this lab, we will focus only the ones specific for our needs for CCNA/CCNP study and lab practice:

 <img src="images/FolderNaming.png" width="800"/> 

c) Upload Cisco Router (L3 & L2) Images:<br>

From WinSCP (Windows) or File Explorer (Linux), navigate to `/opt/unetlab/addons/qemu` path and create 2 folders, naming it "`vios-<YourFileName>`" & "`viosl2-<YourFileName>`", then copy and paste image .qcow2 files into created folders from download location:

<img src="images/FileTransfer4.png" width="400"/> <img src="images/FileTransfer5.png" width="400"/><br>

We must now change the name of the file via the `mv` command and fix permissons to allow EVE-NG to accept and properly run the images.  Though we've managed  EVE-NG cli from VM window in VMWare, lets do it from our **Terminal** this time:

| Step    | Command |
|---------|---------|
| 1) Open Terminal and ssh login into EVE-NG | `ssh root@<EVE-NG VM IP address>` |
| 2) Navigate to `qemu/` folder location  | (see pic for linux cli navigation commands) |

<img src="images/Root1.png" width="400"/> <img src="images/Root2.png" width="400"/><br>

| Step    | Command |
|---------|---------|
| 3) Change name of .qcow2 files in both folders to `virtioa.qcow2` |  -`mv vios-adventerprisek9-m.spa.159-3.m8.qcow2 virtioa.qcow2` <br> -`mv viosl2-adventerprisek9-m.spa.159-3.m8.qcow2 virtioa.qcow2` |
| 4) Fix file permissions  | `/opt/unetlab/wrappers/unl_wrapper -a fixpermissions` |
<br>
<img src="images/Root3.png" width="800"/>
<br>
d) Test functionality<br>
<br>
Login to EVE-NG via Web GUI and create a `new lab` named "Test": <br> 
<br>

<img src="images/Test1.png" width="400"/><img src="images/Test2.png" width="400"/><br>

Hover over the `+` sign > select `Add New Object` > select `Node`... you'll see the options for Cisco Devices are selectable.  Select `Cisco vIOS Router` and press `Enter`.  When router appears on lab, right-click on it > select `Start`, then double click on router to open up device console (select `Open Link` on the popup message):<br>
<br> 

<img src="images/Test3.png" width="400"/> <img src="images/Test4.png" width="400"/>






d) Upload Cisco IOL (IOS on Linux) Images:

From WinSCP (Windows) or File Explorer (Linux), navigate to `/opt/unetlab/addons/iol/bin` path, then copy and paste image files into this location:

<img src="images/FileTransfer6.png" width="400"/> <img src="images/FileTransfer7.png" width="400"/><br>

From EVE-NG cli (command line interface), enter command:

<h2> 🤳 Connect with me:</h2>

[<img align="left" alt="JoshMadakor | YouTube" width="22px" src="https://cdn.jsdelivr.net/npm/simple-icons@v3/icons/youtube.svg" />][youtube]
[<img align="left" alt="JoshMadakor | Tik Tok" width="22px" src="https://cdn.jsdelivr.net/npm/simple-icons@v3/icons/tiktok.svg" />][tiktok]
[<img align="left" alt="JoshMadakor | LinkedIn" width="22px" src="https://cdn.jsdelivr.net/npm/simple-icons@v3/icons/linkedin.svg" />][linkedin]
[<img align="left" alt="JoshMadakor | Instagram" width="22px" src="https://cdn.jsdelivr.net/npm/simple-icons@v3/icons/instagram.svg" />][instagram]

[tiktok]: https://tiktok.com/upcoming...
[youtube]: https://www.youtube.com/@EvenSteveTech
[instagram]: https://www.instagram.com/upcoming...
[linkedin]: https://www.linkedin.com/in/steven-komono-71790197/
