# Teardown Checklist (Cost Control)

If you implement this architecture in AWS, delete resources in a safe order:

1. Delete ALBs and target groups
2. Delete Auto Scaling Groups (terminate instances)
3. Delete NAT Gateways (releases EIPs)
4. Delete RDS (ensure snapshots as needed)
5. Delete route tables, subnets, and VPC
6. Verify no orphaned EIPs, ENIs, or load balancers remain
