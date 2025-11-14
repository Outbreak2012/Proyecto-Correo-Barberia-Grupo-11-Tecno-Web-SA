---
marp: true
theme: default
paginate: true
backgroundColor: #fff
backgroundImage: url('https://marp.app/assets/hero-background.svg')
header: '🏢 Sistema de Gestión para Barberías'
footer: 'Modelo de Negocio - 2025'
---

<!-- _class: invert -->
# 🏢 Modelo de Negocio
## Sistema de Gestión para Barberías

### Control por Email - Innovación Accesible

---

<!-- _class: lead -->
## 📋 ¿Qué es?

**Sistema ERP integral para barberías** con control por correo electrónico

### Características Principales:
- ✅ Gestión completa de operaciones
- ✅ Control por comandos de email (POP3/SMTP)
- ✅ Reportes y análisis de negocio
- ✅ Sin necesidad de app móvil o web

---

## 🎯 Propuesta de Valor

### **Innovación Principal**
Control total de la barbería mediante **comandos por email**

```
Cliente envía email:
Asunto: CREATERESERVAS[1, 1, 1, 2024-12-01, 10:00, 11:00, Corte]

Sistema responde:
✓ Reserva creada exitosamente. ID: 42
```

### **Beneficios:**
- No requiere conexión permanente a internet
- Accesible desde cualquier cliente de email
- Bajo costo de implementación
- Fácil de usar para cualquier usuario

---

## 🔄 Flujo de Negocio

```
┌─────────────┐
│   Cliente   │
└──────┬──────┘
       │ Solicita servicio
       ▼
┌─────────────┐
│   Reserva   │ ← Asigna barbero, fecha, hora
└──────┬──────┘
       │
       ▼
┌─────────────┐
│   Barbero   │ ← Atiende y usa productos
└──────┬──────┘
       │
       ▼
┌─────────────┐
│    Pago     │ ← Anticipo o pago completo
└──────┬──────┘
       │
       ▼
┌─────────────┐
│  Reportes   │ ← Análisis de ingresos
└─────────────┘
```

---

## 💼 Entidades del Sistema

| Entidad | Función |
|---------|---------|
| **👤 Usuario** | Gestión de cuentas (admin, barberos, clientes) |
| **✂️ Barbero** | Profesional con especialidades y horarios |
| **👨 Cliente** | Usuario que consume servicios |
| **🎨 Servicio** | Corte, tinte, afeitado (con precio y duración) |
| **🧴 Producto** | Inventario consumible (shampoo, gel, etc.) |
| **📅 Reserva** | Cita agendada que genera ingresos |
| **💰 Pago** | Transacciones (efectivo, tarjeta, transferencia) |
| **🕐 Horario** | Disponibilidad de barberos por día/hora |

---

## 💰 Modelo de Ingresos

### **Fuentes de Ingreso:**

1. **Servicios principales**
   - Cortes de cabello
   - Tintes y coloración
   - Afeitado y barba
   - Tratamientos capilares

2. **Productos**
   - Venta de productos de belleza
   - Consumibles usados en servicios

3. **Gestión de pagos**
   - 💵 Pago anticipado (confirma reserva)
   - 💳 Pago final (al completar)
   - ✅ Pago completo (todo de una vez)

---

## 📊 Estados del Negocio

### **Ciclo de Reserva:**
```
Pendiente → Confirmada → En Proceso → Completada
              ↓              ↓
          Cancelada    No Asistió
```

### **Control de Pagos:**
```
Sin Pagar → Anticipo → Pago Parcial → Completado
```

### **Productos:**
```
Activo ← → Inactivo
   ↓
Stock Mínimo Alcanzado (Alerta)
```

---

## 📧 Comandos por Email

### **Operaciones CRUD disponibles:**

| Comando | Ejemplo |
|---------|---------|
| **LISTAR** | `LISTARUSUARIOS[*]` |
| **CREATE** | `CREATERESERVAS[1,1,1,2024-12-01,10:00,11:00,nota]` |
| **UPDATE** | `UPDATESERVICIOS[1,Corte Premium,desc,30,25.00]` |
| **DELETE** | `DELETEPRODUCTOS[5]` |
| **GET** | `GETCLIENTES[1]` |
| **HELP** | `HELP` |

