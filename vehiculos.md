<link rel="stylesheet" type="text/css" href="styles.css">

<br>
<br>

[Volver](./index.md)
<br>

# <u>PROCESOS DE VEHÍCULOS</u>
<br>

## DEJAR PARA IMPRESIÓN QR DE VEHÍCULO (pendiente de impresión de QR)

1. `veh_solicitud`: nos fijamos cualquiera que no esté en 10, `fkid_Estado` cambiar a 4
2. Tomamos el id y vamos a `veh_Credencial_solicitud` y cambiamos el `fk_estadocredencial` a 3
3. PARA VERIFICAR VAMOS A CREDENCIALIZACIÓN - EMISIÓN CREDENCIALES VEH  
##### NO TOCAR PENDIENTES WORKMATE O PENDIENTES CODELCO

---
<br>

## DEJAR ACREDITADA Y HABILITADA PATENTE (O VALIDAR PATENTE)

1. Buscar patente en script
2. Ir a `veh_solicitud` y cambiar `fkid_estado` a 4
3. En `veh_credencial_solicitud` cambiar `fkid_estadocredencial` a 4  
##### VERIFICAR EN CREDENCIALIZACIÓN - EMISIÓN CREDENCIALES VEHÍCULO 
##### NO TOCAR PENDIENTES WORKMATE O PENDIENTES CODELCO

---
<br>

## DEJAR PATENTE PENDIENTE DE INSPECCIÓN (WM/Codelco)

1. En `veh_solicitud` dejar `fkid_estado` en estado 16 (pendiente inspección)
2. Dejar 1 en `fkid_calendario`
3. Luego, ingresar la `fecha_turno` como 2024-04-13 (siempre debe pedirse con 2 meses de anticipación, es decir, dejarlo para 1 mes al día actual)
4. Copiar el id de `veh_solicitud` y dirigirse a `veh_credenciales_solicitud`
5. En `veh_credenciales_solicitud` dejar 2
6. Posteriormente, dirigirse a `veh_asignacion_horario`. Si no existe, crear un registro
7. Ingresar en `fecha_inspeccion` la `fecha_turno`
8. En `fkid_configuracion_inspectores`, seleccionar dejar en 1 (ZN ZONA NORTE)
9. Dejar `fkid_calendario` en 1 y poner la `fkid_solicitud` que corresponde al id del vehículo  
##### PARA VERIFICAR IR A HERRAMIENTAS - BÚSQUEDA PATENTE  
##### NO TOCAR PENDIENTES WORKMATE O PENDIENTES CODELCO

---
<br>

## PATENTE PENDIENTE DE REVISIÓN O PENDIENTE WORKMATE

1. Buscamos patente en script
2. Vamos a `veh_solicitud`
3. Dejamos `fkid_estado` en 18
4. Dejamos `fecha_revision_workmate` en NULL
5. Dejamos `fecha_revision_codelco` en NULL
6. `revision_wm` en 0
7. `revision_codelco` en 0  
##### NO TOCAR PENDIENTES WORKMATE O PENDIENTES CODELCO

---
<br>

## DEJAR RECHAZADA DE INSPECCIÓN

1. En `veh_solicitud` cambiar `fkid_estado` a 5 (RECHAZADO DE INSPECCIÓN)  
##### NO TOCAR PENDIENTES WORKMATE O PENDIENTES CODELCO

---
<br>

## DEJAR RECHAZADA WORKMATE

1. Buscamos patente en plataforma para verificar si está editado pendiente workmate
2. En `vhe_solicitud` cambiamos estado de 18 a 20 (editado rechazado workmate)
3. Luego en `fecha_revisionwm` dejamos la fecha de hoy (o la de hoy) y en `revision_wm` en 2
4. Fijarse que `fecha_revisioncodelco` esté en Null y `revision_codelco` en 0

---
<br>

## RECHAZAR VEHÍCULO O PATENTE

1. En `veh_solicitud`, ponemos la fecha de hoy en `fecha_revisionworkmate`
2. `revision_Workmate` en 2
3. `fkid_estado` en 20
