## Docker Set Up for Windows 10 home

### Requirements
- Windows-Powershell
- Git Bash

### Steps
1. Install docker-machine in Git Bash:
   
   ``base=https://github.com/docker/machine/releases/download/v0.16.0 &&
   mkdir -p "$HOME/bin" &&
   curl -L $base/docker-machine-Windows-x86_64.exe > "$HOME/bin/docker-machine.exe" &&
   chmod +x "$HOME/bin/docker-machine.exe"``

2. Create Default machine in Git Bash:
   
   ``docker-machine create -d virtualbox --virtualbox-memory=4096     --virtualbox-cpu-count=4 --virtualbox-disk-size=40960     --virtualbox-no-vtx-check default``

3. Enable the WSL 2 feature on Windows:
   
   Follow the instructions of Microsoft: [https://docs.microsoft.com/en-us/windows/wsl/install-win10](url)

4. Get Docker Desktop Installer and run it:

    [https://hub.docker.com/editions/community/docker-ce-desktop-windows/](url)

5. Make sure that the environment variables are compatible with the environment variables of docker-machine:
   
   1. Run ``docker-machine env`` in Git Bash to see the environment variables of the docker-machine.
   2. Run ``Get-ChildItem env:`` in Powershell to get the environment variables of the computer.
   3. Make sure that the Variables **DOCKER_CERT_PATH** and **DOCKER_HOST** have the same values as in the Git Bash.
   4. If not set the values correct with the command ``$env:variable_name=value`` in Powershell.
   


![image](DockerSetUp/../docker.png)