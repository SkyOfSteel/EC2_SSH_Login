# EC2_SSH_Login

SSH login to an EC2 instance with PPK or PEM key.

## Login with PuTTY

PuTTY is an SSH client used to connect to remote servers on Windows 8 and earlier. Requires a .PPK file (also able to convert a .PEM file into a .PPK).

1. Download the client from the [website](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html) and install the program.

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

11. Enter the command **whoami** to make sure that you are logged in as **ec2-user** (default EC2 instance user created by AWS).

## Login with Windows PowerShell (Windows 10)

1. Click **Start** and type **PowerShell**, then click **PowerShell** to launch Windows PowerShell.

2. Navigate to the folder containing the .PEM file:

    a. Use **ls** to see the list of files in the current folder.

    b. Use **cd** [Path] to navigate to the folder with the .PEM file, where [Path] is the full path to the folder.

3. Use the command **ssh -i .\File.pem ec2-user@IP-address**, where **.\File.pem** is the name of the .PEM file and **IP-address** is the IP address of the EC2 instance.

    *Note: **-i identity_file** option selects a file from which the identity (private key) for public key authentication is read.*

4. If a prompt appears and asks to confirm the connection to the host, enter **Yes** and press ENTER.

5. In case of an **Unprotected Private Key** error message, navigate to the .PEM file, right-click the file and select **Properties**.

![Illustration](https://github.com/SkyOfSteel/EC2_SSH_Login/blob/main/SSH%20Error%20Message.png "Illustration of the SSH window with error")

6. Select the **Security** tab and click **Advanced**.

7. Click **Disable Inheritance** and choose **Remove all inherited permissions from this object**.

8. Click the **Add** button, then click **Select a principal**.

9. In the field **Enter the object name to select**, enter your Windows user name and click **Check Names** to check if you entered the name correctly.

10. Click **OK**, then under the **Basic Permissions** pane, select the checkbox **Full Control**.

11. Click **OK** to close the **Properties** window. The file will now have only one user on the **Security** tab.

![Illustration](https://github.com/SkyOfSteel/EC2_SSH_Login/blob/main/PEM%20Access%20Properties.png "Illustration of the PEM file properties")

12. In the SSH terminal, enter the command **ssh -i .\File.pem ec2-user@IP-address** again.

![Illustration](https://github.com/SkyOfSteel/EC2_SSH_Login/blob/main/SSH%20Login.png "Illustration of the successful SSH login")