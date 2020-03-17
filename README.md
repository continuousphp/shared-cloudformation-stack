# Generic Cloudformation Stack

This reposository regroup a set of stack that aim to be generic as possible.
You can copy / paste them in your Infrastructure project to easily compose modular Infrastructure.

If you need to build a new service that are not in this project, please consider make generic stack and include it in this repository.

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

## Elasticsearch
