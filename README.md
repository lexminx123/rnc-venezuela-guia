# Guía Operativa y Técnica: Registro Nacional de Contratistas (RNC en Línea - Venezuela)

Repositorio oficial con la documentación técnica, guías operativas, matrices de validación y automatización para el proceso de inscripción y calificación de empresas en el **Registro Nacional de Contratistas (RNC)** administrado por el **Servicio Nacional de Contrataciones (SNC)** de Venezuela.

---

## 📋 Tabla de Contenidos
1. [Introducción y Objetivos](#introducción-y-objetivos)
2. [Estructura del Repositorio](#estructura-del-repositorio)
3. [Guía de Módulos del RNC](#guía-de-módulos-del-rnc)
   - [Módulo 1: Datos de la Empresa](#módulo-1-datos-de-la-empresa)
   - [Módulo 2: Información Legal y Estatutaria](#módulo-2-información-legal-y-estatutaria)
   - [Módulo 3: Información Técnica y Catálogo UNSPSC](#módulo-3-información-técnica-y-catálogo-unspsc)
   - [Módulo 4: Información Financiera y Balance](#módulo-4-información-financiera-y-balance)
4. [Casos Prácticos y Reglas de Negocio](#casos-prácticos-y-reglas-de-negocio)
5. [Protocolo de Seguridad y Control Pre-Envío](#protocolo-de-seguridad-y-control-pre-envío)
6. [Habilidad Antigravity (Skill)](#habilidad-antigravity-skill)

---

## 📌 Introducción y Objetivos
El **Registro Nacional de Contratistas (RNC)** es el registro público de carácter obligatorio para todas las personas naturales y jurídicas que deseen contratar con el Estado venezolano (empresas públicas, ministerios, PDVSA, gobernaciones y alcaldías).

Este repositorio compila todo el conocimiento operativo y contable adquirido durante la tramitación y saneamiento de expedientes en el portal `https://rncenlinea.snc.gob.ve/`, permitiendo:
- Minimizar rechazos o devoluciones por inconsistencias legales o tributarias.
- Cuadrar matemáticamente balances generales con declaraciones del ISLR.
- Configurar adecuadamente catálogos de bienes y servicios sin limitar la capacidad de contratación.

---

## 🗂 Estructura del Repositorio
```text
rnc-venezuela-guia/
├── README.md                          # Visión general y guía principal
├── docs/
│   ├── 01_informacion_empresa.md      # Datos generales, nómina y domicilio fiscal
│   ├── 02_informacion_legal.md        # Registro mercantil, actas, accionistas y comisario
│   ├── 03_informacion_tecnica.md      # Catálogo UNSPSC, clientes y obras/servicios
│   └── 04_informacion_financiera.md   # Dictámenes, ISLR, balances y estado de resultados
├── templates/
│   ├── balance_cuadrado_template.csv  # Plantilla de balance general sincronizado con ISLR
│   └── catalogo_productos_ejemplo.json# Estructura JSON para actividades y bienes UNSPSC
└── skills/
    └── rnc-venezuela-gestion/         # Habilidad lista para agentes de IA (Antigravity)
        └── SKILL.md
```

---

## ⚙️ Guía de Módulos del RNC

### Módulo 1: Datos de la Empresa
- **RIF y Razón Social**: Deben coincidir exactamente con el comprobante digital emitido por el SENIAT.
- **Nómina**: Cantidad verídica de trabajadores (obreros y empleados).
- **Ubicación Territorial**:
  - Estado, Municipio y Parroquia exactos según división político-territorial venezolana.
  - Sede administrativa y depósitos/galpones.

### Módulo 2: Información Legal y Estatutaria
- **Registro Mercantil Matriz**:
  - Circunscripción judicial exacta (ej. Registro Mercantil Tercero del Estado Anzoátegui).
  - Número de documento, Tomo, Año y Protocolo.
  - Vigencia de la sociedad (ej. 50 años) y período estatutario de la Junta Directiva.
- **Accionistas y Junta Directiva**:
  - Registro de titulares con porcentaje accionario exacto (**total 100%**).
  - Tipo de firma de directores: *Separada* o *Conjunta*.
- **Comisario Mercantil**:
  - Designación del profesional (Licenciado en Contaduría o Administración) con número de colegiación (**CPC**).
  - Período de vigencia según la asamblea correspondiente.
- **Modificaciones Estatutarias**:
  - Asentar el tracto sucesivo de todas las asambleas extraordinarias registradas (aumentos de capital, reformas de objeto, venta de acciones, cambios de domicilio).
- **Sucursales**:
  - Si la empresa opera únicamente desde su sede matriz sin sucursales registradas, el módulo no requiere registros y permanece conforme.

### Módulo 3: Información Técnica y Catálogo UNSPSC
- **Codificación UNSPSC**:
  - Clasificación en segmentos, familias y clases compatibles con el objeto de la empresa.
  - En bienes comerciales (ej. lubricantes, repuestos, filtros): en el campo **Marca** se recomienda indicar el concepto descriptivo del producto para preservar amplitud operativa en compras públicas multimarca.
- **Informes de Distribución**:
  - Validación del 100% de los informes técnicos asociados a los productos a comercializar.
- **Relación de Clientes vs. Relación de Obras y Servicios**:
  - *Relación de Clientes*: Comercialización y suministro de bienes con empresas comprobables.
  - *Relación de Obras y Servicios*: Contratos de obras o servicios técnicos específicos (ej. transporte y flete de productos petrolíferos) con su porcentaje de ejecución.

### Módulo 4: Información Financiera y Balance
El sistema exige una estricta secuencia cronológica y validación cruzada con la Declaración del Impuesto Sobre la Renta (ISLR):
1. **Dictamen de Auditoría**: Asentar informe de atestiguamiento / auditoría emitido por Contador Público Colegiado.
2. **Estado de Resultados**: Sincronización obligatoria con las casillas del ISLR:
   - Ingresos brutos por ventas.
   - Costo de ventas (Inventario inicial + Compras netas - Inventario final).
   - Gastos operacionales y administrativos.
   - Utilidad antes y después de impuestos.
3. **Balance General de Cierre**:
   - Inventario final coincidente con el ISLR.
   - Retenciones acumuladas de ISLR por cobrar coincidentes con las planillas tributarias.
   - Pasivo por impuestos por pagar idéntico a la porción liquidada del ejercicio.
   - Capital social suscrito y pagado conforme al último aumento registrado.
   - **Ecuación fundamental**: `Total Activo = Total Pasivo + Patrimonio Neto`.

---

## 🔒 Protocolo de Seguridad y Control Pre-Envío
> [!IMPORTANT]
> **REGLA DE BLOQUEO DE ENVÍO**: El sistema de automatización o preparación de expediente **BAJO NINGUNA CIRCUNSTANCIA** debe presionar el botón de formalización ni enviar la solicitud al RAC (`/procesos/enviar_rnc`).
>
> Toda la información debe dejarse en estado de **Borrador Validado (0 errores / 0 advertencias)** para que el representante legal o gestor autorizado realice la verificación visual final y ejecute el envío con su firma digital.

---

## 🤖 Habilidad Antigravity (Skill)
La habilidad ubicada en `skills/rnc-venezuela-gestion/SKILL.md` permite a cualquier agente de codificación e IA interactiva guiar, auditar y ejecutar la carga de datos respetando todos los estándares del SNC venezolano.
