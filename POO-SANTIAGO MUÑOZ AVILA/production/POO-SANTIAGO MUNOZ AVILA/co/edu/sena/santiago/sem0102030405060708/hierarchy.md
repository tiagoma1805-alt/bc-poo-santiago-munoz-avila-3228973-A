# Jerarquía de Clases - Semana 04

## Diagrama

Empleado  
│  
├── EmpleadoFijo  
└── EmpleadoPorContrato

## Justificación
La empresa de fumigación y control de plagas maneja diferentes tipos de employees:
- Técnicos de planta con experiencia variable
- Técnicos contratistas por service

Ambos comparten atributos en común (nombre, identificación, salario base), por lo que una clase padre evita duplicación y mejora la organización.

## Atributos heredados
- nombre (String)
- identificacion (String)
- salarioBase (double)

## Métodos sobrescritos
### calcularSalario()
- `EmpleadoFijo`: aplica bono por años de experiencia
- `EmpleadoPorContrato`: mantiene el salario base sin bonos

Esto demuestra polimorfismo en tiempo de ejecución.
