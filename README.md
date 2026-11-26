
# PENETRATION TESTING REPORT

---

## FOOTPRINTING, RECONNAISSANCE & NETWORK SCANNING

---

## WEEK 2 | CYBERSECURITY & ETHICAL HACKING  |  NETWORK WALKS

## Report Information	Details
| | |
|---|---|
| Pentester Name (Cybersecurity Professional) | Rotimi Elijah Ogunbiyi | 
| Program/Batch | B084-NetworkWalks |  
| Date | 25 November 2026 |
| Client/Target | Networkwalks (secured written permission already); My own local LAN Network | 
| Modules Covered | W2-PM2 (GHDB); W2-PM3 (Maltego); W2-PM5 (Network Scanning with Zenmap) | 
| Permission secured from client?	| Yes |
| Phases covered | Phase 1: Maltego; Phase 2: Scanning & Network Discovery; Phase 3: GHDB |

---
 
## 1. Liability Disclaimer and Scope
The activities documented in this report were carried out for educational and training purposes as part of the Cybersecurity & Ethical Hacking programme at Network Walks. The domain networkwalks.com was supplied by the instructor for the assigned exercise, while the network scanning activity was conducted on my own local network. Reconnaissance and scanning activities should only be performed on systems, domains, and networks for which appropriate permission has been granted. The findings in this report represent observations from the assigned practical exercises and should not be interpreted as confirmation of exploitable vulnerabilities. Do not use anything from here to break the law. Every action you take is your own responsibility. Misuse can lead to criminal charges, heavy fines, loss of your job, and a permanent record. In most countries, unauthorised access is a crime even when nothing is damaged.

---

## 2. Introduction
This report documents two practical activities completed during Week 2 of my cybersecurity training. The first activity focused on footprinting and reconnaissance using Maltego, supported by the installation and configuration work required to run the application. The second activity focused on network scanning and host discovery using Zenmap, the graphical interface for Nmap. The third activity explored using the Google Hacking Database (GHDB) to identify publicly indexed information through search queries known as Google dorks. The exercise involved finding relevant dorks, testing them in Google Search, and reviewing the results against each task's requirements.
Together, these exercises introduced three complementary approaches to information gathering and reconnaissance: using Maltego to discover and examine relationships between publicly available information associated with a supplied internet domain, using Zenmap to identify active devices and examine exposed network services within a local network, and using GHDB to discover information that search engines have publicly indexed through targeted search queries. The report records the tools used, the procedures followed, a screenshot as evidence, and a short note on why the finding matters from an attacker's point of view.

---

## 3. Tools and Technologies Used
| Tool | purpose |
|---|---|
| Kali Linux |	Linux environment used during the footprinting and reconnaissance practical.|
| Maltego Graph Desktop | Visual investigation and relationship-mapping tool used for the assigned footprinting exercise.|
| Java Runtime / Development installations |	Java installations tested while resolving Maltego's Java compatibility and startup issue. |
| Windows 11 virtual machine |	Windows environment used to run the assigned Windows applications and collect practical evidence. |
| Oracle VirtualBox |	Virtualisation platform used to run the Windows virtual machine. |
| Zenmap |	Graphical interface for Nmap used to perform local network host discovery. |
| Exploit-DB |	Served as the website used to access the Google Hacking Database (GHDB). |
| Google Hacking Database (GHDB) |	Provided Google dork search queries designed to locate specific types of information indexed by search engines. |
| Google Search |	Used to test selected dorks and review the publicly indexed results against the task requirements. |
| Windows Command Prompt |	Used to inspect local IP configuration and adapter details. |
| VirtualBox Guest Additions |	Installed to enable clipboard integration between the Windows guest and Windows 11 host.

## 4. Activities Performed
### 4.1 Footprinting and Reconnaissance with Maltego
The first activity involved setting up Maltego Graph Desktop and using it for the footprinting exercise. The target domain is networkwalks.com.
I downloaded the Maltego application and worked through the installation and initial configuration process. On the first attempt to run Maltego, the application displayed the error: “Cannot find Java 1.8 or higher.” I investigated the Java configuration, checked the installed versions, and  I subsequently installed and tested Java versions 27 and 25, before installing Java 17, which is the  compatibility/startup requirement. The issue was resolved after installing and configuring Java 17, after which Maltego Graph Desktop was able to launch successfully. 
Once the application launched successfully, I signed in to my Maltego account and completed the online activation process. The activation was successful, allowing me to proceed with the practical exercise in Maltego Graph Desktop.

