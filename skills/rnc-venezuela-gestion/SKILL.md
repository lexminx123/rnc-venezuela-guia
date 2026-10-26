---
name: rnc-venezuela-gestion
description: Procedimiento integral, validación legal, técnica y financiera para la inscripción y actualización de empresas en el Registro Nacional de Contratistas (RNC en Línea - SNC de Venezuela).
---

# Habilidad: Gestión Integral en el Registro Nacional de Contratistas (RNC en Línea)

Esta habilidad documenta y estandariza todo el flujo operativo, requisitos legales, catálogo UNSPSC, estados financieros y reglas de negocio para tramitar solicitudes de inscripción y actualización ante el Servicio Nacional de Contrataciones (SNC) de Venezuela (`https://rncenlinea.snc.gob.ve/`).

## 1. Reglas Críticas de Seguridad y Operación
- **REGLA DE ORO**: **NUNCA pulsar el botón de envío formal al RAC (`/procesos/enviar_rnc`)** salvo autorización expresa y final del usuario. El sistema debe dejar la solicitud en borrador validada con 0 errores y 0 advertencias para revisión humana.
- **Navegador**: Cuando se opere por automatización, utilizar una sesión interactiva o depurada con Chrome DevTools en puerto `9222`.

---

## 2. Módulo de Información de la Empresa (`/datosgenerales`, `/infempresa`)
1. **Datos Básicos**:
   - RIF de la empresa (ejemplo: `J-406252719`).
   - Razón Social exacta según Acta Constitutiva / Modificaciones.
   - Cantidad de trabajadores reales (nómina administrativa y obrera).
2. **Dirección Fiscal**:
   - Estado, Municipio y Parroquia exactos según Registro de Información Fiscal y Registro Mercantil.
   - Sector, avenida/calle, edificio/galpón y número.
3. **Servicios y Afiliaciones**:
   - Indicar con veracidad pólizas de seguros, vigilancia o filiales. No inventar URLs de páginas web si la empresa no posee dominio institucional activo.

---

## 3. Módulo de Información Legal (`/legal`)

### 3.1. Registro Mercantil (`/regmercantiles`)
- **Tipo de Registro Mercantil**: Seleccionar la circunscripción exacta (ej. *Registro Mercantil Tercero de la Circunscripción Judicial del Estado Anzoátegui*).
- **Número, Tomo, Año y Protocolo**: Extraer del sello/nota de inscripción del Registro.
- **Capital Social Suscrito y Pagado**: Actualizado a la fecha de la solicitud (expresado en Bolívares vigentes).
- **Vigencia de la Sociedad y de la Junta Directiva**:
  * Duración de la sociedad (ej. 50 años a partir de la constitución).
  * Duración estatutaria de la Junta Directiva (ej. 5 años desde la última asamblea de designación).
- **Fecha de Cierre del Ejercicio Económico**: Generalmente `31/12`.

### 3.2. Accionistas y Junta Directiva (`/accionistas`)
- Documento de Identidad (V / E / J).
- Nombre completo y cargo (Presidente, Vicepresidente, Director).
- Tipo de firma: **Separada** o **Conjunta** según lo fijen los estatutos.
- Porcentaje accionario: Debe totalizar obligatoriamente el **100%**.

### 3.3. Comisario (`/comisarios`)
- Cédula de identidad del profesional contable/administrador.
- Número de Colegiación (**CPC** para Contadores Públicos Colegiados).
- Período de vigencia según la asamblea que lo designó o ratificó.

### 3.4. Modificaciones Estatutarias (`/modificaciones`)
Cada modificación en la historia jurídica de la empresa debe asentarse cronológicamente:
1. Venta o cesión de cuotas/acciones.
2. Reformas del objeto social.
3. Aumentos de capital social.
4. Cambios de domicilio fiscal.
5. Reestructuración de Junta Directiva y Comisario.

*Datos obligatorios por acta*: Tipo de modificación, N° de documento, Tomo, Folio, Fecha de la asamblea y Fecha de registro mercantil.

### 3.5. Sucursales (`/sucursales`)
- Si la sociedad no tiene formalmente establecidas sucursales mediante acta registrada, el módulo permanece sin registros, manteniéndose sin observaciones.

