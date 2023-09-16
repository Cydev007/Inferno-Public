# Inferno-Public
*(As this is a University Academic Project I am not Providing Source Code Publically).*
#### In an increasingly interconnected and digitized world, the threat landscape has evolved, posing significant challenges to individuals and organizations alike. The rise of cybercrime, malware attacks, and sophisticated hacking techniques demands robust security measures to safeguard sensitive data, systems, and networks. To address these pressing concerns, we have developed INFERNO, an advanced threat intelligence software that empowers users with the ability to detect malicious files/programs and malicious URLs, providing a comprehensive shield against cyber threats and analyzing malwares for security research pourposes.

![image](https://github.com/Cydev007/Inferno-Public/assets/108612723/7bf8ca48-83ad-4d12-a33a-228b4f47c007)

![image](https://github.com/Cydev007/Inferno-Public/assets/108612723/64ad2a10-11a1-4e3e-b956-affdfc18e3c2)

### This is a general DataFlow of our tool.
![image](https://github.com/Cydev007/Inferno-Public/assets/108612723/8c79d700-adea-47b2-9813-dc27a9871782)

#### INFERNO offers a range of features designed to deliver comprehensive protection:
1.	Malware Detection: The software employs advanced scanning techniques to identify known malware with image processing and detect suspicious files/programs on users' devices.
2.	URL Reputation Analysis: INFERNO analyzes URLs to determine their reputation, helping users avoid visiting malicious websites and falling victim to phishing attempts. 
3.	Malware Analysis: By analyzing the behavior of files and programs, INFERNO can identify suspicious activities of a malware in our device.
4.	Inferno assistant: This is a chatbot capable of answering cyber security related questions
5.	Yara Rules: YARA rules are malware detection patterns that are fully customizable to identify targeted attacks and security threats specific to your environment.


![image](https://github.com/Cydev007/Inferno-Public/assets/108612723/e693f96c-2ecc-4329-a0f6-6b680e8ea5f0)


## Malicious URL Detection Using Machine Learning.
Detect Malicious URLs using Logistic regression for more info visit https://github.com/Cydev007/Phishing-Url-Detection-Using-Machine-Learning-
![image](https://github.com/Cydev007/Inferno-Public/assets/108612723/def6093a-e81d-4306-bbfd-98b7b0629b12)



![image](https://github.com/Cydev007/Inferno-Public/assets/108612723/a3fae2fc-3abb-412b-85fd-e4c79ab85d44)

![Screenshot 2023-06-13 200455](https://github.com/Cydev007/Inferno-Public/assets/108612723/dc68bc26-263a-4fac-95b8-4abf29deb468)

## Inferno Assistant 
Inferno asistant is a basic chatbot for security related questions. If you have any doubt while analyzing malware you can ask this in desktop chatbot for instant answer.

![image](https://github.com/Cydev007/Inferno-Public/assets/108612723/eced7411-2c58-4ff5-a49c-890c446ef282)

## Detect Malware 
This Feature can suggest us an executable is secure to execute in our device or not?
For Detection malware we took a little different approch. we can detect malware using Image Data.
=> 	Link: https://www.kaggle.com/datasets/matthewfields/malware-as-images .
After getting the dataset, we did some pre processing task on the dataset, including image labeling and resizing.
For malware classification, we had use Transfer learning. Transfer learning is a machine learning technique that involves using knowledge gained from training a model on one task to improve performance on a different, related task. It allows a model to leverage pre-trained weights and learned representations from one domain to another, saving time and resources while enhancing performance on new tasks. Therefore, for our classification task we tested the accuracy for different pertained model including ResNet50, ResNet101, VGG16, VGG19, MobileNet and more. After testing some of the pre-trained model in the light of accuracy, at last we conclude that “ResNet50” is the best-fitted model in our dataset.
![image](https://github.com/Cydev007/Inferno-Public/assets/108612723/85a6928b-87e7-4400-bf9b-e6f77437695a)

Now we integreting this Model to our application. 

![image](https://github.com/Cydev007/Inferno-Public/assets/108612723/1f7cc401-d789-435b-ba08-b9d27ad641a7)
#### Non-Malicious File
![image](https://github.com/Cydev007/Inferno-Public/assets/108612723/787cc3a4-2625-4cf0-838e-010be596f260)
![image](https://github.com/Cydev007/Inferno-Public/assets/108612723/d250d54d-5803-4139-a8b5-af520e9650df)

#### Malware File
![image](https://github.com/Cydev007/Inferno-Public/assets/108612723/87fedcf3-4f41-42fd-b727-5a82acfb4b88)
![image](https://github.com/Cydev007/Inferno-Public/assets/108612723/46a5a73d-3cd8-40d9-9d7c-2c23db13384c)

## Malware Analysis: 
By analyzing the behavior of files and programs, INFERNO can identify suspicious activities of a malware in our device.
Malware analysis can be done by in several ways we took two approach 
![image](https://github.com/Cydev007/Inferno-Public/assets/108612723/853002b5-9795-4de6-9a0e-b6002f8bca5e)

### i.	Static Analysis : 
Static analysis of malware refers to the examination and analysis of malware without actually executing it. It involves inspecting the structure, content, and behavior of the malware code to gain insights into its functionality, potential impacts, and evasion techniques. This analysis technique is commonly used by security researchers, malware analysts, and antivirus companies to understand the nature and capabilities of malicious software.

PE header analysis is an essential step in static analysis when examining Windows executable files, including malware. The Portable Executable (PE) format is the executable file format used by Windows operating systems. Analyzing the PE header provides valuable information about the structure, characteristics, and behavior of the executable. Here are some key aspects to consider when performing PE header analysis for malware:

#### 1. File Type Identification: 
The PE header contains a signature that identifies the file as a PE executable. This signature is located at the beginning of the file and is typically "MZ" (hexadecimal representation) for DOS header followed by "PE\0\0" (hexadecimal representation) for the PE signature.
#### 2. Optional Header Information: 
The PE header contains an optional header that provides additional details about the executable. This includes the entry point address, the preferred base address for loading the executable into memory, the size of the image, and various flags that specify the characteristics of the executable.
#### 3. Sections and Virtual Addressing: 
The PE header defines the layout of sections within the executable. Each section contains specific data, such as code, data, resources, and import/export information. Analyzing the sections helps identify code injection, encrypted sections, or packed content within the executable. Virtual addresses associated with each section provide insights into the memory layout and the executable's behavior.
#### 4. Import and Export Tables: 
The import and export tables within the PE header list the functions and libraries that the executable imports or exports. Analyzing the import table helps identify external dependencies, such as APIs used by the malware to interact with the system. The export table indicates functions that the malware may expose for other modules to use, although this is less common for malicious code.
#### 5. Resource Information: 
The PE header also includes a resource table that stores various resources used by the executable, such as icons, images, strings, or configuration data. Analyzing the resource information can reveal any embedded files, encrypted data, or other artifacts used by the malware.
#### 6. Overlay Analysis: 
The PE header can provide insights into the presence of overlays within the executable. Overlays are additional data appended to the end of the PE file after the standard headers. Malware authors may use overlays to hide malicious code or data, making overlay analysis important for understanding the full extent of the malware's functionality.

By thoroughly analyzing the PE header, security analysts can gather crucial information about the malware, including its entry point, dependencies, sections, resources, and potential malicious behavior. This knowledge assists in understanding the malware's capabilities, developing detection mechanisms, and formulating appropriate mitigation strategies.
![image](https://github.com/Cydev007/Inferno-Public/assets/108612723/4998e24f-b6e0-41a7-a503-659f8aaab6dd)


## ii.	Dynamic Analysis:
Dynamic analysis of malware in a virtual environment involves executing the malware within a controlled, isolated environment to observe its behavior, interactions, and potential impacts. By running malware in a virtual environment, analysts can monitor its actions without risking the compromise of a real system. Here are the key steps involved in dynamic analysis of malware in a virtual environment:

#### 1. Setting up the Virtual Environment: 
Create a virtual machine (VM) using virtualization software like VMware, VirtualBox, or Hyper-V. The VM should closely resemble the target environment (e.g., specific operating system version, software configurations) where the malware is expected to execute. It's crucial to keep the virtual environment isolated from the host system and ensure appropriate security measures are in place.

#### 2. Snapshot or Sandbox: Take a snapshot of the clean state of the virtual machine or use a sandboxing tool to maintain a controlled environment. This allows for easy restoration to a clean state after malware analysis, preventing contamination or persistence of malware artifacts.

#### 3. Execution and Behavior Monitoring: Run the malware within the virtual environment while monitoring its behavior. Use tools like process monitors, network traffic analyzers, system call monitors, and behavior analysis tools to capture and analyze the malware's activities. This includes observing file system modifications, registry changes, network connections, process creation, DLL injections, and any attempts to evade detection or alter system settings.

![image](https://github.com/Cydev007/Inferno-Public/assets/108612723/5eeed8c3-0510-4a7a-a500-6c545c0ac60d)

#### 4. Dynamic Instrumentation: 
Employ dynamic instrumentation techniques, such as hooking or API monitoring, to intercept and monitor the malware's interactions with the system. This helps in capturing function calls, system API usage, and memory access patterns, providing deeper insights into the malware's actions and capabilities.

#### 5. Behavioral Analysis and Malware Family Classification:
Analyze the collected data to understand the malware's behavior, its intended purpose, and potential impact. Compare the observed behavior with known malware families and their typical characteristics to classify the malware and understand its capabilities.

Dynamic analysis in a virtual environment provides valuable insights into the malware's behavior, allowing analysts to understand its functionality, detect evasion techniques, and develop effective mitigation strategies. It complements static analysis techniques and aids in the identification of advanced threats, zero-day vulnerabilities, and the creation of robust defense mechanisms.


![image](https://github.com/Cydev007/Inferno-Public/assets/108612723/471504e8-68ef-4c91-b223-5504b903485a)

![image](https://github.com/Cydev007/Inferno-Public/assets/108612723/d26b9fcd-83b1-460e-a7ff-118a2da711d8)

![image](https://github.com/Cydev007/Inferno-Public/assets/108612723/099e6ac7-deda-4e02-b010-772c78518979)

## Writing YARA rules
YARA rules are easy to write and understand, and they have a syntax that resembles the C language.
Each rule in YARA starts with the keyword rule followed by a rule identifier. Identifiers must follow the same lexical conventions of the C programming language, they can contain any alphanumeric character and the underscore character, but the first character cannot be a digit. Rule identifiers are case sensitive and cannot exceed 128 characters.
In our application when you click on YARA rules a notepad promt will open where you can write your own YARA rules by analyzing malwares.
This is a Demo how to write YARA Rules.
![image](https://github.com/Cydev007/Inferno-Public/assets/108612723/0cee542b-4fd7-4e83-a740-c644fcc92dd3)
