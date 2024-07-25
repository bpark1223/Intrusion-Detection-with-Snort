# Intrusion-Detection-with-Snort
<p>In this project, I will  cover the process of using custom and community Snort rules. I will also make use of Snorpy, which is a Web Based Snort Rule Creator </p>
<h2>Utilities Used</h2>
</p>- Ubuntu </p>
</p>- UTM VM setup </p>
</p>- Snort </p>
</p> Snorpy </p>
<h2>Step-by-Step Walkthrough</h2>
</p> I use nano (text editor) to make changes to my local rules. </p>
<img width="730" alt="Screenshot 2024-07-22 at 5 33 01 PM" src="https://github.com/user-attachments/assets/40543129-2ad9-4185-87ee-e6a1d0a8750a">
</p> I want to configure a rule to detect any ICMP pings. I write the following code in my text editor which means: generate an alert for any ICMP traffic that comes from any external address with any external port that comes into our home network subnet and any port with the message "ICMP Ping Detected." The SID is 100001 and this is revision 1. </p>
<img width="821" alt="Screenshot 2024-07-22 at 5 48 56 PM" src="https://github.com/user-attachments/assets/d9fc0865-e7d2-4675-bcd1-676e958bb8cc">
</p> I use man Snort to look at options before I run snort. The following code means: run snort in quiet mode. the log directory is var/log/snort, and the interface is enp0s1. The alert mode is console (because we are displaying it to ourselves and not yet logging them), and the configuration file is etc/snort/snort.conf 
</p> <img width="1052" alt="Screenshot 2024-07-22 at 6 15 11 PM" src="https://github.com/user-attachments/assets/54e50a69-a55f-45b0-a9fc-1e96c6640495" </p>
</p> I open a terminal in my Kali Linux machine and perfom a ping on the ubuntu vm that has Snort installed. Snort picks this up, as I can see in my Ubuntu Machine. </p>
<img width="1440" alt="Screenshot 2024-07-23 at 7 28 05 PM" src="https://github.com/user-attachments/assets/9570edca-10af-4f84-b1a1-b6edf7afb899">
</p> I now write another rule for SSH connections. I use my vim text editor to add the following local rule: </p>
<img width="867" alt="Screenshot 2024-07-23 at 7 32 22 PM" src="https://github.com/user-attachments/assets/cd3ba14d-3c51-425f-8216-32470c2c9066">
</p> I SSH the ubuntu macihne from my Kali Linux vm while running Snort, and authenticate successfully. </p>
<img width="843" alt="Screenshot 2024-07-23 at 8 19 50 PM" src="https://github.com/user-attachments/assets/3f025766-2117-465e-a614-0d9361ca55c9">
</p> I see the SSH authentication attempts through Snort </p>
<img width="1403" alt="Screenshot 2024-07-23 at 9 08 42 PM" src="https://github.com/user-attachments/assets/a86c6f2d-fcf2-4adb-b395-56b8159cfbc5">
</p> I navigate to snorpy (http://www.cyb3rs3c.net/) which is a graphical interface allowing you to simplify the process of creating a rule. I want to create a rule to catch FTP traffic, so I configure as follows: </p>
<img width="1209" alt="Screenshot 2024-07-24 at 2 56 20 PM" src="https://github.com/user-attachments/assets/8be2d455-53ce-4ad8-b38f-b13324b77195">
</p> I navigate to my local rules file and paste the output from Snorpy </p>
<img width="1194" alt="Screenshot 2024-07-24 at 2 58 30 PM" src="https://github.com/user-attachments/assets/9ea813e1-61b7-4f17-baac-aa120079c423">
</p> I start up Snort on my ubuntu machine and then use my kali linux machine to ftp into the ubuntu machine. I can now see ftp authentication attempts from my kali linux vm into my ubuntu machine through snort. </p>
<img width="1440" alt="Screenshot 2024-07-24 at 3 09 21 PM" src="https://github.com/user-attachments/assets/ceefb353-4c8d-4a1d-8f16-3237f663ca8d">
</p> I want to take a look at some community rules that I had previously disabled. I navigate to the snort.conf file to uncomment the lines </p>
<img width="852" alt="Screenshot 2024-07-24 at 3 20 55 PM" src="https://github.com/user-attachments/assets/106f245e-d5e2-4212-a417-3adc208b227b">
</p> I navigate to Snort's website and download/extract the community rules for Snort  v2.9. This is a set of rules that allows you to detect exploits, intrusions for specific CVE's, malware, etc. One important ruleset is the eternal blue rule, which filters a Windows exploit that allows cyber threat actors to remotely execute arbitrary code and gain access to a network by sending specially crafted packets. I will copy this rule and add it to my local ruleset. 
</p> <img width="910" alt="Screenshot 2024-07-24 at 4 06 27 PM" src="https://github.com/user-attachments/assets/252c88f9-e943-400e-9121-0f005dfc46cf"> </p>


