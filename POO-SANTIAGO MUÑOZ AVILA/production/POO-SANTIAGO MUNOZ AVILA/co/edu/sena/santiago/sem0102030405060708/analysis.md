# Análisis Orientado a Objetos - Empresa de Fumigación y Control de Plagas

## 1. Identificación del Dominio

**Nombre del negocio:** FumiControl S.A.S  
**Tipo:** Empresa de servicios ambientales  
**Descripción:** La empresa realiza fumigaciones, tratamientos contra insectos, control de roedores y manejo integral de plagas en hogares, locales y bodegas.

---

## 2. Objetos Identificados

### Objeto Principal: ServicioFumigacion
**¿Qué es?:**  
Representa un service que la empresa ofrece al cliente, incluyendo información sobre el tipo de plaga, área y precio.

**Atributos identificados:**
- `codigoServicio: String` – Identificador único del service.
- `tipoPlaga: String` – Tipo de plaga a tratar.
- `areaMetros: double` – Área total del lugar.
- `urgente: boolean` – Indica si requiere atención prioritaria.
- `precioBase: double` – Costo inicial del service.

**Métodos identificados:**
- `mostrarInformacion()` – Imprime datos del service.
- `calcularCostoTotal()` – Calcula el valor final del service.
- `getCodigoServicio()` – Obtiene el código.
- `setUrgente()` – Permite modificar si es urgente.

---

### Objeto Secundario: Cliente
**¿Qué es?:**  
Representa a un cliente que solicita uno o más servicios de fumigación.

**Atributos identificados:**
- `idCliente: String` – Identificador del cliente.
- `nombre: String` – Nombre completo.
- `direccion: String` – Ubicación donde se prestan los servicios.
- `serviciosRealizados: int` – Número de servicios consumidos.

**Métodos identificados:**
- `mostrarDatos()` – Imprime información del cliente.
- `registrarServicio()` – Incrementa los servicios usados.
- `esClienteFrecuente()` – Indica si ha solicitado varios servicios.

---

## 3. Relación entre Objetos

**Tipo de relación:** Asociación  
**Descripción:**  
Un **Cliente** puede tener múltiples **ServiciosFumigacion** en el tiempo.  
El service depende del cliente que lo solicita, pero ambos existen de forma independiente.

---

## 4. Justificación del Diseño

**¿Por qué elegí estos objetos?**  
Porque representan las dos entidades centrales del negocio: los clientes y los servicios prestados.

**¿Por qué estos atributos son importantes?**  
Permiten modelar características clave como área, urgencia, dirección y precios.

**¿Por qué estos métodos son necesarios?**  
Son la lógica real del negocio: calcular costos, mostrar datos, registrar servicios, etc.

---

## 5. Comparación: POO vs Programación Estructurada

### **Sin POO (estructurado)**
- Tendría variables sueltas para cada cliente y service.
- Sería difícil organizar los datos.
- Sería confuso reutilizar lógica como calcular costos.

### **Con POO**
- Los datos se agrupan en clases claras.
- Es escalable y fácil de mantener.
- Permite reutilizar métodos y crear más objetos sin duplicar código.

### **Ventajas específicas en este dominio**
1. Organización de múltiples servicios.
2. Gestión de clientes frecuente y lógica de negocio clara.
3. Facilita futuras expansiones (facturación, personal, inventario, etc.).

---

## 6. Diagrama de Clases (Opcional)

┌──────────────────────────┐ ┌──────────────────────┐
│ ServicioFumigacion │ │ Cliente │
├──────────────────────────┤ ├──────────────────────┤
│ - codigoServicio │ │ - idCliente │
│ - tipoPlaga │ │ - nombre │
│ - areaMetros │ │ - direccion │
│ - urgente │ │ - serviciosRealizados │
│ - precioBase │ ├──────────────────────┤
├──────────────────────────┤ │ + mostrarDatos() │
│ + mostrarInformacion() │ │ + registrarServicio() │
│ + calcularCostoTotal() │ │ + esClienteFrecuente()│
│ + getCodigoServicio() │ └──────────────────────┘
│ + setUrgente() │
└──────────────────────────┘