## Permitir repo inseguros (usar con precaucion).
```
sudo apt-get update --allow-insecure-repositories
```
## Hostname ip.
```
hostname -I
```
## Habilitar firewall.
```
sudo ufw enable
sudo ufw app list
sudo ufw status
```
## Instalar Apache.
```
sudo apt install apache2
```
### Permitir apache en firewall.
```
sudo ufw allow 'Apache'
sudo systemctl status apache2
```
### Manejar proceso apache.
```
sudo systemctl stop apache2
sudo systemctl start apache2
sudo systemctl restart apache2
sudo systemctl reload apache2
sudo systemctl disable apache2
sudo systemctl enable apache2
```

## Conectar a una nueva red wifi en ubuntu server.
### Conocer el nombre de tu tarjetas de red (eth y wifi)(alternativas).
```
ls -l /sys/class/net
ip a
```
### Configurar/modificar archivo YAML para conectar a red wifi.
```
sudo cp /etc/netplan/00-installer-config.yaml /etc/netplan/00-install-config.original.yaml
sudo vim /etc/netplan/00-installer-config.yaml
```
### Reemplzar contenido con lo siguiente.
```
This is the network config written by 'subiquity'

network:
 version: 2 
 wifis:
   wlp0s20f3:
     access-points:
       Mywifi1:
         password: G4XJdbuBVsQeq6Rz
       Mywifi2:
         password: uRK46vdoA76iCNBY
     dhcp4: true
```
### Aplicar cambios. (tambien sirve reiniciar el equipo)
```
sudo netplan apply
```
## Para copiar archivos y preserver los permisos.
```
cp -p [Source_file] [Destination_file]
```
## Crear un nuevo usuario, darle una contraseña y permisos de sudo.
```
sudo useradd -m username
sudo passwd username
sudo usermod -aG sudo username
```
## Para detener todo proceso de algun usuario.
```
sudo killall -u username
```
## Para borrar algun usuario.
```
sudo userdel -r -f username
```
## Como cambiar hora, fecha y zona horaria.
### Para mostrar fecha, hora y zona horaria.
```
timedatectl
```
### Para listar zonas horarias. (para chile continental es America/Santiago)
```
timedatectl list-timezones
timedatectl list-timezones | grep [keyword]
```
### Para establecer la zona horaria.
```
timedatectl set-timezone Region/Location
```
### Para sincronizar con el servicio NPT. (se respeta la zona horaria)
```
timedatectl set-ntp yes
```
