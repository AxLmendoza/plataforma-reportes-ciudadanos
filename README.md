# Plataforma de Reportes Ciudadanos

## 📌 Descripción del proyecto

La **Plataforma de Reportes Ciudadanos** es un proyecto orientado a centralizar y analizar los reportes relacionados con fallas o deficiencias en los servicios públicos de un municipio.

Actualmente, este tipo de reportes puede encontrarse disperso, lo que dificulta identificar cuáles son los problemas más frecuentes, en qué zonas se concentran y cuáles requieren una atención más urgente.

La plataforma busca convertir esta información dispersa en datos organizados que puedan ser consultados y analizados mediante un **mapa y un dashboard**, facilitando la toma de decisiones de las autoridades.

---

## 🎯 Objetivo general

Diseñar e implementar una plataforma que centralice y analice los reportes ciudadanos de fallas o deficiencias en servicios públicos del municipio, convirtiendo la información dispersa en datos organizados y útiles para que las autoridades puedan priorizar la atención de los problemas urbanos de forma objetiva.

---

## 📋 Alcance

La plataforma contempla las siguientes funcionalidades:

* Registro de reportes ciudadanos.
* Clasificación de reportes por tipo de problema.
* Registro de ubicación.
* Consulta de reportes.
* Filtrado por tipo de problema y zona.
* Detección de posibles reportes duplicados.
* Análisis de reportes por zona.
* Generación de una prioridad por zona.
* Visualización de reportes mediante un mapa.
* Dashboard con estadísticas e información relevante.

### Fuera del alcance

La plataforma no realizará directamente la reparación o atención de los problemas reportados.

Su función será **recopilar, organizar y analizar información para apoyar la toma de decisiones**.

---

# 👥 Equipo y metodología

## Metodología

El proyecto utiliza la metodología ágil **Scrum**, dividiendo el desarrollo en periodos cortos de trabajo llamados *sprints*.

Durante el proyecto se utilizarán:

* Product Backlog.
* Sprint Planning.
* Sprints.
* Reuniones de seguimiento.
* Sprint Review.
* Retrospective.

# 🔀 Flujo de trabajo con Git

El flujo de trabajo será:

```text
                    ┌─────────────┐
                    │    main     │
                    │   estable   │
                    └──────┬──────┘
                           │
                           ▼
                    Crear nueva rama
                           │
                           ▼
                    Desarrollar función
                           │
                           ▼
                         Commit
                           │
                           ▼
                    Subir a GitHub
                           │
                           ▼
                     Pull Request
                           │
                           ▼
                        Revisión
                       /        \
                     NO          SÍ
                     │            │
                     ▼            ▼
                Correcciones    Merge
                                  │
                                  ▼
                              main
```

## Reglas para ramas

Las ramas utilizarán la siguiente estructura:

```text
tipo/nombre-de-la-funcionalidad
```

Ejemplos:

```text
feature/registro-reportes
feature/mapa-reportes
feature/dashboard
feature/deteccion-duplicados
fix/validacion-formulario
docs/manual-tecnico
test/casos-reportes
```

### Reglas

* Utilizar letras minúsculas.
* No utilizar espacios.
* Separar palabras con `-`.
* Utilizar nombres descriptivos.
* No utilizar nombres como `rama1`, `prueba` o `cambios`.
* No desarrollar directamente sobre `main`.

---

# 📝 Reglas para commits

Los commits utilizarán la siguiente estructura:

```text
tipo: descripción del cambio
```

Tipos principales:

| Tipo       | Uso                             |
| ---------- | ------------------------------- |
| `feat`     | Nueva funcionalidad             |
| `fix`      | Corrección de errores           |
| `docs`     | Documentación                   |
| `test`     | Pruebas                         |
| `refactor` | Modificación interna del código |

Ejemplos:

```text
feat: agregar formulario de reportes
feat: agregar mapa de incidencias
fix: corregir validacion de ubicacion
test: agregar prueba de reportes duplicados
docs: actualizar README
```

---

# ⚙️ Enfoque DevOps

El proyecto aplicará un enfoque DevOps para integrar las actividades de desarrollo, pruebas, entrega y monitoreo.

El flujo general será:

```text
Planificación
      ↓
Desarrollo
      ↓
Pruebas
      ↓
Integración
      ↓
Entrega / Despliegue
      ↓
Monitoreo
      ↓
Mejora
```

## Elementos DevOps utilizados

* Control de versiones.
* Repositorio compartido.
* Integración continua.
* Pruebas continuas.
* Entrega continua.
* Despliegue.
* Monitoreo.
* Colaboración entre integrantes.

---

# 🧪 Plan de pruebas

Las pruebas tienen como objetivo verificar que las principales funciones de la plataforma trabajen correctamente.

## Tipos de pruebas

* Pruebas funcionales.
* Pruebas de validación.
* Pruebas de integración.
* Pruebas de interfaz.
* Pruebas de regresión.

## Entorno de pruebas

Las pruebas se realizarán en un entorno de desarrollo/pruebas utilizando información simulada para evitar afectar información real.

---

# 🔍 Casos de prueba

## CP-01 — Registro correcto de un reporte

**Requisito:** HU-01

**Tipo:** Funcional

**Precondiciones:**

* La plataforma está disponible.
* El formulario de reportes está disponible.

**Datos:**

* Tipo: Alumbrado público.
* Descripción: La lámpara de la calle no enciende.
* Ubicación: Calle Principal, zona centro.

**Pasos:**

1. Abrir el formulario.
2. Seleccionar el tipo de problema.
3. Introducir la descripción.
4. Registrar la ubicación.
5. Enviar el formulario.

