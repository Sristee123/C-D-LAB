<h2 align="center"> Experiment-1 : VM vs Container </h2>


#### PART-A:- Virtual Machine (Windows)
<hr>

**Step 1: Download Virtual Box from [here](https://www.virtualbox.org/wiki/Downloads)**
![Download VM](./Experiment-1/images/0.png)

**Step 2: Download Vagrant from [here](https://developer.hashicorp.com/vagrant/install)**
![Download Vagrant](./Experiment-1/images/1.png)


**Step 3: To verify the installation we will check the version via following command**
``` bash
vagrant --version
```
![Version Check](./Experiment-1/images/2.png)


**Step 4: Initialize Vagrant with Ubuntu box:**
```bash
vagrant init hashicorp/bionic64
```
![Initialize](./Experiment-1/images/3.png)


**Step 5: Start the VM:**
   ```bash
   vagrant up
   ```
![Vagrant up](./Experiment-1/images/4.png)


**Step 6: Access the VM:**
```bash
vagrant ssh
```
![ssh](./Experiment-1/images/5.png)


**Step 7: Install Nginx inside VM**
```bash
sudo apt update
sudo apt install -y nginx
sudo systemctl start nginx
```
![Install Nginx inside VM](./Experiment-1/images/6.png)
![Install Nginx inside VM](./Experiment-1/images/7.png)

**Step 8: Verify Nginx**
```bash
curl localhost
``` 
![Verify Nginx](./Experiment-1/images/8.png)


**Step 9: Utilization Matrix In Running State**
![Running State Matrix](./Experiment-1/images/9.png)


**Step 10: Stop VM**
```bash
vagrant halt
```
![Halt Vagrant](./Experiment-1/images/10.png)


**Step 11: Utilization Matrix In Stop State**
![Stop State Matrix](./Experiment-1/images/11.png)


**Step 12: Remove VM**
```bash
vagrant destroy
```
![Vagrant Deleted](./Experiment-1/images/12.png)




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
![Verify Docker](./Experiment-1/images/13.png)


**Step 5: Pull Ubuntu Image**
```bash
docker pull ubuntu
```
![Ubuntu Image](./Experiment-1/images/14.png)


**Step 6: Run Ubuntu Container with Nginx**
```bash
docker run -d -p 8080:80 --name nginx-container nginx
```
![Run ubuntu with nginx](./experiment-1/images/15.png)


**Step 7: Verify Nginx in Container**
```bash
curl localhost:8080
```
![Verify nginx](./Experiment-1/images/16.png)


**Step 8: Container Observation Commands**
```bash
docker stats
free -h
```
![Utilization Matrix](./Experiment-1/images/17.png)
![Utilization Matrix](./Experiment-1/images/18.png)


**Parameters to Compare**

| Parameter    | Virtual Machine | Container |
| ------------ | --------------- | --------- |
| Boot Time    | High            | Very Low  |
| RAM Usage    | High            | Low       |
| CPU Overhead | Higher          | Minimal   |
| Disk Usage   | Larger          | Smaller   |
| Isolation    | Strong          | Moderate  |
