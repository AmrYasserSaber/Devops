# Devops Task 2

## Description

This project involves creating a new user named `devops` for the Devops team.

## Steps

1. **Add User:**
   - Use the `sudo adduser devops` command to create the new user.
   - Provide a new password for the user when prompted.
   - Confirm the user information (full name, room number, work phone, home phone).

2. **Verify:**
   - Check the user information by running `cat /etc/passwd` to verify the user's details.

3. **Creating a script.sh file:**
   - Create a new file named `script.sh` in the `/home/devops` directory.
   - Add the following content to the file:
     ```bash
     #!/bin/bash
     echo "Hello, Devops Team!"
     ```
4. **Change Permissions:**
   - Change the permissions of the `script.sh` file to make it executable.
   - Run the following command: `sudo chmod +x /home/devops/script.sh`.
   - Verify the permissions by running `ls -l /home/devops/script.sh`.
   - Run the script by executing `/home/devops/script.sh`.
   - Verify that the script prints `Hello, Devops Team!`.

5. **Zip the script:**
   - Create a zip file named `task.zip` containing the `task` directory.
   - Run the following command: `sudo zip /home/devops/task.zip /home/devops/task`.
   - Verify that the zip file has been created by running `ls /home/devops`.


## Dependencies
- sudo privileges
## Usage
1. Open a terminal window.
2. Navigate to the project directory.
3. Run the following command: 
   ```bash
   sudo adduser devops
4. Follow the prompts to create the new user.
5. Verify the user information by running `cat /etc/passwd`.
6. Create the `script.sh` file in the `/home/devops` directory.
7. Run the following command to change the permissions of the script file:
   ```bash
   sudo chmod +x /home/devops/script.sh
   ```
8. Add the script content to the file.
9. Run the script by executing `/home/devops/script.sh`.
10. Verify that the script prints `Hello, Devops Team!`.
11. Create a zip file named `task.zip` containing the `task` directory.
12. Run the following command: `sudo zip /home/devops/task.zip /home/devops/task`.
13. Verify that the zip file has been created by running `ls /home/devops`.
