# EC2_SSH_Login

SSH login to an EC2 instance with PPK or PEM key.

## Login with PuTTY

PuTTY is an SSH client used to connect to remote servers on Windows 8 and earlier. Requires a .PPK file (also able to convert a .PEM file into a .PPK).

1. Download the client from https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html and install the program.

2. (Optional) For a .PEM key, open PuTTY Key Generator from the program folder, click **Load** to load the file, then **Generate** to generate a .PPK, then **Save private key**.

3. For a .PPK key, open the PuTTY app.

4. In the  **Host Name** box, enter **ec2-user@IP-address**, where IP-address is the IP address of the EC2 instance.

5. Enter the name of the session and save it.

![Illustration](https://github.com/SkyOfSteel/EC2_SSH_Login/blob/main/PuTTY%20Illustration.png "Illustration of the PuTTY window")

6. On the left panel, click **+** next to the tab **SSH**.

7. Click the tab **Auth** to open the options for controlling SSH authentication.

8. In the right pane, click **Browse** and select the generated .PPK file.

9. After opening the .PPK file, return to the tab **Session** and save it.

10. Click **Open**. The remote terminal will appear.

![Illustration](https://github.com/SkyOfSteel/EC2_SSH_Login/blob/main/PuTTY%20Illustration%202.png "Illustration of the terminal window")