# Group-4-Cap-Stone-Project-
. Secure File Transfer Service 
Introduction
The purpose of this project was to design and implement a secure, automated mechanism for transferring files from a Virtual Machine (VM) to a cloud droplet. The solution had to meet requirements in networking, security, scripting, and cloud deployment. Specifically, the project leverages scp and rsync for data transfer, SSH keys for authentication, firewall rules for access control, and a Bash script with logging and error handling for automation.

This report presents the methodology used, the implementation details, security configurations, and verification through logs and screenshots. The final deliverables include the transfer script, project documentation, and system configuration screenshots.
Skills Applied
1. Networking (Week 4): Configured secure file transfer using scp and rsync. Verified connectivity between the VM and the droplet using SSH. Implemented a pre-flight connectivity check in the script.
2. Security (Week 5): Generated and deployed SSH key pairs to replace password authentication. Hardened SSH settings by editing /etc/ssh/sshd_config to disable root login and password-based authentication. Configured UFW (Uncomplicated Firewall) to allow SSH only from the VM’s public IP address.
3. Scripting (Week 6): Created transfer_files.sh to automate file transfers. Implemented robust error handling with set -euo pipefail. Logged all transfer attempts to ~/myproject/logs/transfer.log. Added alerting mechanisms to notify on failures.
4. Cloud (Week 7): Prepared the droplet with a dedicated user (deploy). Set up appropriate directory permissions (/srv/inbox). Verified firewall and SSH configurations on the cloud host.
Implementation
1. Script: transfer_files.sh – A Bash script was developed to automate the secure transfer of files. Key features include configurable parameters, support for both rsync and scp, logging, error handling, and optional alerts.
2. SSH Key Authentication – SSH keys were generated and copied to the droplet’s authorized_keys. Root login and password authentication were disabled to reduce attack surface.
3. Firewall Configuration (UFW) – The droplet firewall was configured to allow SSH only from the VM’s IP, enhancing security.
4. Documentation – A README was prepared describing SSH setup, UFW configuration, and script usage.
5. Verification Screenshots – Screenshots included transfer logs and UFW status.
Results
The project resulted in a robust file transfer system with secure authentication using SSH keys, hardened droplet access with firewall rules, and automated file transfer through a reusable Bash script. Logs and alerts provided auditing and monitoring capabilities. The solution successfully demonstrated secure file transfer from VM to cloud droplet.
Conclusion
This project demonstrated the integration of networking, security, scripting, and cloud concepts into a practical solution for secure file transfers. By combining rsync/scp with SSH key authentication, firewall hardening, and a scripted workflow, a reliable and secure pipeline was created.

The deliverables—script, documentation, and screenshots—provide a reproducible and auditable method for transferring files between a VM and a cloud droplet. The successful outcome reinforces best practices in secure system administration and cloud deployment.
Deliverables Submitted
- ~/myproject/scripts/transfer_files.sh
- ~/myproject/docs/project_readme.md
- Screenshots: tail transfer.log, sudo ufw status
- (Optional) GitHub repository
