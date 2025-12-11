ANALISIS.md

Aquí tienes el archivo COMPLETO adaptado al dominio:

ANALISIS.md — Semana 06 (Control de Plagas y Fumigación)
1. Identificación de Abstracciones
   ✔ Clase Abstracta: ServicioFumigacion

Razones:

Todos los servicios de la empresa comparten costo base y nombre.

El cálculo del costo total es diferente para cada servicio.

Requiere métodos comunes y plantillas reutilizables.

Jerarquía:

ServicioFumigacion
├── FumigacionDomestica
├── FumigacionIndustrial
└── ControlRoedores

2. Interfaces
   ✔ Interface 1: Inspeccionable

Capacidad: inspeccionar áreas y generar informes.
Implementada por:

ServicioPremium (porque incluye inspección avanzada)

Fumigación Industrial (requiere inspección por protocolos)

✔ Interface 2: Facturable

Capacidad: generar facturas.
Implementada por:

ServicioPremium

FumigacionDomestica

3. Decisiones de Diseño
   ✔ Clase abstracta vs Interface

La clase abstracta se usa porque:

Comparte atributos (estado).

Comparte comportamiento concreto reutilizable.

Las interfaces se usan porque:

Son capacidades independientes.

Permiten implementación múltiple.

4. Principios SOLID
   SRP

Cada clase tiene un rol único: Servicios, inspecciones, facturación.

OCP

Puedo crear nuevos servicios sin modificar los existentes.

LSP

Todas las subclases pueden ser tratadas como ServicioFumigacion.

ISP

Cada interface tiene métodos coherentes y específicos.

5. Mejoras logradas

Código más modular

Mayor reutilización

Extensión más fácil

Mantenimiento más sencillo

6. Diagrama de Clases
   <<abstract>>
   ServicioFumigacion
   /        |        \
   Domestica   Industrial   ControlRoedores
   |
   implements Inspeccionable

7. Desafíos y soluciones

Desafío: elegir qué va en interface o abstracta
Solución: revisar si comparten atributos → abstracta

8. Próximos pasos

Agregar interfaz de PagoOnline

Incluir clase Auditoría

Mejorar informes de inspección