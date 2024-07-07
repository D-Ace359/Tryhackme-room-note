##### Windows Fundamentals 1
###### The File System
The file system used in modern versions of Windows is the <font color="#00b050">New Technology File System</font> or simply NTFS.

Before NTFS, there was FAT16/FAT32 (File Allocation Table) and  (High Performance File System).

You still see FAT partitions in use today. For example, you typically see FAT partitions in USB devices, MicroSD cards, etc. but traditionally not on personal Windows computers/laptops or Windows servers.

NTFS is known as a journaling file system. In case of a failure, the file system can automatically repair the folders/files on disk using information stored in a log file. This function is not possible with FAT.

NTFS addresses many of the limitations of the previous file systems; such as:
• Supports files larger than 4GB
• Set specific permissions on folders and files
• Folder and file compression
• Encryption (Encryption File System or EFS)

On NTFS volumes, you can set permissions that grant or deny access to files and folders.
The permissions are:
• Full control
• Modify
• Read & Execute
• List folder contents
• Read
• Write

###### Alternate Data Streams (ADS)
Another feature of NTFS is Alternate Data Streams (ADS).
**From a security perspective, malware writers have used ADS to hide data.**

###### Environment Variable
Per Microsoft, "Environment variables store information about the operating system environment. This information
includes details such as the operating system path, the number of processors used by the operating system, and the
location of temporary folders"

###### System32
**The System32 folder holds the important files that are critical for the operating system.**

###### User Account Control (UAC)
What is UAC?
-> User Account Control (UAC) is a Windows security feature designed to protect the operating system from unauthorized changes.

##### Windows Fundamentals 2:
###### Windows Command
A  command to retrieve the help manual in windows is `/?`.
To clear the command prompt screen, the command is `cls`.
The command `hostname` will output the computer name.
The command `whoami` will output the name of the logged-in user.
A command used often is `ipconfig`. This command will show the network address settings for the computer.
The next command is `netstat`. Per the help manual, this command will display protocol statistics and current TCP/IP network connections.

For the ipconfig command, how do you show detailed information?
-> `ipconfig /all`

###### Windows Registry
The Windows Registry (per Microsoft) is a central hierarchical database used to store information necessary to configure the system for one or more users, applications, and hardware devices.

The registry contains information that Windows continually references during operation, such as:

- Profiles for each user
- Applications installed on the computer and the types of documents that each can create
- Property sheet settings for folders and application icons
- What hardware exists on the system
- The ports that are being used.

**Warning**: The registry is for advanced computer users. Making changes to the registry can affect normal computer operations.

##### Windows Fundamentals 3:
###### Firewall
What is a firewall?

Per Microsoft, "Traffic flows into and out of devices via what we call ports. A firewall is what controls what is - and more importantly isn't - allowed to pass through those ports. You can think of it like a security guard standing at the door, checking the ID of everything that tries to enter or exit".

What is the difference between the 3 (Domain, Private, and Public)?

Per Microsoft, "Windows Firewall offers three firewall profiles: domain, private and public".

- Domain - The domain profile applies to networks where the host system can authenticate to a domain controller. 
- Private - The private profile is a user-assigned profile and is used to designate private or home networks.
- Public - The default profile is the public profile, used to designate public networks such as Wi-Fi hotspots at coffee shops, airports, and other locations

Configuring the Windows Defender Firewall is for advanced Windows users. Refer to the following Microsoft documentation on best practices [here](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/best-practices-configuring).

###### Microsoft Defender SmartScreen
the Microsoft Defender SmartScreen.
Per Microsoft, "Microsoft Defender SmartScreen protects against phishing or malware websites and applications, and the downloading of potentially malicious files".

###### Trusted Platform Module
What is the Trusted Platform Module (TPM)?  

Per Microsoft, "Trusted Platform Module (TPM) technology is designed to provide hardware-based, security-related functions. A TPM chip is a secure crypto-processor that is designed to carry out cryptographic operations. The chip includes multiple physical security mechanisms to make it tamper-resistant, and malicious software is unable to tamper with the security functions of the TPM".

###### BitLocker
What is BitLocker?

Per Microsoft, "BitLocker Drive Encryption is a data protection feature that integrates with the operating system and addresses the threats of data theft or exposure from lost, stolen, or inappropriately decommissioned computers".

On devices with TPM installed, BitLocker offers the best protection.

Per Microsoft, "BitLocker provides the most protection when used with a Trusted Platform Module (TPM) version 1.2 or later. The TPM is a hardware component installed in many newer computers by the computer manufacturers. It works with BitLocker to help protect user data and to ensure that a computer has not been tampered with while the system was offline".

###### Volume Shadow Copy Service
the Volume Shadow Copy Service (VSS)

Per [Microsoft](https://docs.microsoft.com/en-us/windows-server/storage/file-server/volume-shadow-copy-service), the Volume Shadow Copy Service (VSS) coordinates the required actions to create a consistent shadow copy (also known as a snapshot or a point-in-time copy) of the data that is to be backed up. 

Volume Shadow Copies are stored on the System Volume Information folder on each drive that has protection enabled.  

If VSS is enabled (System Protection turned on), you can perform the following tasks from within advanced system settings. 

- Create a restore point
- Perform system restore
- Configure restore settings
- Delete restore points

**From a security perspective, malware writers know of this Windows feature and write code in their malware to look for these files and delete them.** Doing so makes it impossible to recover from a ransomware attack unless you have an offline/off-site backup.
