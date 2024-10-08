# Fast File Transfer Protocol (FFTP)
**Alexis Leclerc**

**08/24/2024**

**Version 1.0.0**
## Overview

**Fast File Transfer Protocol (FFTP) is a secure, efficient, and feature-rich protocol designed to handle large data and file transfers over the network. Built to compete with established protocols like SFTP, FTP, and SSH, FFTP provides robust security through SSL/TLS encryption, system-level authentication, remote command execution, and concurrent file transfers. This protocol is ideal for system administrators, developers, and anyone needing secure and fast file transfers.**

## Features

- **Secure Communication**: Utilizes SSL/TLS for end-to-end encryption, ensuring that all data transferred between the client and server is secure.
- **System-Level Authentication**: Authenticates users against the system's user database and shadow passwords, offering strong security similar to SSH.
- **Remote Command Execution**: After authentication, users can execute bash commands remotely, and the server will send back the command output.
- **File Transfer**: Supports secure file transfers with basic functionality for sending and receiving files.
- **Concurrency**: Capable of handling multiple client connections simultaneously via multi-threading, ensuring efficient processing of multiple requests.
- **Logging**: Logs all user activities, including command executions and file transfers, for audit and security purposes.
- **Cross-Platform Compatibility**: Designed to work on POSIX-compliant operating systems (Linux, Unix-based systems).

## Architecture

**The FFTP consists of two main components:**

1. **FFTP Server**: Handles client connections, authentication, command execution, and file transfers. It listens on a specified port and manages multiple client connections concurrently.
2. **FFTP Client**: Connects to the FFTP server, authenticates the user, and sends commands or requests for file transfers.

## Installation

### Prerequisites

**Before you begin, ensure you have the following installed on your system:**

- **OpenSSL**: Required for SSL/TLS encryption.
- **GCC** or any other C compiler.
- **POSIX-compliant OS**: Linux/Unix-based system.

### Compilation

**To compile the server and client programs, use the following commands:**

```bash
gcc -o fftp_server server.c -lssl -lcrypto -lpthread
gcc -o fftp_client client.c -lssl -lcrypto -lpthread
```

## Usage

**To start the FFTP server, run:**
```bash
./fftp_server
```

**To connect to the FFTP server, run the client program:**
```bash
./fftp_client
```

**To download a file from the server, use the following command after successful authentication:**
```bash
send_file /path/to/remote/file.txt
```

**To upload a file to the server, use the following command after successful authentication:**
```bash
get_file /path/to/remote/file.txt
```

**After successful authentication, you can execute any bash command remotely. For example:**
```bash
ls -l /home/user
```

**To exit the session, simply type:**
```bash
exit
```


### Summary

The scripts now fully support file upload (`send_file`) and file download (`get_file`) functionalities, along with command execution and logging. The `README.md` has been updated to reflect these new commands and provide clear instructions for usage.
