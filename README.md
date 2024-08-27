# KAPE

![image](https://github.com/user-attachments/assets/af37aaf0-8166-42b6-98b8-cdbc81ce33a4)


## Personal Project Report: Forensic Investigation Using KAPE

### Scenario

Organization X has an Acceptable Use Policy (AUP) for their Portable Devices, including Laptops. This policy forbids users from connecting removable or network drives, installing software from unknown locations, and connecting to unknown networks. It appears that one of the users has violated this policy. My task was to help Organization X determine if the user violated the AUP on their device. The user’s machine was provided as a Virtual Machine (VM).

Using KAPE, a powerful forensic tool, I was required to analyze the VM and answer specific forensic questions to determine whether the AUP was breached. This investigation leveraged the skills gained from TryHackMe’s KAPE room, as well as the Windows Forensics 1 and Windows Forensics 2 rooms.
Project Steps and Answers

#### 7.1 Two USB Mass Storage devices were attached to this Virtual Machine. One had a Serial Number 0123456789ABCDE. What is the Serial Number of the other USB Device?

To answer this question:

I set the options in GKAPE similar to those in Task 5 and executed it.
After processing, I navigated to the Registry folder within the KAPE output directory.
I then accessed the subfolder beneath it and opened the USBSTOR file using EZViewer.
The file revealed two registry keys, and the Serial Number of the other USB Device was identified.

![image](https://github.com/user-attachments/assets/ac6346fa-3cd1-47b2-8c7a-541eccac635f)

![image](https://github.com/user-attachments/assets/fdd83c5d-78bc-4c66-afae-7d1ee4419319)

    Answer: 1C6F654E59A3B0C179D366AE

#### 7.2 7zip, Google Chrome, and Mozilla Firefox were installed from a Network drive location on the Virtual Machine. What was the drive letter and path of the directory from where these software were installed?

To answer this question:

  I navigated to the Registry folder and accessed the subfolder beneath it.
  Using EZViewer, I opened the RecentApps file.
  he file showed the installation paths, allowing me to identify the drive letter and directory.

![image](https://github.com/user-attachments/assets/a88c69d2-5967-4792-8de0-75d4764f912c)

    Answer: Z:\setups

#### 7.3 What is the execution date and time of CHROMESETUP.EXE in MM/DD/YYYY HH
?

To answer this question:

I stayed in the Registry subfolder and continued analyzing the RecentApps file with EZViewer.
The execution date and time of CHROMESETUP.EXE were found within this file.

![image](https://github.com/user-attachments/assets/b0e325f9-e0bc-4d5c-8bef-fffde4db2f8e)

    Answer: 11/25/2021 3:33

#### 7.4 What search query was run on the system?

To answer this question:

I used the hint provided, which led me to open the “WordWheelQuery” file within the same registry subfolder.
This file contained the search query that was executed on the system.

![image](https://github.com/user-attachments/assets/b5c7905e-f63e-441d-a3d8-d3a905b4fdab)

    Answer: RunWallpaperSetup.cmd

#### 7.5 When was the network named Network 3 first connected to?

To answer this question:

I remained in the same registry subfolder and opened the “KnownNetworks” file using EZViewer.
This file listed the first connection date and time for Network 3.

![image](https://github.com/user-attachments/assets/47b0ba04-3ac3-4916-835e-90bc7880f77a)

    Answer: 11/30/2021 15:44

#### 7.6 KAPE was copied from a removable drive. Can you find out what was the drive letter of the drive where KAPE was copied from?

To answer this question:

I reviewed the AutomaticDestinations file within the KAPE output directory.
The drive letter from which KAPE was copied was identified within this file.

![image](https://github.com/user-attachments/assets/070cb005-6361-4ecd-b52c-1aa1c7834e18)

    Answer: E:

#### Conclusion

This project involved an in-depth analysis using KAPE to investigate potential violations of an Acceptable Use Policy. The investigation confirmed several breaches, including unauthorized USB device connections, software installations from a network drive, and connections to an unknown network. The use of KAPE proved to be instrumental in uncovering these violations, demonstrating its power and flexibility in forensic investigations.
Experience Gained

Throughout this project, I gained valuable hands-on experience with KAPE, reinforcing my understanding of Windows forensics. I learned how to navigate and interpret various forensic artifacts, such as registry files and network connections. This project also highlighted the importance of methodical analysis and the use of specialized tools to uncover critical evidence.

#### Benefits:

Enhanced Forensic Skills: This project significantly enhanced my forensic investigation skills, particularly in using KAPE for artifact collection and analysis.
Improved Problem-Solving: I honed my problem-solving abilities by systematically addressing each question and exploring the VM's forensic data.
    
#### Practical Application:

The project provided practical experience that will be beneficial for future forensic investigations, especially in scenarios involving policy violations and unauthorized activities.

This project not only solidified my knowledge of Windows forensics but also provided a comprehensive understanding of how to use KAPE effectively in real-world scenarios.


