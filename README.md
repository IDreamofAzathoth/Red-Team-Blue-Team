# Red-Team-Blue-Team
**Project Description**

In our second project I worked in a Red Team vs Blue Team scenario, where I played the role of both pentester and SOC analyst.

As the red team I attacked a vulnerable VM within our environment, ultimately gaining root access to the machine. As the Blue Team, I used Kibana to review logs taken during the attack, using those logs to extract hard data and visulizations for our report.

Then I interpreted the log data to suggest mitigation strategies for each exploit that I successfully performed.

**Project Objectives**

This project will apply the knowledge and use of the following skills and tools:

   * Penetration testing with kali Linux.
   * Log and incident analysis with Kibana.
   * System hardening and configuration.
   * Reporting, documentation, and communication.

## Red Team

Before performing the attack it was essential to setup the backend logs to capture the attack data.

**Filebeat**

   * filebeat modules enable apache
   * filebeat setup

**Metricbeat**

   * metricbeat modules enable apache
   * metricbeat setup

**Packetbeat**

   * packetbeat setup

**Restarting to ensure they working and operational**

   * systemctl restart filebeat
   * systemctl restart metricbeat
   * systemctl restart packetbeat


**Red Team Instructions**

   * Discover the IP address of the Linux web server.
   * Locate the hidden directory on the web server.
   * Brute force the password for the hidden directory using Hydra.
   * Break the hashed password with the Crack Station website or John the Ripper.
   * Connect to the server via WebDAV.
   * Upload a PHP reverse shell payload.
   * Execute payload to open up a meterpreter session.
   * Find and capture the flag.

# Blue Team

What your attack looks like from a defender's perspective.
How stealthy or detectable your tactics are.
Which kinds of alarms and alerts SOC and Incident Response professionals can use to spot these types of attacks while they occur, rather than after.
