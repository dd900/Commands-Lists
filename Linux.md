<details>
<summary><h4>Toggle Display</h4></summary>
<p>
	
- ```xset dpms force off```
	
- ```xset dpms force on```
	
- However, you need to make sure that your acpi is enabled.
You can check this with
	
	* ```cat /proc/acpi/info```
	
<details>	
<summary><h4>vbetool</h4></summary>
<p>
	
- ```sudo apt-get install vbetool```
		
- ```sudo vbetool dpms on```

- ```sudo vbetool dpms off```

</p>	
</details>
</p>
</details>
<br/>
<details>
<p>
<summary><h4>USB 3.0 express card</h4></summary>

1. ```sudo nano /etc/default/grub```

2. Find ```GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"```

3. Change to ```GRUB_CMDLINE_LINUX_DEFAULT="quiet splash pciehp.pciehp_force=1"```

4. ```sudo update-grub```

5. ```sudo reboot```

</p>	
</details>	
<br/>
<details>
<p>
<summary><h4>Start Ubuntu in Text Mode</h4></summary>

1. ```sudo nano /etc/default/grub```

2. Find ```GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"```

3. Change to ```GRUB_CMDLINE_LINUX_DEFAULT="text"```

4. UnComment or add ```GRUB_TERMINAL=console```

5. ```sudo update-grub```

6. ```sudo systemctl enable multi-user.target --force```

7. ```sudo systemctl set-default multi-user.target```

8. ```sudo reboot```

<details>
<p>
<summary><h4>Undoing Text Mode</h4></summary>

1. ```sudo nano /etc/default/grub```

2. Find ```GRUB_CMDLINE_LINUX_DEFAULT="text"```

3. Change to ```GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"```

4. Comment or delete ```GRUB_TERMINAL=console```

5. ```sudo update-grub```

6. ```sudo systemctl enable graphical.target --force```

7. ```sudo systemctl set-default graphical.target```

8. ```sudo reboot```

</p>
</details>
</p>
</details>
<br/>
<details>
<p>
<summary><h4>Turn Off "Energy Efficient Ethernet"</h4></summary>

1. ```sudo nano /etc/default/grub```

2. Find ```GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"```

3. Change to ```GRUB_CMDLINE_LINUX_DEFAULT="quiet splash igb.EEE=0"```

4. ```sudo update-grub```

5. ```sudo reboot```

</p>
</details>
<br/>
<details>
<p>
<summary><h4>Download to Directory</h4></summary>

- ```sudo wget www.url.com -P /path/to/dir```

</p>
</details>
<br/>
<details>
<p>
<summary><h4>How to check cron logs</h4></summary>

- ```sudo systemctl status cron```
	
- ```ps aux | grep cron```
	
- ```grep cron /var/log/syslog```
	
	* ```grep -i cron /var/log/syslog```
	
- ```journalctl -u cron.service```
	
- ```journalctl -u anacron.service```
	
</p>
</details>
<br/>
<details>
<p>
<summary><h4>Docker</h4></summary>

set all containers to restart unless-stopped
	
- ```docker update --restart unless-stopped $(docker ps -q)```
	
</p>
</details>
<br/>
<details>
<p>
<summary><h4>NGINX</h4></summary>

Link sites-available to sites-enabled

- ```sudo ln -s /etc/nginx/sites-available/sitename /etc/nginx/sites-enabled/```

Check nginx config

- ```sudo nginx -t```

Restart nginx

- ```sudo systemctl restart nginx```

</p>
</details>
<br/>
