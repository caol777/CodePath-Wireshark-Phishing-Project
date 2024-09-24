Overview:

This project involved identifying phishing emails by analyzing packet capture (PCAP) files using Wireshark, filtering the SMTP traffic to identify malicious emails sent by a bad actor. I was able to extract email content, identify phishing attempts, and pinpoint the malicious actor's IP address. Here's a step-by-step guide on how I completed the project.

Step-by-Step Guide

Step 1: Open the PCAP Files in Wireshark

First, I downloaded the pcap\_files.zip file and unzipped it using the command:

unzip pcap\_files.zip

After extracting the files, I opened them individually in Wireshark. Since the goal was to analyze email traffic, the primary protocol I focused on was SMTP (Simple Mail Transfer Protocol).

Step 2: Apply Filters to Narrow Down SMTP Traffic

To identify emails sent over the network, I used the SMTP filter in Wireshark. Applying the filter helped me isolate email traffic from all the other captured packets. The filter I used was:

smtp

This filter displayed only SMTP-related traffic, including email transmissions.

Step 3: Identify Suspicious Activity

As I was reviewing the packet captures, I noticed that in File C, one particular IP address consistently sent a high volume of emails to multiple other IP addresses. This unusual behavior led me to suspect that this IP address might belong to the malicious actor.

Step 4: Read Email Contents with SMTP Filters

To get a clearer view of the email contents, I further refined my filter to focus on the End of Message (EOM) command used in SMTP communications. This command signifies the end of an email's body. The filter I applied was:

smtp.eom

Using this filter allowed me to fully read the emails. I found that the emails from the suspicious IP address were phishing attempts. They contained threatening messages claiming that the attacker had access to the recipient's passwords and personal data, demanding payment to prevent the leak.

Step 5: Export the Phishing Emails as .eml Files

Once I identified the phishing emails, I exported the captured packets as .eml files to simulate how they would appear to the victim. This step provided a better understanding of the formatting and presentation of these phishing emails. To export the emails, I went to:

File -> Export Objects -> IMF...

I then saved the specific phishing emails, which could later be opened using email clients like Outlook or Mail.

Results

Malicious Actor's IP Address: Identified from File C as the one sending phishing emails to multiple addresses.

Phishing Email Subject Lines:

"Your Password Has Been Compromised"

"Pay Up or Get Exposed!"

"Final Warning: Leaked Data"

Explanation: By filtering the network traffic using SMTP-related commands in Wireshark, I identified an IP address responsible for sending phishing emails. These emails demanded money and threatened to leak personal data. Exporting the emails as .eml files provided a full view of the scam from the victim’s perspective.

Additional Notes for GitHub Portfolio

I plan to include screenshots of the phishing emails and packet captures, along with the .pcap files and .eml exports to demonstrate the process.

Conclusion
This project provided hands-on experience with analyzing PCAP files and identifying malicious activities like phishing. It also helped improve my skills in using Wireshark for cybersecurity investigations, especially in analyzing email traffic and extracting useful information.
