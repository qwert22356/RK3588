# How to Install Docker on Debian

## Step 1: Change iptables **important**

```bash
[ -f /usr/sbin/iptables-legacy ] && sudo update-alternatives --set iptables /usr/sbin/iptables-legacy
[ -f /usr/sbin/ip6tables-legacy ] && sudo update-alternatives --set ip6tables /usr/sbin/ip6tables-legacy
```

## Step 2: Install Docker
```bash

sudo apt install lsb-release wget
codename=$(lsb_release -c | awk '{print $2}')
version=$(lsb_release -sr | cut -d'.' -f1)
wget https://download.docker.com/linux/debian/dists/${codename}/pool/stable/arm64/containerd.io_1.7.25-1_arm64.deb
wget https://download.docker.com/linux/debian/dists/${codename}/pool/stable/arm64/docker-ce-cli_28.0.1-1~debian.${version}~${codename}_arm64.deb
wget https://download.docker.com/linux/debian/dists/${codename}/pool/stable/arm64/docker-buildx-plugin_0.21.1-1~debian.${version}~${codename}_arm64.deb
wget https://download.docker.com/linux/debian/dists/${codename}/pool/stable/arm64/docker-ce_28.0.1-1~debian.${version}~${codename}_arm64.deb
wget https://download.docker.com/linux/debian/dists/${codename}/pool/stable/arm64/docker-compose-plugin_2.33.1-1~debian.${version}~${codename}_arm64.deb
sudo apt install ./containerd.io_1.7.25-1_arm64.deb \
  ./docker-ce_28.0.1-1~debian.${version}~${codename}_arm64.deb \
  ./docker-ce-cli_28.0.1-1~debian.${version}~${codename}_arm64.deb \
  ./docker-buildx-plugin_0.21.1-1~debian.${version}~${codename}_arm64.deb \
  ./docker-compose-plugin_2.33.1-1~debian.${version}~${codename}_arm64.deb
```

## Step 3: Verify install of Docker
```bash
systemctl start docker
docker info
docker run hello-world
```
