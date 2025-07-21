# Multisynq

![1500x500](https://github.com/user-attachments/assets/d51c1cc9-d5c2-460a-9571-74859194d5d6)



## Server Güncelleme : 

```bash
sudo apt update -y && sudo apt upgrade -y
```

```bash
sudo nano /root/.synchronizer-cli/synchronizer-cli.service
```

- --launcher cli 'yi kaldırın.
- --sync-name keyadi --launcher cli --key synqkey - buradaki --launcher cli'yi kaldırın.

- Örnek Hali

```bash
[Unit]
Description=Multisynq Synchronizer headless service
After=docker.service
Requires=docker.service

[Service]
Type=simple
User=root
Restart=always
RestartSec=10
ExecStart=/usr/bin/docker run --rm --name synchronizer-cli --platform linux/amd64 cdrakep/synqchronizer:latest --depin wss://api.multisynq.io/depin --sync-name burayakedadiniz --key burayasynckey --wallet monadcüzdanadresi
Environment=PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin

[Install]
WantedBy=multi-user.target

```


```bash
sudo cp /root/.synchronizer-cli/synchronizer-cli.service /etc/systemd/system/
sudo systemctl daemon-reload
sudo systemctl restart synchronizer-cli
sudo systemctl status synchronizer-cli
```


```bash
sudo journalctl -u synchronizer-cli -f
```

