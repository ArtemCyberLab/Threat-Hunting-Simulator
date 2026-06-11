Scenario overview
The alert hit the SOC around 4:00 PM. Two machines, fully encrypted. Ransom notes where files used to be. The central SIEM went dark just minutes before.

Fortunately, someone had managed to pull logs from the two affected hosts—Perry’s and another developer’s—before everything spiraled out of control.

Now the team has to figure out what happened. And all signs point to something Perry did earlier that day...

September 26, 2023—just another Tuesday at SwiftSpend Financial, a small but resourceful company where everyone’s always juggling five deadlines and too much coffee.

Perry, one of the devs, had a tight sprint deadline. His manager had sent him an encrypted .7z archive with a snippet of code that needed finishing yesterday. Perry quickly realized his workstation didn’t have anything that could unzip the file. So, in true caffeine-fueled developer fashion, he Googled the first thing that came to mind, clicked the top result (because who scrolls down?), and downloaded a tool to open it.

Everything seemed fine. Until it wasn’t.

A little more than one hour later, Perry’s workstation started acting weird. At first, it was slow. Then apps crashed. Then everything—literally every file—became unreadable.

Your mission as a threat hunter is to dig through the logs and reconstruct the attack chain. What happened? How did it start? How did it spread? And what damage did it do?

Scenario objectives
Investigate command-line artifacts and reconstruct process trees to reveal the attacker's steps.
Correlate tool usage with MITRE ATT&CK techniques.
Map compromised accounts over time.

SOC REPORT !!!
ID 1000 true positive
Time of activity: Jun 6th 2026 at 21:26
List of Affected Entities: support@tryhatme.com
Reason for Classifying as True Positive: The sender  is asking  the victim about bank details 
Reason for Escalating the Alert: N/A
Recommended Remediation Actions: Block the sender adress. Check to see if any other similar emails  were delivered to other users
List of Attack Indicators: Asking for bank details 

ID 1001 - 1002
Time of Activity: Jun 8th 2026 at 20:01
List of Related Entities: win-3459
Reason for Classifying as False Positive:  Nothing malicious was detected.

ID 1003
Time of Activity: Jun 8th 2026 at 20:04
List of Related Entities:  yani.zubair@tryhatme.com
Reason for Classifying as False Positive:  Appears to be spam

1004
Time of Activity: Jun 9th 2026 at 20:35
List of Related Entities: kyra.flores@tryhatme.com
Reason for Classifying as False Positive: Appears to be spam

1005
Time of activity: Jun 9th 2026 at 20:37
List of Affected Entities: michael.ascot@tryhatme.com
Reason for Classifying as True Positive: The email is a confirmed phishing attempt utilizing high-pressure social engineering tactics to deliver a malicious attachment. The sender creates an artificial sense of urgency by claiming the account will be suspended today. Furthermore, the message uses intimidation by threatening immediate legal action within 24 hours to panic the recipient. The ultimate goal of this pressure is a malicious call to action, forcing the user to open an unverified "invoice" file. Therefore, the email exhibits classic indicators of a malicious campaign aimed at endpoint compromise.
Reason for Escalating the Alert: N/A
Recommended Remediation Actions: First, the affected computer must be isolated from the network immediately to stop the threat from spreading. Security teams should delete the malicious email from all user mailboxes to prevent others from opening it. A complete antivirus and EDR scan needs to be run on the victim's machine to check for any malware. Additionally, the user's password must be reset right away in case their credentials were stolen. Finally, the sender's email address and domain should be blocked on the email gateway.
List of Attack Indicators: The email comes from a highly suspicious external domain (@hatmakereurope.xyz) that does not look like a legitimate billing department. Inside the message, the sender uses aggressive language like URGENT and FINAL NOTICE to create an artificial sense of urgency and panic the recipient. Furthermore, the text includes a strict 24-hour deadline before "legal action" starts, which is a classic psychological trick to force quick action. The attachment itself is sent as a compressed archive (.zip), which is a common method used by attackers to hide malicious files from email security filters. Finally, the file name contains a clear spelling mistake (Febrary instead of February), which is a major red flag for any official financial document.

iD 1006
Time of activity: Jun 10th 2026 at 21:19
List of Affected Entities: 
sender: john@hatmakereurope.xyz 
recipient: michael.ascot@tryhatme.com 
attachment: ImportantInvoice-Febrary.zip
Reason for Classifying as True Positive: 
Attachment contain a malicious file with .lnk as an extension (instead of PDF).
Reason for Escalating the Alert: 
Scanning the attachment reveal it as malicious. 
There are many typos, the file is called (ImportantInvoice-Febrary.zip) and the file contained is called 'invioce.pdf.' but instead is a .lnk file.
Recommended Remediation Actions: 
Quarantine the email. 
Exclude the domain.
List of Attack Indicators: ImportantInvoice-Febrary.zip


