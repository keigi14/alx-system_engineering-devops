# Web Stack Debugging 3

This project is part of the ALX Software Engineering program and focuses on web stack debugging techniques, particularly using `strace` to identify and resolve issues within an Apache web server configuration.

## Description

In this project, we explore debugging techniques for resolving issues causing a 500 Internal Server Error within an Apache web server. We use `strace` to trace system calls made by the Apache process, enabling us to pinpoint the source of the error. Once identified, we manually fix the issue and automate the fix using Puppet.

## Contents

- `0-strace_is_your_friend.pp`: Puppet manifest file containing code to automate the fix for the Apache server.
- `README.md`: This file, providing an overview of the project and instructions.

## Usage

1. **Debugging with `strace`:**
   - Attach `strace` to the running Apache process to trace system calls:
     ```bash
     sudo strace -p $(pidof apache2)
     ```

2. **Identify the Issue:**
   - Analyze the output of `strace` to identify the source of the 500 Internal Server Error within the Apache server configuration.

3. **Manual Fix:**
   - Based on the findings from `strace`, manually fix the issue within the Apache server configuration.

4. **Automating the Fix with Puppet:**
   - Edit the `0-strace_is_your_friend.pp` file to include Puppet code that automates the fix for the identified issue.
   - Apply the Puppet manifest using the following command:
     ```bash
     puppet apply 0-strace_is_your_friend.pp
     ```

## Requirements

- Linux environment
- Apache web server installed
- `strace` utility installed
- Puppet installed

## Contributors

- [Gislain](https://github.com/keigi14)
