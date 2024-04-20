# electron-notes

git config --global user.name "Electron Team Server"
git config --global user.email "electron.team.md@gmail.com"
ssh-keygen -t rsa -b 4096 -C "electron.team.md@gmail.com"
/home/electron/.ssh
cat id_rsa.pub
git clone git@github.com:electronteam/electron-persistence.git
git clone git@github.com:electronteam/electron-backend.git
git clone git@github.com:electronteam/electron-frontend.git
git clone git@github.com:electronteam/electron-admin.git
https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04
sudo apt install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
apt-cache policy docker-ce
sudo apt install docker-ce
sudo systemctl status docker
sudo curl -L "https://github.com/docker/compose/releases/download/1.27.4/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
sudo usermod -aG docker ${USER}
https://docs.portainer.io/v/ce-2.9/start/install/server/docker/linux
portainer:
user: admin
pass: baroncea
https://github.com/docker/kitematic/releases
sudo dpkg -i ~/Downloads/mysql-workbench-community_8.0.27-1ubuntu21.10_amd64.deb
sudo dpkg -i ~/Downloads/mysql-workbench-community-dbgsym_8.0.27-1ubuntu20.04_amd64.deb
To delete a directory with rm, you need to add the -d option (if it is empty), or the -r option to delete recursively. Also you can use rmdir to delete empty directories
sudo apt install maven
sudo apt install npm
sudo npm install -g serve

Jenkins:
sudo chown -R jenkins:jenkins Projects

sudo chown -R electron:electron /home/electron/Projects
sudo chown -R jenkins:jenkins /home/electron/Projects

sudo chown -R electron:electron /home/electron/Projects/electron-admin
sudo chown -R jenkins:jenkins /home/electron/Projects/electron-admin

sudo chown -R electron:electron /home/electron/Projects/electron-frontend
sudo chown -R jenkins:jenkins /home/electron/Projects/electron-frontend

If git cloning doesn't work, run the following:
chmod 600 id_rsa
chmod 644 id_rsa.pub



Insecure configuration for --pid-file: Location '/var/run/mysqld' in the path is accessible to all OS users. Consider choosing a different directory. - worked after a while

sudo apt-get update

with error:
Err:6 http://repo.mysql.com/apt/ubuntu focal InRelease
  The following signatures couldn't be verified because the public key is not available: NO_PUBKEY B7B3B788A8D3785C
Fetched 127 kB in 1s (151 kB/s)

Helped:
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys B7B3B788A8D3785C



electron-backend:

mvn clean package
mvn spring-boot:run
git reset --hard HEAD       (going back to HEAD)

electron-frontend:

git pull -r
npm run build
serve -s build
serve -s build -l 3001


lrwxrwxrwx 1 root root           22 Apr 20 13:45  java -> /etc/alternatives/java

sudo apt remove jenkins

sudo apt install openjdk-11-jdk

sudo apt install jenkins

service jenkins restart
sudo systemctl restart jenkins

Jenkins change default PORT:

electron@electron-server:/etc/systemd/system$ sudo mkdir jenkins.service.d
electron@electron-server:/etc/systemd/system$ sudo touch /etc/systemd/system/jenkins.service.d/override.conf
electron@electron-server:/etc/systemd/system$ sudo nano /etc/systemd/system/jenkins.service.d/override.conf
electron@electron-server:/etc/systemd/system$ sudo systemctl restart jenkins
Warning: The unit file, source configuration file or drop-ins of jenkins.service changed on disk. Run 'systemctl daemon-reload' to reload units.
electron@electron-server:/etc/systemd/system$ systemctl daemon-reload
electron@electron-server:/etc/systemd/system$ sudo systemctl restart jenkins

https://stackoverflow.com/questions/28340877/how-to-change-port-number-for-jenkins-installation-in-ubuntu-12-04
https://stackoverflow.com/questions/70100117/cant-get-jenkins-to-run-on-different-port-on-ubuntu-20-4

Open file manager from terminal:
xdg-open .
