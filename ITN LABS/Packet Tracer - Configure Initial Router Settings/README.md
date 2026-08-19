<h2> Packet Tracer - Configure Initial Router Settings</h2>

## Overview
This lab covers basic router configuration tasks including securing CLI and console access, configuring banner messages, and saving running configurations.

## Objectives
- Part 1: Verify the Default Router Configuration
- Part 2: Configure and Verify the Initial Router Configuration
- Part 3: Save the Running Configuration File

## Part 1: Verify the Default Router Configuration

### Step 1: Establish Console Connection
1. Choose Console cable from available connections
2. Connect PCA RS 232 port to R1 Console port
3. Open Terminal from PCA Desktop tab
4. Press ENTER to begin configuration

### Step 2: Examine Current Configuration
Enter privileged EXEC mode and view the running configuration.

Commands:
```
Router> enable
Router# show running-config
Router# show startup-config
```

## Part 2: Configure and Verify the Initial Router Configuration

### Step 1: Configure Initial Settings

Configure the following on R1:

1. **Hostname**: R1
2. **Message of the day banner**: Unauthorized access is strictly prohibited.
3. **Passwords**:
   - Privileged EXEC (unencrypted): cisco
   - Privileged EXEC (encrypted): itsasecret
   - Console: letmein
4. **Enable password encryption** for all passwords using service password-encryption

### Step 2: Verify Settings

Verify the configuration has been applied correctly:

```
Router# show running-config
```

Exit the console session and reconnect to verify the banner and password prompts are working as configured.

## Part 3: Save the Running Configuration File

### Step 1: Save Configuration to NVRAM

Back up the running configuration to NVRAM to preserve changes during reboot or power loss:

```
Router# copy running-config startup-config
```

Or use the shortest unambiguous version of this command.

### Step 2: Optional - Save Startup Configuration to Flash

Examine flash memory contents:

```
R1# show flash
```

Copy startup configuration to flash as an additional backup:

```
R1# copy startup-config flash
```

Accept the default filename or enter a custom name when prompted.

Verify the file was saved:

```
R1# show flash
```

## Equipment Required
- Cisco Packet Tracer
- Router (R1)
- PC (PCA)
- Console cable

## Key Commands Summary
- `enable` - Enter privileged EXEC mode
- `show running-config` - Display active configuration
- `show startup-config` - Display saved configuration in NVRAM
- `show flash` - Display flash memory contents
- `copy running-config startup-config` - Save configuration to NVRAM
- `copy startup-config flash` - Backup startup config to flash

## Configuration Tasks
- Set hostname
- Configure MOTD banner
- Set enable password (unencrypted)
- Set enable secret password (encrypted)
- Set console password
- Enable password encryption service
