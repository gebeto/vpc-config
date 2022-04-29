## Configure NGINX

```bash
sudo ln -s /home/$USER/vpc-config/nginx /etc/nginx/sites-enabled

sudo ln -s /home/$USER/vpc-config/nginx/default /etc/nginx/sites-available/
sudo ln -s /home/$USER/vpc-config/nginx/default /etc/nginx/sites-enabled/

sudo ln -s /home/$USER/vpc-config/nginx/msx.config /etc/nginx/sites-available/
sudo ln -s /home/$USER/vpc-config/nginx/msx.config /etc/nginx/sites-enabled/

sudo ln -s /home/$USER/vpc-config/nginx/filmes-bot.config /etc/nginx/sites-available/
sudo ln -s /home/$USER/vpc-config/nginx/filmes-bot.config /etc/nginx/sites-enabled/

# test nginx config
sudo nginx -t

# reload nginx service
sudo service nginx reload
```

### Generate certificates for domains

```bash
# install dependencies
sudo apt-get install certbot
sudo apt-get install python3-certbot-nginx

# generate
sudo certbot --nginx -d msx.gebeto.dev
sudo certbot --nginx -d filmes-bot.gebeto.dev

# renew certificates
sudo certbot renew --dry-run
```
