# Kaseya AiTM Workshop Reference Guide
Please don't skip ahead!


## Signing into your VPS
```bash
# Syntax ssh <username>@<external IP of your server>
ssh root@192.192.129.192

# Confirming you have root access
whoami
```

## Cloning GitHub Repositories
```bash
# Cloning the Evilginx 3 
git clone https://github.com/bjones-saasalerts/evilginx3/

# Cloning the Evilginx 3 Phishlets
git clone https://github.com/bjones-saasalerts/phishlets
```

## Installing the correct version of Go
```bash
# Download version 1.19
wget https://go.dev/dl/go1.19.linux-amd64.tar.gz

# Extract go into the correct folder
tar -zxvf go1.19.linux-amd64.tar.gz -C /usr/local/

# Adding the path for go to be able to execute
echo "export PATH=/usr/local/go/bin:${PATH}" | sudo tee /etc/profile.d/go.sh

# Making sure linux knows where to find go
source /etc/profile.d/go.sh
```

## Time to make Evilginx Server
```bash
# Update your apt information
apt update

# Installing make
apt install make -y

#Change directory into the Evilginx folder
cd evilginx3

#Time to compile Evilginx
make
```

## Time to run Evilginx3!

```bash
# Disable the Ubuntu resolver (it is sitting on port 53 and we need that port)
systemctl stop systemd-resolved

# Running Evilginx3 for the first time!
/root/evilginx3/build/evilginx -p /root/phishlets/
```

