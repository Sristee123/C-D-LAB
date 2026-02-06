## Experiment 2:- Docker Installation, Configuration, and Running Images

**Step 1: Pull Image**

```bash
docker pull nginx
```
![Check Version](./images/1.png)


**Step 2: Run Container with Port Mapping**

```bash
docker run -d -p 8080:80 nginx
```
![Run nginx container](./images/2.png)


**Step 3: Verify Running Containers**

```bash
docker ps
```
![Verify container](./images/3.png)


**Step 4: Stop Container**

```bash
docker stop <container_id>
```
![Stop Container](./images/4.png)


**Step 5: Remove Container**

```bash
docker rm <container_id>
```
![Remove Container](./images/5.png)


**Step 5: Remove Image**

```bash
docker rmi nginx
```
![Remove Images](./images/6.png)


**Result**
Docker images were successfully pulled, containers executed, and lifecycle commands performed.