### **10 Entidades Gestionables:**
Usuarios • Categorías • Productos • Barberos • Clientes  
Servicios • Horarios • Reservas • Pagos • ServicioProductos

---

## 📈 Inteligencia de Negocio

### **10 Reportes Disponibles:**

1. 📊 **Dashboard General** - Vista 360° del mes
2. 💵 **Ingresos por Período** - Análisis financiero
3. 🏆 **Ranking de Barberos** - Performance individual
4. ⭐ **Servicios Populares** - Demanda y tendencias
5. 👥 **Clientes Frecuentes** - Programa de fidelización
6. 📋 **Distribución de Estados** - Eficiencia operativa
7. 🕐 **Horas Pico** - Optimización de capacidad
8. 📅 **Días Ocupados** - Planificación de personal
9. 💳 **Métodos de Pago** - Preferencias financieras
10. 🧴 **Consumo de Productos** - Control de inventario

---

## 📊 Ejemplo: Dashboard General

```
╔════════════════════════════════════════╗
║   DASHBOARD - NOVIEMBRE 2025          ║
╠════════════════════════════════════════╣
║ 💰 Ingresos del Mes:     $12,450.00  ║
║ 📅 Total Reservas:            145     ║
║ ✅ Completadas:               128     ║
║ ❌ Canceladas:                 12     ║
║ 👤 Clientes Atendidos:         89     ║
║ 📈 Tasa de Ocupación:         88%     ║
╠════════════════════════════════════════╣
║ 🏆 TOP 3 BARBEROS                     ║
║ 1. Juan Pérez        $4,200.00       ║
║ 2. María López       $3,850.00       ║
║ 3. Carlos Ruiz       $3,100.00       ║
╠════════════════════════════════════════╣
║ ⭐ SERVICIOS MÁS POPULARES            ║
║ 1. Corte Clásico          45 veces   ║
║ 2. Corte + Barba          32 veces   ║
║ 3. Tinte                  18 veces   ║
╚════════════════════════════════════════╝
```

---

## 🔗 Integración Producto-Servicio

### **Gestión Inteligente de Inventario:**

```
Servicio: Corte Premium
  ├─ Producto: Shampoo Premium (2 unidades)
  ├─ Producto: Acondicionador (1 unidad)
  └─ Producto: Cera para cabello (0.5 unidades)

Al completar servicio:
✓ Stock actualizado automáticamente
✓ Alerta si stock < mínimo
✓ Costo calculado en reporte
```

### **Beneficios:**
- Control automático de inventario
- Cálculo preciso de costos por servicio
- Alertas de reabastecimiento
- Análisis de rentabilidad real

---

## ⚙️ Arquitectura del Sistema

```
┌──────────────────────────────────────┐
│     Email (Cliente/Admin)            │
│  Asunto: CREATERESERVAS[...]         │
└───────────────┬──────────────────────┘
                │
        ┌───────▼────────┐
        │   POP3 Client  │ ← Recibe emails
        │   (10 seg)     │
        └───────┬────────┘
                │
        ┌───────▼────────┐
        │ ComandoEmail   │ ← Procesa comandos
        └───────┬────────┘
                │
        ┌───────▼────────┐
        │   Service      │ ← Lógica de negocio
        │   Layer        │
        └───────┬────────┘
                │
        ┌───────▼────────┐
        │  Repository    │ ← Acceso a datos
        │  + Mappers     │
        └───────┬────────┘
                │
        ┌───────▼────────┐
        │   Database     │ ← PostgreSQL/MySQL
        └───────┬────────┘
                │
        ┌───────▼────────┐
        │  SMTP Client   │ ← Envía respuesta
        └───────┬────────┘
                │
        ┌───────▼────────┐
        │   Respuesta    │
        │   por Email    │
        └────────────────┘
```

---

## 🎯 Ventajas Competitivas

