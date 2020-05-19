## Network

Network folder must contain stack associate to Networking related services.

- VPC : Able to create SDN with Public / Private subnets in many availability zone with ou without NAT Gateway for giving Internet Access to private subnet

```
              VPC
              +---------------------------------------+
              |   Public Subnet Zone X                |
     +--+     |   +---------------+                   |
     |IG|---------|--           -------|   +--------+ |
     +--+     |   +---------------+    -----DynamoDB| |
              |                        |   |Endpoint| |
              |                        |   +--------+ |
              |   Private Subnet Zone X|              |
              |   +---------------+    |   +--------+ |
     +---+    |   | +---+         |    -----S3      | |
     |EIP|----------|NAT|       -------+   |Endpoint| |
     +---+    |   | +---+         |        +--------+ |
              |   +---------------+                   |
              +---------------------------------------+
```
