# Confiruacion servicio NFS
## servidor
1. instalar paquetes necesarios:
```bash
$ apt-get install portmap
$ apt-get install nfs-common
$ apt-get install nfs-kernel-server
```
2. definir el directorio a exportar:
```bash
$ mkdir /export/nfs
```
luego editamos el archivo de configuracion de nfs-kernell:
```bash
$ nano /etc/exports
```
descomente y edite la siquiente linea asi:
```bash
/export/nfs IP_RED(rw,no_root_squash)
```
3. iniciar servicio:
```bash
$ /etc/init.d/nfs-kernel-server start
```
4. Exportar el sistema de archivos /nfs
```bash
$ exportfs -av
```
5. Comprobar el servicio:
```bash
$ rpcinfo -p
```
