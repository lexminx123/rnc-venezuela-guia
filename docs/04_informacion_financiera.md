# Módulo 4: Información Financiera, Auditoría y Balance General

## 1. Alcance
La calificación financiera es el filtro más riguroso del RNC. Exige absoluta coherencia matemática y contable entre la Declaración del Impuesto Sobre la Renta (ISLR), los Estados Financieros de Cierre y los dictámenes de auditoría externa.

## 2. Flujo Secuencial Obligatorio en RNC en Línea
El sistema no permite cargar el balance sin antes registrar el dictamen, ni finalizar sin el estado de resultados:
1. **Dictamen de Auditoría** (`/dictamenes/cierre`).
2. **Balance General de Cierre** (`/balances/cierre`).
3. **Estado de Resultados** (`/edoresultados/cierre`).

---

## 3. Dictamen de Auditoría
- Datos del Contador Público Colegiado (CPC) independiente o firma de auditores:
  - Cédula de identidad y nombres completos.
  - Número de colegiación profesional (CPC).
  - Fecha de emisión del dictamen.
  - Tipo de opinión: **Opinión Limpia / Favorable sin salvedades**.

---

## 4. Estado de Resultados (Sincronización con ISLR)
Las cifras deben guardar estricta correspondencia con las casillas del formulario DPJ del SENIAT:
- **Ingresos Operacionales Netos**: Casilla de Ventas Netas del sector privado o público.
- **Costo de Ventas**:
  - `Inventario Inicial` + `Compras Netas Nacionales y Exterior` - `Inventario Final`.
- **Utilidad Bruta**: Ingresos Netos menos Costo de Ventas.
- **Gastos Operativos y de Administración**:
  - Sueldos y salarios + directivos.
  - Tributos pagados.
  - Indemnizaciones laborales.
  - Depreciaciones y amortizaciones acumuladas del ejercicio.
  - Otros gastos operativos deducibles.
- **Utilidad Contable del Ejercicio**: Coincidente con la renta neta contable antes de reservas.
- **Impuesto Sobre la Renta (ISLR)**: Coincidente con el impuesto determinado del ejercicio.

---

## 5. Balance General de Cierre (Ecuación Patrimonial)

### 5.1. Activos
- **Activo Circulante**:
  - Efectivo en Caja y Bancos.
  - Cuentas por Cobrar Comerciales.
  - **Retenciones de ISLR por Cobrar**: Valor idéntico a las retenciones del ejercicio reflejadas en el renglón 28 de la declaración del ISLR.
  - **Inventario Final de Mercancías**: Valor idéntico al inventario final asentado en el costo de ventas de la declaración del ISLR.
- **Propiedad, Planta y Equipos**:
  - Mobiliario, vehículos y maquinaria.
  - Menos: Depreciación acumulada.

### 5.2. Pasivos
- **Pasivo Circulante**:
  - Cuentas por Pagar Comerciales / Proveedores.
  - **Impuestos por Pagar**: Valor idéntico al impuesto liquidado por pagar resultante de la declaración de ISLR.
  - Otras cuentas por pagar operativas.

### 5.3. Patrimonio Neto
- **Capital Social Actualizado**: Monto suscrito y pagado según la última acta de asamblea de aumento de capital inscrita en el Registro Mercantil.
- **Utilidad Neta del Ejercicio**: Coincidente con el Estado de Resultados.
- **Reservas / Utilidades Acumuladas**.

### 5.4. Verificación de Ecuación Fundamental
$$\text{Total Activo} = \text{Total Pasivo} + \text{Patrimonio Neto}$$
Cualquier descuadre de céntimos causará un bloqueo inmediato en la validación del sistema RNC.
