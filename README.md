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
