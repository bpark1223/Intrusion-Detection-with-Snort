# Intrusion-Detection-with-Snort
<p>In this project, I will make cover the process of using custom and community Snort rules. I will be using Snorpy, which is a Web Based Snort Rule Creator / </p>
<h2>Utilities Used</h2>
</p>- Ubuntu </p>
</p>- UTM VM setup </p>
</p>- Snort </p>
</p> Snorpy </p>
<h2>Step-by-Step Walkthrough</h2>
</p> I use vim (text editor) to make changes to my local rules. </p>
<img width="730" alt="Screenshot 2024-07-22 at 5 33 01 PM" src="https://github.com/user-attachments/assets/40543129-2ad9-4185-87ee-e6a1d0a8750a">
</p> I want to configure a rule to detect any ICMP pings. I write the following code in my text editor which means: generate an alert for any ICMP traffic that comes from any external address with any external port that comes into our home network subnet and any port with the message "ICMP Ping Detected." The SID is 100001 and this is revision 1. </p>
<img width="821" alt="Screenshot 2024-07-22 at 5 48 56 PM" src="https://github.com/user-attachments/assets/d9fc0865-e7d2-4675-bcd1-676e958bb8cc">
</p> I use man Snort to look at options before I run snort. The following code means: run snort in quiet mode. the log directory is var/log/snort, and the interface is enp0s1. The alert mode is console (because we are displaying it to ourselves and not yet logging them), and the configuration file is etc/snort/snort.conf 
</p> <img width="1052" alt="Screenshot 2024-07-22 at 6 15 11 PM" src="https://github.com/user-attachments/assets/54e50a69-a55f-45b0-a9fc-1e96c6640495" </p>
