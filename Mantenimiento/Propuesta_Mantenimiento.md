# 🔧 Propuesta de Mantenimiento del Sistema de Gestión de Biblioteca

## 📖 Introducción
El Sistema de Gestión de Biblioteca, desarrollado para optimizar el registro, préstamo y devolución de libros, presenta limitaciones que afectan su confiabilidad y eficiencia.  
Entre los principales problemas detectados se encuentran:
- Ausencia de control de disponibilidad de libros.
- Falta de registro y trazabilidad de usuarios.
- Reportes limitados para la toma de decisiones.

Con base en estas observaciones, se propone un plan de mantenimiento que combine acciones **correctivas** y **perfectivas**.

---

## 🛠 Tipos de mantenimiento aplicables

### 1. Mantenimiento Correctivo
- **Objetivo:** Corregir defectos que afectan la operación normal del sistema.  
- **Aplicación en el caso:**  
  - Resolver el error que permite préstamos duplicados sin validar disponibilidad.  
- **Justificación técnica:**  
  - Garantiza la integridad de los datos y evita inconsistencias en el inventario.  
- **Beneficio esperado:**  
  - Mayor confiabilidad en el control de ejemplares.

---

### 2. Mantenimiento Perfectivo
- **Objetivo:** Ampliar y mejorar la funcionalidad del sistema.  
- **Aplicación en el caso:**  
  - Incorporar un módulo de **usuarios** con datos básicos (ID, nombre, correo).  
  - Añadir un campo **estado** en la tabla de libros (Disponible/Prestado).  
  - Implementar validaciones automáticas antes de confirmar un préstamo.  
  - Mejorar el módulo de reportes con estadísticas de uso y préstamos vencidos.  
- **Justificación técnica:**  
  - Responde a necesidades evolutivas del sistema, mejorando trazabilidad y escalabilidad.  
- **Beneficio esperado:**  
  - Transparencia en la gestión, reducción de errores humanos y soporte a la toma de decisiones.

---

## 📂 Cambios funcionales propuestos
1. Crear tabla **Usuarios** en la base de datos.  
2. Modificar tabla **Libros** para incluir campo `Estado`.  
3. Relacionar **Usuarios** con **Préstamos** mediante identificador único.  
4. Incorporar formularios gráficos (GUI) para gestión de usuarios y préstamos.  
5. Añadir validaciones automáticas en la capa lógica antes de confirmar un préstamo.  

---

## 📊 Evaluación del impacto

| Criterio              | Antes del cambio | Después del cambio |
|-----------------------|------------------|--------------------|
| Control de disponibilidad | ❌ No | ✅ Sí |
| Registro de usuarios  | ❌ No | ✅ Sí |
| Confiabilidad de datos | Media | Alta |
| Trazabilidad          | Limitada | Completa |
| Mantenibilidad        | Media | Alta |
| Escalabilidad         | Baja | Alta |

---

## 🔄 Reflexión sobre el control de versiones
El uso de **control de versiones (Git/GitHub)** es esencial para gestionar este proceso de mantenimiento.  
Permite:
- Documentar cada cambio en el código y la base de datos.  
- Coordinar el trabajo en equipo sin sobrescribir avances.  
- Revertir errores y comparar versiones anteriores.  
- Mantener un historial claro de la evolución del sistema.  

En este proyecto, el control de versiones asegura que las mejoras correctivas y perfectivas se integren de manera ordenada, garantizando la calidad y sostenibilidad del software.

---

## ✅ Conclusión
La propuesta de mantenimiento permitirá que el Sistema de Gestión de Biblioteca evolucione hacia una solución más confiable, trazable y escalable.  
La combinación de **mantenimiento correctivo** y **perfectivo**, junto con el uso disciplinado de **control de versiones**, asegura que el sistema se mantenga alineado con las necesidades reales de los usuarios y preparado para futuras mejoras.