### 4.1.1 Footprinting Exercise
Using networkwalks.com, I carried out the assigned Maltego exercise and ran the relevant transform to retrieve information for analysis. The transform returned results, which I examined within the Maltego graph interface.
The purpose of this activity was to practise using Maltego to gather and visualise information associated with a domain. The resulting graph provided a visual way to examine the information returned by the transform and its relationships.
The exact entities and transform output are in the screenshots captured during the exercise. No additional findings have been inferred beyond the results observed in the application.

#### Evidence 1 – Maltego installation and Java troubleshooting 
![Maltego Installation](https://github.com/user-attachments/assets/24fa72e8-87e3-4e85-b64f-6be36f80eda4)

![Java Error](https://github.com/user-attachments/assets/a18382f5-52e3-44a7-9240-a70f2c189b49)

![Command Prompt check for java](https://github.com/user-attachments/assets/0fccbbbc-6064-4c25-ae5b-20b8751e1870)

![CMD Java 27 confirmed](https://github.com/user-attachments/assets/a8fa6344-62eb-4589-a029-0e765fe50151)

![Java 17 installation](https://github.com/user-attachments/assets/a7d2d334-accd-4c07-9367-c99c4be7bb6b)

![Maltego Running Successfully](https://github.com/user-attachments/assets/3bad3046-dee8-4bf3-9c35-71b38fc0be49)

---
#### Evidence 2 – Maltego activation
![Activation Options](https://github.com/user-attachments/assets/a465f72d-55cb-4720-956f-274a636844b6)

![Login to Maltego](https://github.com/user-attachments/assets/310c64e4-253c-4c8b-a1b8-48c57c0b374c)

![Activation Successful](https://github.com/user-attachments/assets/41fb748b-8de0-4d10-83b6-7ae3e2e6f150)

#### Evidence 3 – Maltego transform results
![Maltego New Page](https://github.com/user-attachments/assets/77dcf559-359a-435f-9e91-5edbaadb98fa)

![Maltego input](https://github.com/user-attachments/assets/c14b964e-6241-463e-989f-d49c1e77b416)

![Domain Search](https://github.com/user-attachments/assets/a1035834-d28d-4a6f-8c9c-191b41953ede)
![Domain](https://github.com/user-attachments/assets/96f7e100-b3be-423d-b470-e7f39037f373)


![Person Search](https://github.com/user-attachments/assets/7b8bed90-5940-4d06-bed0-11012671cb31)

### 4.2 Network Scanning with Zenmap
The second activity involved using Zenmap to discover active hosts on my own local network. The assignment required identifying the local IP address and LAN subnet, performing a ping scan, recording the live hosts and their IP and MAC addresses, and exporting the network topology as a PDF.

#### 4.2.1 Zenmap Download and Installation
I downloaded the required Zenmap installation package from the official Nmap website (https://nmap.org/download.html) and installed it in the Windows environment used for the practical. After installation, I opened Zenmap and confirmed that the application was available for the scanning exercise.

#### 4.2.2 Identifying the Local IP Address and Subnet
Before scanning, I opened Windows Command Prompt and ran the following command: ipconfig.
I reviewed the network adapter output to identify the IPv4 address, subnet mask, default gateway, and MAC address. This information was used to determine the local subnet to enter as the scan target in Zenmap.

#### 4.2.3 Performing a Ping Scan
I entered the identified local subnet in Zenmap's Target field and selected the Ping Scan profile. I then initiated the scan. Zenmap used Nmap host-discovery functionality to identify responsive devices within the specified subnet. The command generated by the Ping Scan profile uses the Nmap -sn option. nmap -sn [IPv4 address].

#### 4.2.4 Identifying Live Hosts and IP Addresses
After the scan completed, I reviewed the Hosts panel and Nmap Output to identify the number of responsive hosts and record their IP addresses. The results recorded below should match the scan evidence captured from my own environment.
Scan finding	My observed result
Number of live hosts --[Two hosts were live, including mine]
Live host IP addresses -- [IP addresses shown in Zenmap]

#### 4.2.5 Identifying MAC Addresses
To identify the MAC address of the local Windows network adapter, I returned to Command Prompt and executed: ipconfig /all
I examined the Physical Address field under the relevant network adapter and compared the available information with the MAC address details displayed in the Zenmap scan output.
Host IP address	MAC / Physical address
[Host IP 1]	[MAC address 1]
[Host IP 2]	[MAC address 2]

#### 4.2.6 Network Topology Visualisation and PDF Export
After reviewing the scan results, I opened the Topology tab in Zenmap and enabled the legend to interpret the displayed symbols. I used the Save Graphic option to export the topology in PDF format, as required by the assignment.
The topology view provided a graphical representation of the discovered hosts and their relationship to the scanning computer. The exported PDF was retained as a project deliverable.

#### Evidence 4 – Local network configuration & MAC address identification
![](https://github.com/user-attachments/assets/edc3d20e-2d2b-41c5-ab75-6be66e4f5b7f)

![](https://github.com/user-attachments/assets/3b45b892-8202-443a-bbcc-d82ab517be17)

#### Evidence 6 – Zenmap ping scan
![](https://github.com/user-attachments/assets/08d7d1f7-bc7b-40b3-982e-88b4d513d4c3)

#### Evidence 7 – Live hosts
![](https://github.com/user-attachments/assets/4869e642-1faa-4c84-82f2-8f676b3bf601)

#### Evidence 8 – Network topology
![Network Topology](https://github.com/user-attachments/assets/eadacc78-5feb-48b5-9617-6045ba738e58)

#### Evidence 9 – Exported topology
![Topology pdf](https://github.com/user-attachments/assets/dbd88960-4157-4a35-9ae8-58999f652218)

### 4.3 Footprinting and Reconnaissance with GHDB
The third activity involved accessing Exploit-DB from the Kali Linux environment and navigating to the Google Hacking Database (GHDB). The GHDB was used to identify search dorks relevant to two assigned tasks: locating camera-related search results and finding publicly indexed mathematics e-book PDF listings.

For the camera-related task, the assigned keywords, “cam” and “cam live,” were entered into the GHDB Quick Search. The available dorks were reviewed, and relevant queries were selected. Each selected dork was copied into Google Search, and the returned listings were examined individually against the task requirements.

For the mathematics PDF task, relevant keywords were entered into the GHDB Quick Search to identify dorks that could locate mathematics e-book PDF files. The selected queries were tested in Google Search, and the returned listings were reviewed one by one to identify those matching the assignment criteria.

The search and review process was repeated for both tasks until the required activities were completed. Relevant observations were recorded for the report. 

#### Evidence (step-by-step process)
![](https://github.com/user-attachments/assets/f7c27d0f-9614-4d07-ae92-c81693cfd3b0)

![](https://github.com/user-attachments/assets/6c9f27f0-c462-40c3-a1e0-999412deb74d)

![](https://github.com/user-attachments/assets/41e2efc4-229e-4490-a23f-f7c005ccb0fd)

![](https://github.com/user-attachments/assets/aa64fa9a-a68b-4128-af57-01133307f21e)

![](https://github.com/user-attachments/assets/7063a14b-4ff2-4897-aa95-cf9358cc6132)


#### Evidence (Result for cam)
![](https://github.com/user-attachments/assets/38abf1fc-d364-4066-943c-c8e9dfadf0d8)

![](https://github.com/user-attachments/assets/3937079c-c3ea-474d-b25a-3f500fbde450)

![](https://github.com/user-attachments/assets/7b43ffce-f81d-4464-a652-dc5a32b634ae)

#### Evidence (Result for Math e-book PDF)

---
## 5. Challenges Encountered and Troubleshooting

### 5.1 Maltego Java Compatibility and Application Startup
The main challenge during the Maltego setup was the initial startup error stating that Java 1.8 or higher could not be found. The installation process also involved correcting an initial package-selection mistake and testing multiple Java versions. I installed and tested Java 27 and Java 25 on Windows, then installed Java 17. After configuring Java 17, Maltego launched successfully, and I completed the online login and activation process.

### 5.2 Saving and Accessing Zenmap Project Evidence
During the Zenmap exercise, I needed to save the topology in PDF format and move screenshots and copied information from the Windows virtual machine to the Windows 11 host. The clipboard integration initially did not work because VirtualBox Guest Additions was not installed in the guest operating system.
To resolve the issue, I located the Guest Additions installer files and selected VBoxWindowsAdditions-amd64 for the 64-bit Windows guest. I ran the installer, completed the installation, and restarted the virtual machine. I then enabled Bidirectional for Shared Clipboard and Drag and Drop in the VirtualBox settings. After this configuration, copying and pasting between the virtual machine and host Windows worked successfully, making it easier to transfer and organise the project evidence.

### 5.3 GHDB Repetition
The practical required reviewing multiple GHDB dorks and checking the returned search listings individually. This involved repeating the search and review process to identify results that matched the criteria for each task.

## 6. Risk Analysis and Security Relevance
These are potential risks associated with exposed information or unreviewed network devices; they are not confirmed vulnerabilities. 
Any potentially sensitive findings should be handled responsibly, documented with appropriate redaction, and reported through an authorized channel.

| Observation	| Potential impact | Indicative risk |
|---|---|---|
| 1.	Domain-related information and relationships were returned during the Maltego exercise.	| Information gathered from public sources may help build a profile of an organisation and its digital footprint. | Low–Medium |
| 2. The reconnaissance exercise demonstrated that domain-related information can be collected and visually related.	| Collected information may support further targeted reconnaissance if misused.	| Low–Medium |
| 3. Zenmap identified responsive hosts within the local subnet. | Unrecognised or unauthorised devices on a network may increase the organisation's exposure.	| Medium |
| 4. IP and MAC address information was available for host identification.	| Network addressing information can help an administrator inventory devices, but may also assist an attacker conducting internal reconnaissance.	| Low |
|	5. A network topology was generated from the scan results.	| An outdated or widely exposed network map may disclose useful information about the network layout.	| Low–Medium |

The exercises focused on information gathering and host discovery. No exploitation or vulnerability validation was performed as part of these activities. GHDB searches can reveal information that has been indexed publicly, but a search result alone does not establish that a system is vulnerable or that access is authorized. The observations therefore require further authorised assessment before any vulnerability can be confirmed. The practical was conducted for educational purposes. Any further testing or access should be limited to systems within an explicitly authorized scope.

---
## 8. Recommendations
1.	Review the organisation's publicly visible digital footprint periodically and remove or minimise information that is not necessary to disclose.
2.	Keep website platforms, plugins and supporting technologies updated and review them against relevant security advisories.
3.	Use information gathered through reconnaissance to improve asset awareness and defensive monitoring, not to assume that an exposed detail is automatically a vulnerability.
4.	Perform regular network discovery on authorised internal networks to maintain an accurate inventory of active devices.
5.	Investigate unfamiliar or unexpected devices identified during internal network scans.
6.	Maintain up-to-date network diagrams and protect topology documents because they may contain sensitive infrastructure information.
7.	Ensure that reconnaissance and scanning activities remain within the scope of explicit authorisation.

---
## 9. Conclusion
During Week 2 of my Cybersecurity & Ethical Hacking training, I completed practical activities covering footprinting and reconnaissance with Maltego and GHDB, followed by network scanning and discovery with Zenmap.

The Maltego exercise provided experience with installing and configuring a reconnaissance tool, resolving a Java compatibility issue, completing online activation, and running a transform against the instructor-provided networkwalks.com target. The Zenmap exercise provided practical experience identifying local network configuration, performing a ping scan, reviewing active hosts, identifying IP and MAC addresses, and generating a network topology. The GHDB exercise provided practical experience in using search operators for footprinting and reconnaissance.

The troubleshooting involved in the activities was also valuable. Resolving the Maltego Java startup issue and configuring VirtualBox Guest Additions strengthened my ability to investigate application and virtual-machine integration problems rather than stopping at the initial error.

Overall, these exercises reinforced the importance of structured information gathering, network visibility, careful interpretation of results, reviewing findings carefully, handling potentially sensitive information responsibly, and clear technical documentation. They also highlighted that reconnaissance and scanning must always be performed within an authorised scope.

---
## 10. 📌 Project Information
| | |
|---|---|
| Author	| Rotimi Elijah Ogunbiyi |
| Cybersecurity Intern | B084 |
| LinkedIn | | 
| Program Name | Cybersecurity program at Networkwalks |
| Week | 02 | 
| Repository | GitHub |



---
## END OF REPORT
