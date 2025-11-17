# Project 2 Documentation
This page describes my steps in completing project 2.
## Procedure

1. Open your VM
2. Go to [docker install](https://docs.docker.com/engine/install/) in Firefox. Scroll down to the table that shows all the platforms and choose the one that best fits your VM
   - Ubuntu is the best fit for my case
   - This will take you to instructions for installing docker
3. Follow the provided instructions:
    - Open a terminal
    - Run the following command `for pkg in docker.io docker-doc docker-compose docker-compose-
v2 podman-docker containerd runc; do sudo apt-get remove $pkg;
done`
   - Install using the apt repository by entering the code from the website:
    `# Add Docker&#39;s official GPG key:`
   `sudo apt-get update`
    `sudo apt-get install ca-certificates curl`
    `sudo install -m 0755 -d /etc/apt/keyrings`
    `sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o`
    `/etc/apt/keyrings/docker.asc`
    `sudo chmod a+r /etc/apt/keyrings/docker.asc`
    `# Add the repository to Apt sources:`
    `echo \`
    ` "deb [arch=$(dpkg --print-architecture) signed-`
    `by=/etc/apt/keyrings/docker.asc]`
    `https://download.docker.com/linux/ubuntu \`
    `$(. /etc/os-release &amp;&amp; echo &quot;${UBUNTU_CODENAME:-`
    `$VERSION_CODENAME}") stable" | \`
    `sudo tee /etc/apt/sources.list.d/docker.list > /dev/null`
   `sudo apt-get update`
    - Install the docker packages with the following command `sudo apt-get install docker-ce docker-ce-cli containerd.io docker-
buildx-plugin docker-compose-plugin`

   - Verify the installation by running the following command 
    `sudo docker run hello-world`  OR
   `docker –version` and `docker compose version`
   
**NOTE:** I recommend copying the code from the website instead of this file. Adding the code into the markup file lead to some discrepancies. 

4. Now that docker is installed, find an application of choice to install 
   - Find a GitHub page that has a compose file already create
    - I chose [nextcloud](https://github.com/docker/awesome-compose/tree/master/nextcloud-postgres)
    - Open a terminal and run the following commands:
     `mkdir lab2` to create the folder for the lab
      `cd lab2` to move into lab2 folder
      `nano compose.yml`
     - Copy and paste the compose file into this file
     - Add ./ in front of the db_data: /var/lib/
     - Press CTRL+O
     - Press CTRL+X
     ![Example](https://raw.githubusercontent.com/brc1075/ArchLinux_Project2/main/images/Image6.png)
 5. At this point, I verified docker and docker compose were installed. I also verified I was in the correct folder:
     `Docker --version`
     `Docker compose version`
     `Pwd`
     `Ls`
 6. Start docker container using the following command:
     - `Sudo docker compose up -d`
     - The -d is to keep it running in the background
     ![example image](https://raw.githubusercontent.com/brc1075/ArchLinux_Project2/main/images/Image1.png)
     ![example image](https://raw.githubusercontent.com/brc1075/ArchLinux_Project2/main/images/Image2.png)
     - Use the command `Sudo docker ps` to see all of the containers running
     - Now the container is up and running!
     ![example](https://raw.githubusercontent.com/brc1075/ArchLinux_Project2/main/images/Image3.png)
  
 7. Locate IP Address
     - Use the command `ip a` to find the VM's IP address
     - Should be in the range of 10.0.#.# if a VM is being used
 8. Test the app is working
     - Open a browser (Firefox in my case)
     - Enter 
     - `http://”youripaddress”/”port” `
     - `http://10.0.#.##:80`
     - Once Nextcloud open, the admin password can be set!
![image](https://raw.githubusercontent.com/brc1075/ArchLinux_Project2/main/images/Image5.png)

![image](https://raw.githubusercontent.com/brc1075/ArchLinux_Project2/main/images/Image4.png)



