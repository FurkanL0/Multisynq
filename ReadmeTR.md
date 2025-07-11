# Multisynq

![1500x500](https://github.com/user-attachments/assets/d51c1cc9-d5c2-460a-9571-74859194d5d6)

| X        | Minimum              |
|------------------|----------------------------|
| **CPU**          | 4++ |
| **RAM**          | 8++ GB                    |
| **Disk**      | 50 GB+ NVME GB SDD                   |
| **Internet Speed**      | 100 Mbps (1 Gbps+ recommended) |


| Server         | Link              | Features |
|------------------|----------------------------|----------------------------|
| **Contabo**          | [Link](https://www.dpbolvw.net/click-101330552-12454592)                     | Cheap / Paypal  |
| **PQ**      | [Link](https://pq.hosting/?from=627713)                  | Cheap / Crypto Payment |
| **NetCup**          | [Link](https://www.netcup.com/en/?ref=261820) | Cheap / Paypal |

## Proje Sosyal Medyası : 
- Twitter : https://x.com/multisynq

## MultiSynq Kayıt : https://startsynqing.com/?ref=56da30-kzs03j


## Server Güncelleme : 

```bash
sudo apt update -y && sudo apt upgrade -y
```
## Paketleri İndirelim :

```bash
sudo apt install htop ca-certificates zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev tmux iptables curl nvme-cli git wget make jq libleveldb-dev build-essential pkg-config ncdu tar clang bsdmainutils lsb-release libssl-dev libreadline-dev libffi-dev jq gcc screen file unzip lz4 -y
```

## Docker ; 

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io -y
docker version
```

## Docker Compose : 

```bash
VER=$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep tag_name | cut -d '"' -f 4)
curl -L "https://github.com/docker/compose/releases/download/$VER/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
chmod +x /usr/local/bin/docker-compose
docker-compose --version
```

## Docker User

```bash
sudo groupadd docker
sudo usermod -aG docker $USER
```

## Node JS : 
```bash
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash - && sudo apt install -y nodejs
```
## Synqchronize : 

```bash
npm install -g synqchronizer
```
## Json
  ```
  cd $(npm root -g)/synqchronizer
  cat package.json | jq .bin
  ```
  ```
  cat /usr/lib/node_modules/synqchronizer/package.json | jq .bin
  ```
## Synchronize Ayarlama
  ```
  synchronize init
  ```
<img width="458" height="157" alt="image" src="https://github.com/user-attachments/assets/111b86ff-5789-4f79-aedc-5fdc77db266e" />


- İsim verin.
- Dashboard'dan Synq Key'inizi yazın.
- Cüzdan adresinizi yazın.
- Y yazıp onay verin.
- Web paneli için güzel milletin erişemeyeceği bir şifre yazın - şifreyide unutmayın.

## Bilgileri Senkronize Edelim
  ```
  synchronize service
  ```

<img width="511" height="246" alt="image" src="https://github.com/user-attachments/assets/ba4fe2c1-3a18-4a97-a7d2-c92096ca7fe7" />

  ## Servisi Aktaralım
  ```
  sudo cp /root/.synchronizer-cli/synchronizer-cli.service /etc/systemd/system/
  ```
  ```
  sudo systemctl daemon-reload
  sudo systemctl enable synchronizer-cli
  sudo systemctl start synchronizer-cli
  ```
## Durum ; 
  ```
  sudo systemctl status synchronizer-cli
  ```
## WebSite Dashboard için Paneli Açalım

  ## Port Ufw
  ```
  sudo ufw allow 3000/tcp
  ```
  ## Screen
  ```
  screen -S multisynq
  ```
  ```
  synchronize web
  ```
  Detached from screen `CTRL+A+D`
  
  ## Access your Server
  ```
  http://<YOUR_VPS_IP>:3000
  ```

<img width="1452" height="871" alt="image" src="https://github.com/user-attachments/assets/d7530793-e91c-4639-a0ff-5c303772dc1f" />

- Siteye girdiğinizde kullanıcı adı ve şifre isteyecek.
- İsim'iniz sizin kullanıcı adınız.
- Şifre ayarlamıştık oda şifreniz.

## Monitoring Status Synqchronizer
  ```
  sudo systemctl daemon-reload
  sudo systemctl start synqchronizer-cli
  sudo systemctl status synqchronizer-cli
  ```
  ## Check logs realtime for troubleshooting
  ```
  journalctl -u synqchronizer-cli -f