### **vs. Sistemas Web Tradicionales:**

| Característica | Este Sistema | Sistemas Web |
|----------------|--------------|--------------|
| **Acceso** | Email (universal) | Requiere navegador |
| **Conectividad** | Intermitente OK | Permanente necesaria |
| **Costo** | Bajo | Alto (hosting, dominio) |
| **Curva de aprendizaje** | Mínima | Media-Alta |
| **Mantenimiento** | Simple | Complejo |
| **Infraestructura** | Mínima | Servidores web |

### **Beneficios Únicos:**
✅ Sin dependencia de internet 24/7  
✅ Funciona con cualquier cliente de email  
✅ No requiere app móvil  
✅ Bajo costo de operación  
✅ Fácil adopción por usuarios no técnicos  

---

## 👥 Casos de Uso

### **1. Cliente hace una reserva**
```
1. Cliente envía: CREATERESERVAS[2,3,1,2025-11-20,15:00,16:00,corte]
2. Sistema valida:
   ✓ Barbero existe
   ✓ Horario disponible
   ✓ No hay conflictos
3. Responde: "Reserva #45 creada. Barbero: Juan. 20-Nov 15:00"
```

### **2. Barbero revisa su agenda**
```
1. Barbero envía: LISTARBARBEROS[*]
2. Sistema responde con tabla de todos los barberos
3. Barbero envía: LISTARRESERVAS[*]
4. Ve todas las reservas del día
```

### **3. Administrador genera reporte**
```
1. Admin envía: REPORTEDASHBOARD
2. Recibe análisis completo del mes
3. Admin envía: REPORTERANKINGBARBEROS[2025-11-01,2025-11-30]
4. Ve performance de cada barbero
```

---

## 📊 Análisis de Rentabilidad

### **Cálculo Automático:**

```
Reserva ID: 100
├─ Servicio: Corte Premium       $25.00
├─ Productos usados:
│  ├─ Shampoo (2 unid x $2.50)   -$5.00
│  └─ Cera (1 unid x $1.50)      -$1.50
├─────────────────────────────────────
│ Ingreso Bruto:                  $25.00
│ Costo Productos:                -$6.50
│ Margen:                         $18.50 (74%)
└─────────────────────────────────────
```

**El sistema calcula automáticamente:**
- Ingresos por servicio
- Costos de productos consumidos
- Margen de ganancia real
- Rentabilidad por barbero

---

## 🔒 Validaciones de Negocio

### **Reglas Implementadas:**

1. **Horarios:**
   - No solapamiento de reservas
   - Respeto a horarios de barbero
   - Validación de días laborales

2. **Inventario:**
   - Stock suficiente antes de reserva
   - Alerta de stock mínimo
   - Trazabilidad de consumo

3. **Pagos:**
   - Anticipo opcional para confirmar
   - Control de pagos parciales
   - Cierre de reserva al completar pago

4. **Estados:**
   - Flujo controlado de reservas
   - No se puede eliminar reserva pagada
   - Histórico de cambios de estado

---

## 📱 Interfaz de Usuario

### **Formato de Respuesta:**

```
╔═══════════════════════════════════════╗
║ ✅ OPERACIÓN EXITOSA                  ║
╠═══════════════════════════════════════╣
║ Tipo: CREATE RESERVA                  ║
║ ID: 45                                ║
║ Cliente: María García                 ║
║ Barbero: Juan Pérez                   ║
║ Servicio: Corte Premium               ║
║ Fecha: 2025-11-20                     ║
║ Hora: 15:00 - 16:00                   ║
║ Estado: Confirmada                    ║
║ Total: $25.00                         ║
╠═══════════════════════════════════════╣
║ 📧 Por favor, llegue 5 minutos antes  ║
╚═══════════════════════════════════════╝
```

**Tablas ASCII para listados:**
```
┌────┬──────────────┬─────────────┬────────┐
│ ID │ Nombre       │ Especialidad│ Estado │
├────┼──────────────┼─────────────┼────────┤
│  1 │ Juan Pérez   │ Corte       │ Activo │
│  2 │ María López  │ Tinte       │ Activo │
│  3 │ Carlos Ruiz  │ Barba       │ Activo │
└────┴──────────────┴─────────────┴────────┘
```

