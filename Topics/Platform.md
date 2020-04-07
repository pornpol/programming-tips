# Platform

## SSH

- Login to server using ssh key

```
ssh -i ~/.ssh/sshKey root@youdomain(ip)
```

---

## PM2

- install

```
sudo npm i -g pm2
```

- start service

```
pm2 start server.js
pm2 start npm -- start
```

- restart service

```
pm2 restart server.js
pm2 restart npm
```

---

## NGINX

- install

```
sudo apt-get install nginx
```

- config

```
sudo nano /etc/nginx/sites-available/default
```

```
location /api {
                proxy_pass http://localhost:8000;
                proxy_http_version 1.1;
                proxy_set_header Upgrade $http_upgrade;
                proxy_set_header Connection 'upgrade';
                proxy_set_header Host $host;
                proxy_cache_bypass $http_upgrade;
        }

        location / {
                proxy_pass http://localhost:3000;
                proxy_http_version 1.1;
                proxy_set_header Upgrade $http_upgrade;
                proxy_set_header Connection 'upgrade';
                proxy_set_header Host $host;
                proxy_cache_bypass $http_upgrade;
        }
```

---

## LetsEncrypt bot

- install

```
sudo add-apt-repository ppa:certbot/certbot
sudo apt-get update
sudo apt-get install python-certbot-nginx
sudo certbot --nginx -d yourdomain.com -d www.yourdomail.com
```

---

## Digital Ocean

## AWS
