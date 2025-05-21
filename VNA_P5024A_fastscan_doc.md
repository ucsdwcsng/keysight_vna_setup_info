### This document explains in detail the steps involved in setting up the P5024A VNA and getting it to run at 10kHz sampling rate for real time wired capture of Sparamerters
-First install all necessary libraries:
- Keysight IOSL: Please use the 2023 Version, Update 1: (https://www.keysight.com/us/en/lib/software-detail/computer-software/io-libraries-suite-downloads-2175637.html), this will download IVI drivers as well 
- Keysight VNA firmware  https://urldefense.com/v3/__https://www.keysight.com/us/en/lib/software-detail/instrument-firmware-software/pxieusb-vector-network-analyzer-firmware-update-64-bit-3027357.html__;!!Mih3wA!CAXSMjTl3h5kqmVd6VCo4DTPptPYf2ypJ9FtErwwzqqgd0TG2YHRy4ZUfHSJNhHRSC0d2QNc7r1np3F6Nw$

## Mandatory Step to follow before enabling fast-sample:
- Once the VNA is recognized by the localhost (device shows up as shown below in Connection Expert)
 Connection Expert![image](https://github.com/user-attachments/assets/573ab634-d81a-4f68-81a4-65582708ab34)
- Now using the "Soft Panel" button, launch the VNA software for the Keysight VNA listed in the expert.
   This is how the Vector Network Analyzer looks: ![image](https://github.com/user-attachments/assets/0b9f63ca-263a-4241-8cea-6844e7f20fad)
- Navigate to Remote Interface using the steps shown below:
  Remote Interface Setup: ![image](https://github.com/user-attachments/assets/29484b1b-cb88-431d-926d-2383518dd29f)
- Make sure hi-slip is enabled and the LAN sockets are ENABLED. Socket number does not matter
  Remote Interface settings ![image](https://github.com/user-attachments/assets/399e7d08-e075-456e-9f7c-2a38e8c44dfb)
- For the LAN Instrument Setup, add a new device using "+Add": ![image](https://github.com/user-attachments/assets/28c715a7-57d2-4c9b-8653-c818965917f4)
- The LAN instrument setup shows up like this: ![image](https://github.com/user-attachments/assets/225bd5b5-b89b-435b-956a-1227bbe531e8)
- For Hostname: just enter "localhost".
- Ensure "Allow *IDN Query" is ENABLED.
- Make sure to click on "Test Visa Address" and the response should be the ID of the LAn device you are connecting to.
- Your LAN device is now fully setup and functional to be used to communicate and send/receive messages with localhost computer.
- Now ensure that your device is actually talking to your computer:
- Open Keysight Interactive IO, here you can test out any SCPI commands needed to communicate with the VNA.
- Interactive IO setup, this is a CLI terminal ![image](https://github.com/user-attachments/assets/11d0dc12-428d-4a95-9275-f3766075d704).
- Type *IDN? in the Command Line, and click on Send & Read--This should yield the response as shwon below:
- Returns the Instrument name:  ![image](https://github.com/user-attachments/assets/ba0b25cb-c55d-4342-bdce-44dcb0aba367)

## Calibratiing the VNA to needed spec and frequency range.
- The CalState file that is generated through the E-Cal process is stored at the following location:
- C:\ProgramData\Keysight\Network Analyzer\data1\UserCalSets
- Load it appropriately

## Debugging connection issues:
- https://docs.keysight.com/kkbopen/uninstall-and-deep-clean-a-malfunctioning-install-of-io-libraries-suite-682429352.html

## Create a new ticket:
- When you ask a customer to uninstall the prerequisites, the correct way to uninstall is through Windows Add or Remove programs by removing the 6 programs listed below:
IVI Shared Components 3.0.2828.0
IVI.NET Shared Components 2.0.0
MSVC++ 2015-2022 64-bit 14.40.xxxxx
MSVC++ 2015-2022 32-bit 14.40.xxxxx
VISA Shared Components 7.2.0004
VISA.NET Shared Components 7.2.0
 
There is a new release of IOLS today, 2024 U2, that is supposed to resolve the Streamline VNA issues: IO Libraries Suite Downloads | Keysight
 
What Is the Best Way to Obtain Technical Support from Keysight?
To open a new case or if you have any further questions, please reach out to us through our portal (preferred), phone, or email: What Is the Best Way to Get Technical Support from Keysight?
Contact Keysight Technical Support
Contact Keysight Technical Support 
- https://www.keysight.com/us/en/lib/resources/miscellaneous/contact-keysightcare-support-3011035.html?jmpid=zzfindkeysightcare.contactus





  