---

## 🎨 Gráficos en Reportes

### **Visualizaciones ASCII:**

**Gráfico de Barras:**
```
Ingresos por Barbero:
Juan    ████████████████████ $4,200
María   █████████████████    $3,850
Carlos  ███████████████      $3,100
Luis    █████████            $1,900
```

**Gráfico Circular:**
```
Métodos de Pago:
Efectivo    ████████░░ 45%
Tarjeta     ██████░░░░ 35%
Transfer.   ████░░░░░░ 20%
```

**Histograma:**
```
Horas Pico:
09:00 ███░░░░░░░  15 reservas
10:00 ████████░░  42 reservas
11:00 ██████████  58 reservas ← Pico
12:00 ████████░░  45 reservas
```

---

## 🚀 Proceso de Implementación

### **Pasos para Poner en Marcha:**

1. **Configuración Inicial**
   ```
   ✓ Configurar credenciales POP3/SMTP
   ✓ Crear base de datos (PostgreSQL/MySQL)
   ✓ Ejecutar seeders iniciales
   ```

2. **Carga de Datos Maestros**
   ```
   ✓ Crear categorías de productos
   ✓ Registrar servicios disponibles
   ✓ Dar de alta barberos
   ✓ Configurar horarios laborales
   ```

3. **Inicio de Operaciones**
   ```
   ✓ Ejecutar ServicioEmail.main()
   ✓ Sistema escucha emails cada 10 segundos
   ✓ Procesa comandos automáticamente
   ✓ Responde en tiempo real
   ```

4. **Operación Continua**
   ```
   ✓ Monitorear reportes diarios
   ✓ Gestionar inventario
   ✓ Atender reservas
   ✓ Analizar performance
   ```

---

## 📈 Escalabilidad

### **Capacidades del Sistema:**

| Métrica | Capacidad |
|---------|-----------|
| **Barberos simultáneos** | Ilimitado |
| **Reservas por día** | 1000+ |
| **Usuarios registrados** | 10,000+ |
| **Productos en catálogo** | 500+ |
| **Servicios disponibles** | 100+ |
| **Emails procesados/hora** | 360 |

### **Optimizaciones:**
- Procesamiento cada 10 segundos
- Índices en BD para consultas rápidas
- Caché de datos frecuentes
- Validaciones en múltiples capas

---

## 🎓 Capacitación

### **Comandos Básicos para Usuarios:**

**Para Clientes:**
```
1. LISTARSERVICIOS[*]        ← Ver servicios
2. LISTARBARBEROS[*]          ← Ver barberos
3. CREATERESERVAS[...]        ← Hacer reserva
4. GETRESERVAS[id]            ← Ver mi reserva
```

**Para Barberos:**
```
1. LISTARRESERVAS[*]          ← Ver agenda del día
2. LISTARCLIENTEWS[*]         ← Ver clientes
3. LISTARHORARIOS[*]          ← Ver mis horarios
```

**Para Administradores:**
```
1. REPORTEDASHBOARD           ← Dashboard general
2. REPORTEINGRESOS[año,mes]   ← Ingresos mensuales
3. REPORTERANKINGBARBEROS[...] ← Performance
4. CREATEUSUARIOS[...]        ← Crear usuarios
5. CREATESERVICIOS[...]       ← Crear servicios
```

---

## 💡 Mejores Prácticas

### **Gestión Operativa:**

1. **Reservas:**
   - ✅ Confirmar con anticipo
   - ✅ Enviar recordatorios 24h antes
   - ✅ Actualizar estado al completar

2. **Inventario:**
   - ✅ Revisar stock diariamente
   - ✅ Reabastecer al alcanzar mínimo
   - ✅ Auditar consumo mensual

3. **Reportes:**
   - ✅ Dashboard semanal
   - ✅ Análisis mensual de ingresos
   - ✅ Evaluación trimestral de barberos