---

## 4. Módulo de Información Técnica (`/inftecnica`, `/segcontratistas`)

### 4.1. Catálogo de Actividades y Productos (UNSPSC)
- **Segmentos**: Seleccionar únicamente las familias y clases que guarden relación directa con el objeto social registrado y la capacidad instalada real de la empresa.
- **Bienes (Suministro)**:
  * Código de producto UNSPSC (ej. `15121501` Aceite de motor, `15121504` Aceite hidráulico, etc.).
  * **Nombre comercial / Marca**: Si la empresa comercializa el producto en forma genérica o multimarca, colocar el mismo concepto descriptivo del producto para no restringir la capacidad comercial en licitaciones públicas.
- **Servicios / Obras**:
  * Incluir códigos específicos autorizados (ej. `78102101` Transporte de productos petrolíferos).
  * Depurar actividades que no se presten activamente para evitar exigencias técnicas o certificaciones imposibles de cumplir en pliegos de contratación.

### 4.2. Informes de Distribución (`/infodistribuidor`)
- Cada producto ofertado como distribuidor/comercializador debe tener su informe de distribución validado al 100%, indicando origen, capacidad de almacenamiento y canales logísticos.

### 4.3. Relación de Clientes (`/relclientes`)
- Registrar clientes comerciales reales para soportar la comercialización de bienes.
- Datos indispensables: RIF, Nombre/Razón Social, Dirección, Teléfono, Correo de contacto y montos de operaciones comerciales.

### 4.4. Relación de Obras y Servicios Ejecutados (`/relobras`)
- Diferenciar estrictamente de la venta de bienes: aquí se asientan contratos de servicio o proyectos de obra ejecutados.
- Relacionar el código del servicio (ej. transporte de carga o hidrocarburos), contratante, número de contrato, fechas y porcentaje de ejecución (**100% ejecutado** para contratos culminados).

---

## 5. Módulo de Información Financiera (`/financiera`, `/balances`, `/edoresultados`)

### 5.1. Secuencia Obligatoria de Carga
1. **Dictamen de Auditoría (`/dictamenes/cierre`)**:
   - Asentar los datos del Contador Público Colegiado (CPC) auditor independiente.
   - Fecha de emisión del dictamen y tipo de opinión (**Limpia / Favorable**).
2. **Balance General de Cierre (`/balances/cierre`)**:
   - Fecha de corte: `31-12-XXXX`.
   - Cifras a costo histórico coherentes con la declaración de ISLR.
   - Inventario final de mercancías: Debe coincidir exactamente con la casilla 28/717 del formulario de ISLR.
   - Retenciones acumuladas de ISLR por cobrar: Coincidente con la casilla 28 de anticipos del ISLR.
   - Impuesto por pagar: Coincidente con el impuesto liquidado por pagar de la declaración.
   - Capital Social: Coincidente con el monto suscrito y pagado de la última asamblea registrada.
   - **Regla Contable**: Total Activo = Total Pasivo + Total Patrimonio Neto.
3. **Estado de Resultados de Cierre (`/edoresultados/cierre`)**:
   - Ingresos operacionales / Ventas netas (coincidente con casilla 3/703 de ISLR).
   - Costo de ventas desagregado (Inventario Inicial + Compras Netas - Inventario Final).
   - Gastos operativos y administrativos (Sueldos, tributos pagados, depreciaciones, otros gastos).
   - Utilidad neta contable del ejercicio antes de reservas.

---

## 6. Checklist de Validación Final Pre-Envío
- [ ] Información de la Empresa: 0 errores, 0 advertencias.
- [ ] Información Legal: 0 errores, 0 advertencias (100% acciones distribuidas, comisario vigente).
- [ ] Información Técnica: 0 errores, 0 advertencias (catálogo limpio, informes de distribución al 100%).
- [ ] Información Financiera: 0 errores, 0 advertencias (dictamen registrado, balance cuadrado, ISLR sincronizado).
- [ ] **Verificación de Seguridad**: Dejar la solicitud en estado de borrador y alertar al usuario para que proceda con su envío formal y firma digital ante el RAC.
