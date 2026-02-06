<<<<<<< HEAD
<h2 align="center"> Experiment-1 : VM vs Container </h2>


#### PART-A:- Virtual Machine (Windows)
<hr>

**Step 1: Download Virtual Box from [here](https://www.virtualbox.org/wiki/Downloads)**
![Download VM](./images/0.png)

**Step 2: Download Vagrant from [here](https://developer.hashicorp.com/vagrant/install)**
![Download Vagrant](./images/1.png)


**Step 3: To verify the installation we will check the version via following command**
``` bash
vagrant --version
```
![Version Check](./images/2.png)


**Step 4: Initialize Vagrant with Ubuntu box:**
```bash
vagrant init hashicorp/bionic64
```
![Initialize](./images/3.png)


**Step 5: Start the VM:**
   ```bash
   vagrant up
   ```
![Vagrant up](./images/4.png)


**Step 6: Access the VM:**
```bash
vagrant ssh
```
![ssh](./images/5.png)


**Step 7: Install Nginx inside VM**
```bash
sudo apt update
sudo apt install -y nginx
sudo systemctl start nginx
```
![Install Nginx inside VM](./images/6.png)
![Install Nginx inside VM](./images/7.png)

**Step 8: Verify Nginx**
```bash
curl localhost
``` 
![Verify Nginx](./images/8.png)


**Step 9: Utilization Matrix In Running State**
![Running State Matrix](./images/9.png)


**Step 10: Stop VM**
```bash
vagrant halt
```
![Halt Vagrant](./images/10.png)


**Step 11: Utilization Matrix In Stop State**
![Stop State Matrix](./images/11.png)


**Step 12: Remove VM**
```bash
vagrant destroy
```
![Vagrant Deleted](./images/12.png)




#### PART-B:- Containers using WSL (Windows)
<hr>

**Step 1: Install WSL**
```powershell
wsl --install
```
Reboot the system after installation.


**Step 2: Install Ubuntu on WSL**

```powershell
wsl --install -d Ubuntu
```


**Step 3: Install Docker Engine inside WSL**

```bash
sudo apt update
sudo apt install -y docker.io
sudo systemctl start docker
sudo usermod -aG docker $USER
```
Logout and login again to apply group changes.

**Step 4: Verify Docker Installation**

```bash
docker --version
```
![Verify Docker](./images/13.png)


**Step 5: Pull Ubuntu Image**
```bash
docker pull ubuntu
```
![Ubuntu Image](./images/14.png)


**Step 6: Run Ubuntu Container with Nginx**
```bash
docker run -d -p 8080:80 --name nginx-container nginx
```
![Run ubuntu with nginx](./images/15.png)


**Step 7: Verify Nginx in Container**
```bash
curl localhost:8080
```
![Verify nginx](./images/16.png)


**Step 8: Container Observation Commands**
```bash
docker stats
free -h
```
![Utilization Matrix](./images/17.png)
![Utilization Matrix](./images/18.png)


**Parameters to Compare**

| Parameter    | Virtual Machine | Container |
| ------------ | --------------- | --------- |
| Boot Time    | High            | Very Low  |
| RAM Usage    | High            | Low       |
| CPU Overhead | Higher          | Minimal   |
| Disk Usage   | Larger          | Smaller   |
| Isolation    | Strong          | Moderate  |
=======
<h2 align="center"> Experiment-1 : VM vs Container </h2>


#### PART-A:- Virtual Machine (Windows)
<hr>

**Step 1: Download Virtual Box from [here](https://www.virtualbox.org/wiki/Downloads)**
![Download VM](./images/0.png)

**Step 2: Download Vagrant from [here](https://developer.hashicorp.com/vagrant/install)**
![Download Vagrant](./images/1.png)


**Step 3: To verify the installation we will check the version via following command**
``` bash
vagrant --version
```
![Version Check](./images/2.png)


**Step 4: Initialize Vagrant with Ubuntu box:**
```bash
vagrant init hashicorp/bionic64
```
![Initialize](./images/3.png)


**Step 5: Start the VM:**
   ```bash
   vagrant up
   ```
![Vagrant up](./images/4.png)


**Step 6: Access the VM:**
```bash
vagrant ssh
```
![ssh](./images/5.png)


**Step 7: Install Nginx inside VM**
```bash
sudo apt update
sudo apt install -y nginx
sudo systemctl start nginx
```
![Install Nginx inside VM](./images/6.png)
![Install Nginx inside VM](./images/7.png)

**Step 8: Verify Nginx**
```bash
curl localhost
``` 
![Verify Nginx](./images/8.png)


**Step 9: Utilization Matrix In Running State**
![Running State Matrix](./images/9.png)


**Step 10: Stop VM**
```bash
vagrant halt
```
![Halt Vagrant](./images/10.png)


**Step 11: Utilization Matrix In Stop State**
![Stop State Matrix](./images/11.png)


**Step 12: Remove VM**
```bash
vagrant destroy
```
![Vagrant Deleted](./images/12.png)




#### PART-B:- Containers using WSL (Windows)
<hr>

**Step 1: Install WSL**
```powershell
wsl --install
```
Reboot the system after installation.


**Step 2: Install Ubuntu on WSL**

```powershell
wsl --install -d Ubuntu
```


**Step 3: Install Docker Engine inside WSL**

```bash
sudo apt update
sudo apt install -y docker.io
sudo systemctl start docker
sudo usermod -aG docker $USER
```
Logout and login again to apply group changes.

**Step 4: Verify Docker Installation**

```bash
docker --version
```
![Verify Docker](./images/13.png)


**Step 5: Pull Ubuntu Image**
```bash
docker pull ubuntu
```
![Ubuntu Image](./images/14.png)


**Step 6: Run Ubuntu Container with Nginx**
```bash
docker run -d -p 8080:80 --name nginx-container nginx
```
![Run ubuntu with nginx](./images/15.png)


**Step 7: Verify Nginx in Container**
```bash
curl localhost:8080
```
![Verify nginx](./images/16.png)


**Step 8: Container Observation Commands**
```bash
docker stats
free -h
```
![Utilization Matrix](./images/17.png)
![Utilization Matrix](./images/18.png)


**Parameters to Compare**

| Parameter    | Virtual Machine | Container |
| ------------ | --------------- | --------- |
| Boot Time    | High            | Very Low  |
| RAM Usage    | High            | Low       |
| CPU Overhead | Higher          | Minimal   |
| Disk Usage   | Larger          | Smaller   |
| Isolation    | Strong          | Moderate  |
>>>>>>> 36140c9 (Updated main README and added Experiment-2 folder)
