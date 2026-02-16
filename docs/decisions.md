# Architecture Decisions (Trade-offs)

## NAT Gateway per AZ

- Decision: Deploy NAT Gateway in each public subnet (one per AZ)
- Why: Avoid single point of failure for outbound patching, package installs, and external API calls
- Trade-off: Higher monthly cost versus a single NAT or NAT instance
- Mitigation: For labs, a single NAT can be used with explicit acknowledgment of reduced HA

## Public ALB + Internal ALB

- Decision: Use two ALBs to enforce tier boundaries
- Why: Web tier and App tier isolation, stronger security model, better blast-radius control
- Trade-off: More configuration and another hop
- Benefit: Easier policy enforcement and clearer operational ownership boundaries

## RDS Multi-AZ

- Decision: Managed database failover rather than self-managed replication
- Why: Operational simplicity, predictable failover, managed patching
- Trade-off: Less fine-grained replication control
