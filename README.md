
# Inter-Subnet Routing Lab

# Overview
This lab demonstrates communication between four Linux hosts across two subnets using Containerlab and a Linux router.

# Network Topology
```text
Subnet A (192.168.10.0/24)
  host-a1: 192.168.10.2
  host-a2: 192.168.10.3
          |
       switch-a
          |
        Router
   eth1: 192.168.10.1
   eth2: 192.168.20.1
          |
       switch-b
          |
  host-b1: 192.168.20.2
  host-b2: 192.168.20.3
Subnet B (192.168.20.0/24)
```

# Setup
Requires Docker and Containerlab.

sudo containerlab deploy -t topology.yaml


# Verify YAML
Requires Python 3 and PyYAML.


python3 -c "import yaml; yaml.safe_load(open('topology.yaml')); print('Valid YAML')"


# Test Connectivity
sudo docker exec clab-inter-subnet-host-a1 ping -c 4 192.168.20.2


Result: 4 packets received, 0% packet loss.

## Destroy Lab
sudo containerlab destroy -t topology.yaml


## Author
Taiwo Ajose
Loyalist College
