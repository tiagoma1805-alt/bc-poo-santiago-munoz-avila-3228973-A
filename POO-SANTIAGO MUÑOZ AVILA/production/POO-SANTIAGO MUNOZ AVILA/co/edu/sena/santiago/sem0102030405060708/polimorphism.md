# POLIMORFISMO – Semana 05
## Empresa: Fumigación y Control de Plagas

---

# 1. Sobrecarga (Overloading)

### Métodos sobrecargados:
- buscar(String plaga)
- buscar(int areaMinima)
- buscar(double min, double max)

### Justificación
En una empresa de fumigación se suelen buscar servicios por:
- El tipo de plaga atendida
- El área de la intervención
- El costo estimado del servicio

Por eso la sobrecarga es útil y natural en este dominio.

---

# 2. Sobrescritura (Overriding)

### Métodos sobrescritos:
| Método              | Clase Padre | ServicioFumigacion | ServicioDesinfeccion |
|--------------------|-------------|---------------------|-----------------------|
| calcularCosto()     | precio base x área | agrega bono por infestación | agrega costo por certificado |
| obtenerDescripcion() | descripción general | incluye plaga y nivel | incluye producto y certificado |

---

# 3. Polimorfismo Dinámico (Dynamic Binding)

### Ejemplo
```java
Servicio s = new ServicioFumigacion("Cucarachas", "alto", 15000, 80);
System.out.println(s.calcularCosto());  // Llama al método de la subclase