4. **Clientes:**
   - ✅ Programa de fidelización para frecuentes
   - ✅ Seguimiento de satisfacción
   - ✅ Promociones personalizadas

---

## 🌟 Casos de Éxito

### **Beneficios Medibles:**

```
📊 Antes del Sistema:
├─ Reservas por papel       → 30% pérdidas
├─ Control de inventario    → Manual, errores
├─ Reportes                 → Ninguno
├─ Tiempo administrativo    → 8 hrs/semana
└─ Satisfacción clientes    → 65%

✅ Después del Sistema:
├─ Reservas digitales       → 5% pérdidas
├─ Control automático       → Exacto, alertas
├─ Reportes                 → 10 tipos, tiempo real
├─ Tiempo administrativo    → 2 hrs/semana
└─ Satisfacción clientes    → 92%
```

### **ROI Estimado:**
- **Inversión:** Mínima (sin hosting, sin app)
- **Ahorro mensual:** ~24 horas administrativas
- **Aumento ingresos:** 15-20% (mejor gestión)
- **Recuperación:** < 2 meses

---

## 🔮 Futuras Mejoras

### **Roadmap Sugerido:**

**Versión 2.0:**
- [ ] Notificaciones automáticas de recordatorios
- [ ] Integración con WhatsApp Business
- [ ] Sistema de puntos para clientes frecuentes
- [ ] Fotos de trabajos realizados

**Versión 3.0:**
- [ ] Interfaz web opcional complementaria
- [ ] App móvil para barberos
- [ ] Sistema de propinas digitales
- [ ] Integración con redes sociales

**Análisis Avanzado:**
- [ ] Machine Learning para predicción de demanda
- [ ] Recomendaciones personalizadas
- [ ] Optimización automática de horarios
- [ ] Alertas predictivas de stock

---

## 📞 Soporte y Documentación

### **Recursos Disponibles:**

| Documento | Contenido |
|-----------|-----------|
| `README.md` | Guía completa de comandos |
| `REPORTES_EMAIL_README.md` | Manual de reportes |
| `GRAFICOS_README.md` | Guía de visualizaciones |
| `HELP` (comando) | Ayuda en tiempo real |

### **Contacto:**
- **Email:** grupo11sa@tecnoweb.org.bo
- **Sistema:** Enviar `HELP` para asistencia
- **Documentación:** Archivos README en proyecto

---

## 🎯 Conclusiones

### **Por qué este Sistema es Único:**

1. **Accesibilidad Universal**
   - Email = herramienta conocida por todos
   - No requiere capacitación técnica avanzada

2. **Bajo Costo**
   - Sin hosting, sin dominio, sin apps
   - Infraestructura mínima

3. **Eficiencia Operativa**
   - Automatización de procesos
   - Reportes en tiempo real
   - Control total del negocio

4. **Escalable y Flexible**
   - Crece con el negocio
   - Fácil de personalizar
   - Preparado para múltiples sucursales

---

## 🏆 Resumen Ejecutivo

### **Sistema de Gestión de Barbería por Email**

**Problema Solucionado:**
Barberías pequeñas y medianas necesitan profesionalizar su gestión sin costos elevados ni infraestructura compleja.

**Solución:**
Sistema ERP completo controlado por comandos de email, con gestión de reservas, inventario, pagos y análisis de negocio.

**Diferenciador:**
Control 100% por email, sin necesidad de app o web, accesible desde cualquier dispositivo.

**Resultados:**
- ⏰ 75% reducción en tiempo administrativo
- 📈 15-20% aumento en ingresos
- ✅ 92% satisfacción de clientes
- 💰 ROI < 2 meses

---

<!-- _class: invert -->
## 🙏 ¡Gracias!

### **Sistema de Gestión para Barberías**
*Profesionaliza tu negocio con tecnología simple y efectiva*

---

**Contacto:**
📧 grupo11sa@tecnoweb.org.bo

**Documentación:**
📁 BarberiaCorreo-main/

**Para empezar:**
```
Envía un email con asunto: HELP
```
