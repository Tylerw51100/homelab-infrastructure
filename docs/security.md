# Security 

## Endpoints
- ### Linux endpoints are configured durring initial setup with the following security measures in place:
    - UFW (deny all by default and open ports only as needed)
    - ClamAV
    - Unattended updates via cron and ansiable
    - OS version upgrades via Ansiable

## Network
    ### UniFi gateway
    - VLAN-based network segmentation
    - Firewall rules and traffic isolation
    - IDS/IPS
