# 📚 Sistema de Gestión de Biblioteca

## 📖 Descripción del caso
El Sistema de Gestión de Biblioteca es una aplicación informática diseñada para optimizar la administración de recursos bibliográficos en instituciones pequeñas o medianas.  
Permite registrar libros, gestionar préstamos y devoluciones, y generar reportes básicos.  
Durante la evaluación se identificaron limitaciones como:
- Ausencia de control de disponibilidad de libros. 
- Falta de registro de usuarios.
- Reportes limitados y poco detallados.

Estas deficiencias afectan la trazabilidad, la confiabilidad de los datos y la satisfacción de los usuarios.

---

## 🎯 Objetivos
- Digitalizar procesos de préstamo y devolución de libros.
- Garantizar la trazabilidad de usuarios y ejemplares.
- Mejorar la confiabilidad y eficiencia del sistema.
- Incorporar validaciones automáticas para evitar duplicaciones.
- Ampliar la funcionalidad con reportes más completos y útiles.

---

## ⚙️ Requerimientos

### Funcionales
- **RF01:** Registro de nuevos libros con título, autor, ISBN único y cantidad de ejemplares.  
- **RF02:** Búsqueda de libros por título, autor o ISBN, mostrando disponibilidad y stock.  
- **RF03:** Registro de préstamos con validación de usuario y fecha automática.  
- **RF04:** Registro de devoluciones, actualizando disponibilidad y fecha real.  
- **RF05:** Generación de lista de préstamos activos con usuario y fecha límite.

### No Funcionales
- **RNF01:** Tiempo de respuesta en búsquedas ≤ 2 segundos (hasta 5,000 registros).  
- **RNF02:** Interfaz intuitiva, máximo 3 pasos para registrar un préstamo.  
- **RNF03:** Autenticación obligatoria para bibliotecarios en operaciones críticas.

---

## 🧪 Tabla de Pruebas

| ID Caso | Tipo de Prueba | Requerimiento Asociado | Datos de Entrada | Resultado Esperado | Resultado Simulado |
|---------|----------------|------------------------|-----------------|-------------------|-------------------|
| CPU-01  | Unitaria       | RF01 (Registro)        | Libro: "Análisis", Autor: Pressman, ISBN: 978-84-481-9964-1, Ejemplares: 5 | Registro exitoso con stock = 5 | ✅ Éxito |
| CPU-02  | Unitaria       | RF03 (Préstamo)        | ISBN: 978-84-481-9964-1, Usuario: 101 | Stock reducido a 4 | ✅ Éxito |
| CPU-03  | Unitaria       | RF04 (Devolución)      | ID Préstamo: P-001 | Stock incrementado a 5 | ✅ Éxito |
| CPV-01  | Validación     | RF02 + RNF01           | Búsqueda por Autor: Pressman | Respuesta < 2s | ✅ 0.8s |
| CPV-02  | Validación     | RF03 + RNF03           | Préstamo sin credenciales | Operación rechazada | ✅ Bloqueado |

---

## 🔧 Tipo de mantenimiento propuesto
- **Correctivo:**  
  Resolver errores de validación en préstamos duplicados.  
  → Restablece la integridad de datos y evita inconsistencias.

- **Perfectivo:**  
  Incorporar un módulo de usuarios y control de disponibilidad.  
  → Mejora trazabilidad, confiabilidad y escalabilidad del sistema.

---

## 🔄 Reflexión sobre el control de versiones
El control de versiones es esencial para proyectos de software como este.  
Permite:
- **Historial de cambios:** registrar qué modificaciones se hicieron y por quién.  
- **Colaboración:** varios desarrolladores pueden trabajar en paralelo sin sobrescribir código.  
- **Mantenibilidad:** facilita revertir errores y comparar versiones anteriores.  
- **Evolución continua:** asegura que las mejoras correctivas y perfectivas se integren de manera ordenada.  

En este caso, aplicar control de versiones (ej. Git) garantizaría que las correcciones de validación y la incorporación del módulo de usuarios se documenten y gestionen adecuadamente, evitando pérdida de información y asegurando la calidad del sistema.

---

## ✅ Conclusión
El Sistema de Gestión de Biblioteca requiere mejoras técnicas y organizativas para cumplir con los objetivos planteados.  
La combinación de pruebas, mantenimiento correctivo y perfectivo, junto con un control de versiones disciplinado, asegura la evolución sostenible del software y su alineación con las necesidades reales de los usuarios.

Última actualización: 15 de noviembre de 2025
