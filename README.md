# Домашнее задание к занятию "`Система мониторинга Zabbix`" - `Громов Андрей`

---

### Задание 1

```bash
sudo apt update
sudo apt install postgresql
wget https://repo.zabbix.com/zabbix/6.0/debian/pool/main/z/zabbix-release/zabbix-release_6.0-5+debian12_all.deb
sudo dpkg -i zabbix-release_6.0-4+debian11_all.deb
sudo apt update
sudo apt install zabbix-server-pgsql zabbix-frontend-php php7.4-pgsql zabbix-apache-conf zabbix-sql-scripts 
sudo -u postgres createuser --pwprompt zabbix
sudo -u postgres createdb -O zabbix zabbix
zcat /usr/share/zabbix-sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix 
sudo nano /etc/zabbix/zabbix_server.conf
# DBPassword=123456789
sudo systemctl restart zabbix-server apache2
sudo systemctl enable zabbix-server apache2
```

`Скриншот к заданию 1
![Авторизация в админке](https://github.com/GromDrn/zabbix-1/blob/main/screenshots/install_zabbix.jpg)`


---

### Задание 2


```bash
wget https://repo.zabbix.com/zabbix/6.0/debian/pool/main/z/zabbix-release/zabbix-release_6.0-4%2Bdebian11_all.deb
dpkg -i zabbix-release_6.0-4+debian11_all.deb
apt update
sudo apt install zabbix-agent -y
sudo systemctl restart zabbix-agent
sudo systemctl enable zabbix-agent

```

`Скриншоты к заданию 2
![Configuration > Hosts](https://github.com/GromDrn/zabbix-1/blob/main/screenshots/configuration_hosts.jpg)
![Zabbix agent log](https://github.com/GromDrn/zabbix-1/blob/main/screenshots/agent_log.jpg)
![Monitoring > Latest Data](https://github.com/GromDrn/zabbix-1/blob/main/screenshots/monitoring_latest.jpg)`

---

### Задание 3

`Скриншоты к заданию 3
![Latest Data > C: free space](https://github.com/GromDrn/zabbix-1/blob/main/screenshots/free_space.png)
![Windows ok](https://github.com/GromDrn/zabbix-1/blob/main/screenshots/windows_ok.png)
![Free space setup](https://github.com/GromDrn/zabbix-1/blob/main/screenshots/free_space_setup.png)
`

