# Linux Log Yönetimi

```
└─$ rsyslog
    sudo apt-get install rsyslog
    sudo nano /etc/rsyslog.conf 
    sudo nano /etc/rsyslog.d/remote.conf

└─$ Kuralı Ekleyin:
    *.* @logserver.example.com:514 (UDP)
    *.* @@logserver.example.com:514 (TCP)

└─$ Kaydedip Kapatın: Dosyayı kaydedin ve çıkın.
└─$ Servisi Yeniden Başlatın:
    sudo systemctl restart rsyslog
```

# Yerel log kaynakları

```
└─$ /var/log/apache2/access.log
    /var/log/auth.log
    /var/log/audit/audit.log 
└─$ audit
    sudo apt install auditd
    sudo systemctl start auditd.service
    sudo systemctl enable auditd.service
    sudo nano /etc/audit/auditd.conf    
    sudo nano /etc/audit/audit.rules

└─$ sudo apt-get install auditd audispd-plugins       

└─$ sudo auditctl -a always,exit -F arch=b64 -S execve
sudo auditctl -a always,exit -F arch=b32 -S execve



    └─# nano /etc/audit/rules.d/execve.rules          
        -a always,exit -F arch=b64 -S execve
        -a always,exit -F arch=b32 -S execve

    sudo systemctl restart auditd.service

    sudo ausearch -m AVC                 
    sudo chmod +x /etc/audit/audit.log    
    sudo tail -f /etc/audit/audit.log
```

# Linux Güvenlik Ürünleri

```
└─$ Firewall (Gufw)
└─$ IDS (OSSİM)
└─$ QRadar
└─$ Splunk
└─$ Kibana
└─$ Suricata
└─$ OSSEC
└─$ iptables
```
