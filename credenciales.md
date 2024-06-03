<a href="javascript:history.back()" class="button">Volver</a>

# <u>CREDENCIALES</u>

## CREDENCIAL PENDIENTE DE ENTREGA

1. Verificar tabla persona para RUT  
2. `cnt_contratoempleado` usar ID que tenga `fkid_cntempleadoestado` en 2  
3. `acr_solicitud` poner `entregada_solicitud` en 0 y `fkid_estadoacreditación` en 3  

##### Si solicitan cambiar HID verificar en `acr_credenciales`  
##### VERIFICAR EN HERRAMIENTA - BÚSQUEDA PERSONAL - PONER RUT Y VER QUE TENGA UN BOTÓN AZUL

---

## ENTREGAR CREDENCIAL o SI NO PUEDEN ENTREGAR CREDENCIAL

1. Vamos a `acr_solicitud`  
2. Dejamos `entregada` en 1, `impresa` en 1 y el estado de 3 pasa a 7  
##### Revisar `fecha_entregacredencial`

##### Si aún no quiere  
1. Ir a `acr_credenciales_cnt_empleados` y dejar `estado_credenciales` en 1  
2. Verificar que datos coincidan  
3. En `ws_persona_log` se creará uno con la hora actual  
4. Y a ese registro debemos dejar `fkid_estadocredencial` en 1  
##### Verificar que respuesta sea OK y verificar en `datos_enviados` que información coincida

---

## CREDENCIAL PARA IMPRIMIR

1. Identificar ID contratoempleado  
2. `acr_solicitud` debe quedar en 2 el `fkid_estadoacreditación` y en 0 impresa y entrega solicitud  
3. Si dicen que no aparece hay que ver el campo `fkid_contratoempresa` y ver `fkid_cntempresaestado`  
##### VERIFICAR EN IMPRESIÓN PERSONAL

---

## REVISAR LA REIMPRESIÓN DE LA CREDENCIAL - ARREGLAR y/o MOSTRAR EL DETALLE DEL MOTIVO

1. Buscar en la tabla `prs_persona` mediante el RUT para obtener su ID.  
2. Copiar el ID obtenido y dirigirse a `acr_solicitud_reimpresion`.  
3. Verificar la entrada que concuerde en la fecha (`created_at`) o donde se pueda visualizar el error.

##### Realizar correcciones dentro de los campos de comentarios, como "comentario_impresion" o "motivo_rechazo".  
##### Esto implica arreglar caracteres especiales o, en caso de que un párrafo largo obstruya la información crucial,  
##### adecuarlo para que sea comprensible y no afecte la funcionalidad.

