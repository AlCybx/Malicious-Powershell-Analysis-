# Malicious-Powershell-Analysis-

## Objective

The project on Malicious PowerShell Analysis Lab was designed to create a secure setting for emulating and deciphering encoded PowerShell scripts, with the goal of determining the specific malware behind the attack. The main objective centered on employing CyberChef to decode the encoded PowerShell, following an incident where an employee inadvertently activated malware through a phishing email, leading to significant operational disruption across the business.

### Skills Learned

- Understanding of encoding and encryption, enabling to understand and apply various methods for securing and transforming information.
- Proficiency in data analysis and forensic investigation, to dissect complex data formats, decode communications, and uncover hidden information within diverse datasets.

### Tools Used

- CyberChef.
- Text Editor.


## Step 1

<img width="1440" alt="Screenshot 2024-03-05 at 21 36 54" src="https://github.com/AlCybx/Malicious-Powershell-Analysis-/assets/161755166/06ef1cb3-f305-45b5-9aeb-3821d97a67ee">
*Ref 1: Decoding Malicious Powershell*
The PowerShell text was transferred into CyberChef by copying and pasting it at the input section, selecting base64 along with decode text in the recipe section for processing. Once the text underwent decoding, the investigation proceeded to identify the security protocol utilized for communication with a suspicious domain.The suspicious domain has been highlighted in the attachement.

## Step 2

<img width="1157" alt="Screenshot 2024-03-05 at 23 37 50" src="https://github.com/AlCybx/Malicious-Powershell-Analysis-/assets/161755166/41f92c05-7fd5-4938-9161-dbe06b26b03f">
*Ref 2: Finding directory the obfuscated PowerShell is create*
Upon examining the obscured script once decoded, it was observed that a directory had been established at the path "\HOME\Db_bh30\Yf5be5g".

## Step 3

<img width="714" alt="Screenshot 2024-03-06 at 19 03 22" src="https://github.com/AlCybx/Malicious-Powershell-Analysis-/assets/161755166/04bdc42b-7a2a-480a-88e0-c02883b18d7d">
*Ref 3: Finding the name of file is being downloaded*
Continuing with a comparable procedure, another encounter of string concatenation, now with incorporating variable referencing as well, the name of file is determined.

## Step 4

<img width="717" alt="Screenshot 2024-03-06 at 19 15 23" src="https://github.com/AlCybx/Malicious-Powershell-Analysis-/assets/161755166/b2a6a846-c66c-4461-b482-6afb182f2356">
*Ref 4: Finding what was used to execute downloaded file*
The file is in DLL format, comprising libraries housing code and data to perform specific tasks in support of an .exe file. Typically, an .exe file invokes a .dll, but they can also run independently via rundll32.exe. Evidence of this behavior is apparent in the script.

## Step 5

<img width="714" alt="Screenshot 2024-03-06 at 19 28 23" src="https://github.com/AlCybx/Malicious-Powershell-Analysis-/assets/161755166/55274266-7923-42e2-a2a0-74ee95a32a1a">
*Ref 5: Identifying the domain name of the URI ending in ‘/6F2gd/’*
In order to locate the domain name associated with the URI ending in '6F2gd', I utilized the provided hint in the search box to locate it. Once located, I proceeded to analyze the URI in question which is vm.mcdevelop.net.

## Step 6

<img width="1440" alt="Screenshot 2024-03-06 at 19 49 07" src="https://github.com/AlCybx/Malicious-Powershell-Analysis-/assets/161755166/4d04ac2d-6284-4636-a2b9-3ee2b8518865">
*Ref 5: Identifying the name of malware Based on the analysis of the obfuscated code*
In order to determine the name of the malware, the URI "vm.mcdevelop.net" was copied and pasted into URL Haus, revealing the malware's identity as "Emotet."
