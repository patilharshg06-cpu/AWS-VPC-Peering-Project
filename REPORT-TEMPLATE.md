# AWS VPC Peering – Project Report Template

**Student:** Harshwardhan Ganesh Patil  
**Batch:** [Enter your batch]  
**Project:** AWS VPC Peering – Private Connectivity Between Two VPCs  
**AWS Region:** ap-southeast-2 (Sydney)  
**Date:** [Enter submission date]

## 1. Aim
To connect two Amazon VPCs using VPC Peering and verify private communication between two EC2 application servers.

## 2. Architecture
Insert the repository's `architecture.png` diagram. Explain that VPC A contains a public bastion subnet and a private application subnet, while VPC B contains a private application subnet. The two VPCs communicate through the peering connection.

## 3. Resource inventory
Fill in actual IDs and actual private IP addresses from the AWS Console.

| Resource | Name | Actual ID / IP |
|---|---|---|
| VPC A | ewb-vpc-a | [Fill in VPC ID] |
| VPC B | ewb-vpc-b | [Fill in VPC ID] |
| Peering | ewb-a-b-peer | [Fill in pcx ID; verify Active] |
| Bastion | ewb-bastion | Private IP 10.10.1.80 reported; add public IP privately only if needed |
| App-A | ewb-app-a | [Verify actual private IP] |
| App-B | ewb-app-b | [Verify actual private IP] |

## 4. Subnets and route tables
Record each subnet CIDR, route table association, and every route (including local routes). Add genuine screenshots.

## 5. Security groups
Record the inbound rules for the bastion and both app servers. Show restricted SSH sources and the ICMP rules. Do not expose personal public IP unnecessarily in a public report.

## 6. Implementation
Describe VPC creation, subnet creation, route table associations, Internet Gateway attachment, EC2 launch, security group setup, VPC Peering acceptance, and route configuration.

## 7. Testing evidence – fill only after running each test
| Test | Command / action | Actual result | Screenshot |
|---|---|---|---|
| Baseline before peering | App-A: ping App-B | [Record actual result] | [Filename] |
| Forward ping | App-A to App-B private IP | [Record actual result] | [Filename] |
| Reverse ping | App-B to App-A private IP | [Record actual result] | [Filename] |
| SSH via bastion | Laptop to App-B through bastion | [Record actual result] | [Filename] |
| Controlled failure | Temporarily remove App-B ICMP inbound rule | [Record actual result] | [Filename] |
| Recovery | Restore ICMP rule and repeat ping | [Record actual result] | [Filename] |

Do not write that a test passed unless the terminal output proves it.

## 8. Forward and return path
Explain that the source subnet route table forwards traffic for the other VPC CIDR to the VPC Peering connection. The destination VPC route table needs a route back to the source VPC CIDR. Security groups must allow the traffic in the required direction.

## 9. Learning outcomes
Write what you learned about CIDR planning, subnet associations, route tables, peering, security groups, bastion access, and testing private connectivity.

## 10. Cleanup
After saving all evidence, record termination of the three EC2 instances and removal of lab-only networking resources. Include screenshots only after cleanup has actually been completed.

## 11. Conclusion
Summarize the actual result of your tests. Clearly state any tests that remain incomplete.
