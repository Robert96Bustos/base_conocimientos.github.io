<link rel="stylesheet" type="text/css" href="styles.css">

[Volver](./index.md)

# <u>PROCESOS DE LICENCIAS</u>

## LICENCIA PARA IMPRIMIR

1. Verificar tabla persona para rut
2. `cnt_contratoempleado` usar ID que tenga `fkid_cntempleadoestado` en 2
3. `acr_solicitudlicencia` debe quedar `impresa_solicitud` y `entrega_solicitud` en NULL

##### (Si el trabajador se encuentra pendiente NO SE PUEDE hacer el cambio)
##### Para verificar contrato debemos ver `fkid_contratoempresa` en la tabla `cnt_contrato`
##### REVISAR EN IMPRESIÓN LICENCIA INTERNA

---

## DEJAR LICENCIA HABILITADA EN SISTEMA (entregar lic)

1. Dirigirse a `cnt_contratoempleado` verificar si está acreditado
2. Con `idcontratoempleado` verificar en `acr_solicitudlicencia` si fechas de `impresa_solicitud` y `entregada_solicitud` corresponden.
3. Si no, debemos copiar y pegar la correspondiente en ambas (`impresa_solicitud` y `entregada_solicitud`)
4. Una vez guardado, dirigirse a `lic_credenciales` y cambiar `fkid_estadocredencial` a 1 (Habilitado)

---

## LICENCIA PENDIENTE WORKMATE (O PENDIENTE VALIDACIÓN)

1. `acr_solicitudlicencia` dejar en `fkid_estadoacreditación` editadopendiente workmate (10)
2. `acr_solicitudlicencia` `fechawm` y `fecha codelco` en NULL y `revisionwm` y `revisioncodelco` 0

##### VERIFICAR EN ACRED LIC. INTERNAS PENDIENTES
