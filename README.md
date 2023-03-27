1. Make sure that Docker Desktop is installed by following this link:  https://docs.docker.com/get-docker/. If you have Docker Desktop installed, skip to Step 5

2. After installing make sure to create a Docker account and sign in to your Docker Desktop. Then, open VS Code and install the extension for Docker by Microsoft.

3. If you're using Windows, install Ubuntu.
    - after installing Ubuntu, restart your computer.
    - then, open cmd, type: bcdedit /set hypervisorlaunchtype auto, restart your computer.
    - after restarting, go to Search and type "Turn Windows features on or off".
    - check the "Virtual Machine Platform" and "Windows Subsystem for Linux", restart your computer.
    - after that, open Docker, go to: Settings > General, select the "Use WSL 2 based engine"
    - then go to "Resources" and select "Enable integration with my default WSL distro", make sure to also enable the "Ubuntu", click "Apply and Restart".
    - click start, type "\\wsl$", this should open a new explorer showing folders, go to: Ubuntu > home > [yourname]. This is where you will paste this project.
    - next, open cmd, type "wsl", this will change the command prompt into linux terminal.
    - type code /home/[yourname]/dockerize-express-master. this should open VS Code. 
    - first, install the Docker extension by Microsoft to easily manage the containers, images, volumes etc.

4. If you're on Mac just follow step 2 and open VS Code.

5. Now that we have finished setting up and opened VS Code, right click the "docker-compose.yml", select "compose up". This should create the container and images. Open the Docker extension, you should see dockerize-express-master and mysql below the CONTAINERS. It should have a green play button on the left.

6. In order to use the database, we should connect it to Workbench. Open Workbench, click the "+" sign beside MySQL Connections.
    - in the Connection Name field, type any name for the connection.
    - in the Hostname field if 127.0.0.1 didn't work, type the WSL IPv4 address instead (open terminal, type "ipconfig", find Ethernet adapter vEthernet (WSL))
    - open docker-compose.yml and find "db", on the ports, copy the port on the left and paste it to the Port field on Workbench.
    - Username: root
    - Password: password
    - Default Schema: hh
    - Click Test Connection to ensure that it connects to our database.

7. Go to browser, type localhost:3001. The application should now be running.