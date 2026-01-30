# Born2beRoot

## Description
Born2beRoot is a system administration project in the 1337 (42 Network) curriculum. It introduces students to the fundamentals of system administration by setting up a virtual machine with specific security and configuration requirements.

This project teaches:
- Virtual machine setup and management
- Linux system administration basics
- Security hardening practices
- User and group management
- Service configuration (SSH, UFW)
- LVM (Logical Volume Manager) setup

## Usage

### System Configurations

#### LVM (Logical Volume Manager)
The project requires setting up encrypted partitions using LVM:

**Configuration Details:**
- **Physical Volumes**: `/dev/sda`
- **Volume Group**: `LVMGroup`
- **Logical Volumes**:
  - `root` - 10GB (System root partition)
  - `swap` - 2GB (Swap space)
  - `home` - 5GB (User home directories)

**Verification Commands:**
```bash
# Display physical volumes
sudo pvdisplay

# Display volume groups
sudo vgdisplay

# Display logical volumes
sudo lvdisplay
```

#### SSH Configuration
SSH service configured for secure remote access:

**Key Settings:**
- **Port**: `4242` (Non-standard port for security)
- **PermitRootLogin**: `no` (Disabled for security)
- **PasswordAuthentication**: `yes` (Enabled as per requirements)

**Configuration File**: `/etc/ssh/sshd_config`

**Verification Commands:**
```bash
# Check SSH service status
sudo systemctl status ssh

# View SSH configuration
sudo cat /etc/ssh/sshd_config | grep -E "Port|PermitRootLogin|PasswordAuthentication"

# Connect to SSH
ssh username@localhost -p 4242
```

#### UFW (Uncomplicated Firewall)
Firewall configured to control network traffic:

**Configuration:**
- **Status**: Active
- **Default Policy**: 
  - Incoming: Deny
  - Outgoing: Allow
- **Allowed Ports**:
  - `4242/tcp` - SSH access
  - `80/tcp` - HTTP (if web server enabled)
  - `443/tcp` - HTTPS (if web server enabled)

**Verification Commands:**
```bash
# Check UFW status
sudo ufw status

# View detailed rules
sudo ufw status verbose

# List numbered rules
sudo ufw status numbered
```

### Additional Requirements

#### User Management
```bash
# Check current user groups
groups username

# Check password policy
sudo chage -l username

# View sudo configuration
sudo visudo
```

#### System Monitoring
The project typically requires a monitoring script that displays:
- System architecture
- CPU information
- Memory usage
- Disk usage
- Network information
- Active connections

## Project Files
- `configs.txt` - Contains sample configurations for LVM, SSH, and UFW
- `monitoring.sh` - System monitoring script (if implemented)
- `signature.txt` - VM signature file for evaluation

## Evaluation Notes
During evaluation, the following will be checked:
- Proper LVM partition setup
- SSH configuration and functionality
- UFW rules and firewall status
- Password policies
- Sudo configuration
- User and group management
- Monitoring script functionality