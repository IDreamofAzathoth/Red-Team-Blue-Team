# Red-Team-Blue-Team
**Project Description**
The second project of the Cyber Security Bootcamp covered a Red Team vs Blue Team scenario. This project saw participants take on the roles of both pentester and SOC analyst.

The Red Team portion of the project encompassed attacking a vulnerable VM within the environment environment. The ultimate goal being to gain root access to the machine. 

The Blue Team portion covered the use of Kibana to review logs taken during the attack. Using those logs to extract forensic data and propose remediation strategies for how to better secure the targeted network in the future.

**Project Objectives**
This project will apply the knowledge and use of the following skills and tools:

   * Penetration testing with kali Linux.
   * Log and incident analysis with Kibana.
   * System hardening and configuration.
   * Reporting, documentation, and communication.

## Red Team
Prior to the pentest, setup of the backend logs was required in order to capture the attack data.

<details>
    <summary>The beats and commands used to set up Kibana.</summary>
  <br>

**Filebeat**
  - `filebeat modules enable apache`
  - `filebeat setup`

**Metricbeat**
  - `metricbeat modules enable apache`
  - `metricbeat setup`
  
**Packetbeat**
  - `packetbeat setup`
  
**Restarting to ensure they working and operational**
  - `systemctl restart filebeat`
  - `systemctl restart metricbeat`
  - `systemctl restart packetbeat`
  
</details>

<br>

**Red Team Instructions**
  1. Discover the IP address of the Linux web server.
  2. Locate the hidden directory on the web server.
  3. Brute force the password for the hidden directory using Hydra.
  4. Break the hashed password with the Crack Station website or John the Ripper.
  5. Connect to the server via WebDAV.
  6. Upload a PHP reverse shell payload.
  7. Execute payload to open up a meterpreter session.
  8. Find and capture the flag.

# Blue Team
**Blue Team Instructions**

For the Blue Team, Kibana was used to analyse logs taken during the earlier Red Team attack. The data collected will be used to develop ideas for new alerts that can address the following:

  - What your attack looks like from a defender's perspective.
  - How stealthy or detectable your tactics are.
  - Which kinds of alarms and alerts SOC and Incident Response professionals can use to spot these types of attacks while they occur, rather than after.

**Creating Dashboards**

Using the Dashboards the following reports were added:
  - `HTTP status codes for the top queries [Packetbeat] ECS`
  - `Top 10 HTTP requests [Packetbeat] ECS`
  - `Network Traffic Between Hosts [Packetbeat Flows] ECS`
  - `Top Hosts Creating Traffic [Packetbeat Flows] ECS`
  - `Connections over time [Packetbeat Flows] ECS`
  - `HTTP error codes [Packetbeat] ECS`
  - `Errors vs successful transactions [Packetbeat] ECS`
  - `HTTP Transactions [Packetbeat] ECS`

Using the search queries in the Discover screen with packetbeat to answer the following:
  1. Identify the offensive traffic.
  2. Find the request for the hidden directory.
  3. Identify the brute force attack.
  4. Find the WebDAV connection.
  5. Identify the reverse shell and meterpreter traffic.
