<font size="2">
<font size="5" style="font-weight:bold;">Toggle Display</font>

```xset dpms force off```

```xset dpms force on```

- However, you need to make sure that your acpi is enabled.
You can check this with
	* ```cat /proc/acpi/info```
	
<font size="4" style="font-weight:600;">vbetool</font>
	
- ```sudo apt-get install vbetool```
		
- ```sudo vbetool dpms on```

- ```sudo vbetool dpms off```

##

<br/>
<font size="5" style="font-weight:bold;">USB 3.0 express card</font>

1. ```sudo nano /etc/default/grub```

2. Find ```GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"```

3. Change to ```GRUB_CMDLINE_LINUX_DEFAULT="quiet splash pciehp.pciehp_force=1"```

4. ```sudo update-grub```

5. ```sudo reboot```

##

<br/>
<font size="5" style="font-weight:bold;">Start Ubuntu in Text Mode</font>

1. ```sudo nano /etc/default/grub```

2. Find ```GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"```

3. Change to ```GRUB_CMDLINE_LINUX_DEFAULT="text"```

4. UnComment or add ```GRUB_TERMINAL=console```

5. ```sudo update-grub```

6. ```sudo systemctl enable multi-user.target --force```

7. ```sudo systemctl set-default multi-user.target```

8. ```sudo reboot```

<font size="4" style="font-weight:600;">Undoing Text Mode</font>

1. ```sudo nano /etc/default/grub```

2. Find ```GRUB_CMDLINE_LINUX_DEFAULT="text"```

3. Change to ```GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"```

4. Comment or delete ```GRUB_TERMINAL=console```

5. ```sudo update-grub```

6. ```sudo systemctl enable graphical.target --force```

7. ```sudo systemctl set-default graphical.target```

8. ```sudo reboot```

##

<br/>
<font size="5" style="font-weight:bold;">Turn Off "Energy Efficient Ethernet"</font>
<font size="2">

1. ```sudo nano /etc/default/grub```

2. Find ```GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"```

3. Change to ```GRUB_CMDLINE_LINUX_DEFAULT="quiet splash igb.EEE=0"```

4. ```sudo update-grub```

5. ```sudo reboot```

##

<br/>
</font>
