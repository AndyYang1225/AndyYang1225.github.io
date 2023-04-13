---
title: Bash Variables
weight: 210
menu:
  notes:
    name: Variables
    identifier: notes-bash-variables
    parent: notes-bash
    weight: 10
---

<!-- Variable -->
{{< note title="Variable" >}}

```bash
NAME="John"
echo $NAME
echo "$NAME"
echo "${NAME}
```

{{< /note >}}

<!-- Condition -->
{{< note title="Condition" >}}

```bash
if [[ -z "$string" ]]; then
  echo "String is empty"
elif [[ -n "$string" ]]; then
  echo "String is not empty"
fi
```
{{< /note >}}

{{<note title="Unlearned">}}
```bash
rust functional programming
MERGE into
bash進階： awk; sed; find  -exec 
docker
docker-compose
LPI Linux 第一級資格檢定 第三版
virtualbox
nbuntu 22.04 

k8s 


```
  {{< /note >}}
{{note title="vm docker"}}
Uninstall old versions
```bash
sudo apt-get remove -y docker docker-engine docker.io containerd runc
```

Update the apt package index and install packages to allow apt to use a repository over HTTPS
```bash
sudo apt-get update
sudo apt-get install -y \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
```
Add Docker’s official GPG key
```bash
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

set up the stable repository
```bash
echo \
  "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
 ```

 # Install Docker Engine
```bash
sudo apt-get update
sudo apt-get install -y docker-ce docker-ce-cli containerd.io
 ```

downloads a test image and runs it in a container. When the container runs, it prints a message and exits
 ```bash
sudo docker run hello-world
 ```

docker 只有 root 或 docker 群組能夠使用/var/run/docker.sock 的權限，把當前使用者加到 docker 群組
 ```bash
sudo usermod -aG docker ${USER}
 ```
登出再登入

```
{{< /note >}}



