## permitir repo inseguros (usar con precaucion)
```
sudo apt-get update --allow-insecure-repositories
```
## Hostname ip
```
hostname -I
```
## Habilitar firewall
```
sudo ufw enable
sudo ufw app list
sudo ufw status
```
## Instalar Apache
```
sudo apt install apache2

```
### Permitir apache en firewall
```
sudo ufw allow 'Apache'
sudo systemctl status apache2
```
### Manejar proceso apache
```
sudo systemctl stop apache2
sudo systemctl start apache2
sudo systemctl restart apache2
sudo systemctl reload apache2
sudo systemctl disable apache2
sudo systemctl enable apache2
```