**Resultado esperado:**

El sistema registra correctamente el reporte y permite consultarlo posteriormente.

---

## CP-02 — Registro con información incompleta

**Requisito:** HU-01

**Tipo:** Validación / Error

**Precondiciones:**

* El formulario está disponible.

**Datos:**

* Tipo: Alumbrado público.
* Descripción: Vacía.
* Ubicación: Calle Principal.

**Pasos:**

1. Abrir el formulario.
2. Seleccionar el tipo.
3. Dejar vacía la descripción.
4. Introducir la ubicación.
5. Intentar enviar.

**Resultado esperado:**

El sistema muestra un mensaje indicando que falta información obligatoria y no registra el reporte.

---

## CP-03 — Consulta y filtrado

**Requisito:** HU-02

**Tipo:** Funcional

**Precondiciones:**

* Existen reportes registrados.

**Datos:**

```text
Tipo: Alumbrado público
Zona: Zona Centro
```

**Pasos:**

1. Abrir la consulta de reportes.
2. Seleccionar el tipo de problema.
3. Seleccionar la zona.
4. Ejecutar la búsqueda.

**Resultado esperado:**

El sistema muestra únicamente los reportes que corresponden a los filtros seleccionados.

---

## CP-04 — Visualización en mapa

**Requisito:** HU-03

**Tipo:** Funcional / Interfaz

**Precondiciones:**

* Existen reportes con ubicación registrada.

**Datos:**

Tres reportes ubicados en diferentes zonas.

**Pasos:**

1. Abrir el módulo del mapa.
2. Esperar a que cargue.
3. Revisar las ubicaciones.
4. Seleccionar un reporte.

**Resultado esperado:**

El mapa muestra correctamente las ubicaciones y permite consultar la información del reporte seleccionado.

---

## CP-05 — Detección de reporte duplicado

**Requisito:** HU-04

**Tipo:** Validación / Integración

**Precondiciones:**

* Existe un reporte registrado.
* La detección de duplicados está habilitada.

**Datos:**

Reporte existente:

```text
Tipo: Bache
Ubicación: Calle Principal, Zona Centro
Descripción: Bache de gran tamaño.
```

Nuevo reporte:

```text
Tipo: Bache
Ubicación: Calle Principal, Zona Centro
Descripción: Bache grande en la calle.
```

**Pasos:**

1. Registrar el primer reporte.
2. Intentar registrar el segundo.
3. Ejecutar la detección de duplicados.
4. Comparar la información.

**Resultado esperado:**

El sistema identifica el nuevo reporte como un posible duplicado y evita que sea contabilizado automáticamente como un incidente completamente independiente.

---

# 🚀 Estrategia de despliegue

La estrategia seleccionada es **PaaS (Platform as a Service)**.

PaaS permite desplegar una aplicación sin que el equipo tenga que administrar directamente toda la infraestructura del servidor. El material de la unidad señala que este modelo facilita el despliegue y permite concentrarse en la aplicación, mientras la plataforma gestiona aspectos de infraestructura, mantenimiento y escalabilidad.

Algunos ejemplos de plataformas PaaS estudiadas son:

* Vercel
* Heroku
* AWS Elastic Beanstalk
* Google App Engine
* Netlify
* Platform.sh
* Firebase

## Entornos

Se utilizarán tres entornos:

```text
Desarrollo → Pruebas → Producción
```

### Desarrollo

Utilizado por los integrantes para desarrollar nuevas funcionalidades.

### Pruebas

Utilizado para verificar una nueva versión antes de publicarla.

### Producción

Contendrá la versión estable disponible para los usuarios.

---

# ✅ Verificación de nuevas versiones

Antes de publicar una nueva versión se verificará:

* Funcionamiento de la aplicación.
* Registro de reportes.
* Almacenamiento de información.
* Consulta y filtros.
* Visualización del mapa.
* Funcionamiento del dashboard.
* Detección de posibles duplicados.
* Funcionamiento de las funcionalidades existentes.

Una versión podrá pasar a producción cuando las pruebas críticas sean satisfactorias y no existan errores que impidan utilizar la plataforma.

---

# ↩️ Recuperación ante fallas

Si una nueva versión presenta un error grave después del despliegue, se realizará un **rollback** hacia la última versión estable.

Proceso:

```text
Nueva versión
      ↓
¿Funciona correctamente?
    /       \
  NO         SÍ
  ↓           ↓
Rollback    Mantener
  ↓
Versión estable anterior
```

Git y GitHub permitirán consultar el historial de cambios y recuperar una versión anterior.

Después del rollback, el equipo analizará el problema, realizará la corrección en una nueva rama y volverá a ejecutar las pruebas antes de realizar otro despliegue.


# 📁 Estructura del repositorio

Se propone la siguiente estructura:

```text
plataforma-reportes-ciudadanos/
│
├── documentacion/
│
├── src/
│
├── pruebas/
│
├── README.md
│
└── .gitignore
```


## Funcionalidades planeadas

* [ ] Registro de reportes.
* [ ] Consulta de reportes.
* [ ] Filtros.
* [ ] Mapa de reportes.
* [ ] Detección de duplicados.
* [ ] Priorización por zona.
* [ ] Dashboard.
* [ ] Pruebas.
* [ ] Despliegue.
* [ ] Monitoreo.

---

# 📚 Referencias

* Material de la unidad sobre **Despliegue de Aplicaciones Web**, utilizado para seleccionar y justificar la estrategia PaaS.
* Material de apoyo ampliado sobre **Despliegue de Aplicaciones Web**, utilizado como apoyo para la comparación de alternativas de despliegue.

---

