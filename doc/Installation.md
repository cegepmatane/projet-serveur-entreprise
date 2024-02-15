sudo apt install inspircd

sudo ufw allow 22/tcp
sudo ufw allow 6667/tcp
sudo ufw reload

panneau porkbum

CNAME irc.shiftsphere.xyz

sudo chmod +x /etc/inspircd

sudo cp inspircd.conf inspircd.conf.copie
sudo jed inspircd.conf
