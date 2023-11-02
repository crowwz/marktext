
## command
docker pull ubuntu:22.04
docker run -d -it --name marktext  ubuntu:22.04 bash
docker exec -it marktext bash
//记得提交镜像
docker stop marktext && docker remove marktext

choco install vcxsrv

docker run -d -it -e DISPLAY=host.docker.internal:0 -v C:\Users\z\vsprojects\marktext:/root/marktext --name marktext  ubuntu-gui bash

## build

apt update
apt-get install -y curl wget vim net-tools htop iproute2 sudo nload proxychains4 ncat iputils-ping openssh-server ssh lrzsz git iptables
git config --global core.autocrlf false

apt install -y x11-apps dbus-x11 x11-utils gedit
export DISPLAY=host.docker.internal:0
docker commit marktext ubuntu-gui

//安装node
sudo apt-get install -y ca-certificates curl gnupg
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://deb.nodesource.com/gpgkey/nodesource-repo.gpg.key | sudo gpg --dearmor -o /etc/apt/keyrings/nodesource.gpg
NODE_MAJOR=16
echo "deb [signed-by=/etc/apt/keyrings/nodesource.gpg] https://deb.nodesource.com/node_$NODE_MAJOR.x nodistro main" | sudo tee /etc/apt/sources.list.d/nodesource.list
apt update
apt install -y nodejs

//安装yarn，一定要全局安装 `-g`，不要用apt安装，有软件名冲突
npm install -g yarn

//安装项目
sudo apt-get install -y libx11-dev libxkbfile-dev libsecret-1-dev libfontconfig-dev build-essential

//不能设置环境，否则有报错 ： Downloading ripgrep failed: TypeError [ERR_INVALID_PROTOCOL]: Protocol "https:" not supported. Expected "http:"
//可以用proxychains4
yarn install






