# LISTA DE IPs VENEZOLANAS

## requerimientos si es Lista por Rutas: 

```bash
add comment="RUTA DE BANCOS" distance=1 scope=10 gateway=192.168.1.1 dst-address=156.154.70.1
```

## requerimientos si es Lista por Address List:

Verificar IP de Proveedores, realizar marcado de ruta que todo lo que vaya destino a la lista, que se dirija a una marca de ruta especifica, ejemplo del comando en Route para ello:

```bash
add comment="RUTA DE BANCOS" distance=1 gateway=192.168.1.1 dst-address=0.0.0.0/0 routing-mark=Venezuela
```
