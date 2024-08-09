# LISTA DE IPs VENEZOLANAS

## requerimientos si es Lista por Rutas: 

```bash
add comment="RUTA IPs VENEZUELA" distance=1 scope=10 gateway=192.168.1.1 dst-address=156.154.70.1
```

## requerimientos si es Lista por Address List:

Verificar IP de Proveedores, realizar marcado de ruta que todo lo que vaya destino a la lista, que se dirija a una marca de ruta especifica, ejemplo del comando en Route para ello:

```bash
# IP > Firewall > Magle (todo lo que este en la LAN que vaya destino a alguna IP de TRAFICO_NACIONAL que vaya por la marca de ruta "Venezuela")
add action=mark-routing chain=prerouting dst-address-list=TRAFICO_NACIONAL in-interface-list=LAN new-routing-mark=Venezuela passthrough=no

#  Marcado de ruta.
add comment="RUTA DE BANCOS" distance=1 gateway=192.168.1.1 dst-address=0.0.0.0/0 routing-mark=Venezuela
```
## NOTA IMPORTANTE:
De preferencia es mejor hacer esta recursiva por ROUTE y no por Address List, evita desgaste de procesador y en caso de tener IPs Publicas no se ven afectadas por estar dentro del rango ya que los routers toman como prioridad las rutas mas pequeñas que las grandes.
