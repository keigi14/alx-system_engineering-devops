**0x19-postmortem**

![I WILL FIND YOU AND I WILL FIX YOU](https://miro.medium.com/max/1400/0*kHoWD7gJ0PC9GmBK.jpg)
**Issue Summary:**

- **Duration:** The outage occurred from 03:00 to 05:30 UTC.
Impact: The 30% error rate increment received late response and therefore demoralized the way people perceived the web application.

**Root Cause:**

This was caused by a misconfiguration setting inside the load balancer, leading to inconsistencies in the traffic distributed among the servers.

**Timeline:**

- 03:00 UTC: The issue was detected when monitoring alerts indicated a spike in error rates and latency.
- The issue was initially noticed by the on-call engineer who received automated alerts regarding server errors.
Back-end servers were requisitioned for testing the network; performance of the application was checked rigorously.
The other tangential lines of investigation were the performance of the database, and checking the application code for errors. There were made no big sudden moments of revelation.
- The incident was escalated to the DevOps team and senior engineers for further analysis and resolution.

**Resolution:**

Investigation further reveals that during one of the routine maintenance work or activity, the configuration of load balancer was done somewhat wrongly doing so; which continued to provide the imperfect distribution of incoming requests.
The Load Balancer got reconfigured back to what it was before, and the same fix got rolled out across the infrastructure.
Also, additional monitoring checks have been put on to inform or warn, in case, any future change is done in the load balancer configuration or, if the God forbids, the issue has happened again.

**Corrective and Preventative Measures:**

- Improve change management processes to prevent accidental misconfigurations during maintenance activities.
Tighten access control and permission to key or core components of infrastructure to reduce the risk of unauthorized change. - Conduct regular audits of load balancer configurations to identify and rectify any discrepancies.

Review and update the change management policy to include mandatory peer reviews for all infrastructure modification. Task: Enable automated backup of load balancer configuration for fast restoration in case of accidental changes. Configuration Validation - New monitoring that enhances the capability to provide real-time visibility on changes of the configuration and the performance of the load balancer. This then serves as a testimony that solid change management practice, coupled with proactiveness in regards to monitoring, happen to be key worthy elements that would maintain availability and reliability of our web services. We would expect such downtimes to be reduced and our mode of service delivery improved through the effective implementation of the identified corrective measures and the lessons learned from this incident.
