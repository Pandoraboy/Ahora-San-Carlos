# Ahora San Carlos

Aplicación móvil para descubrir puntos de interés de la comuna de San Carlos y facilitar la comunicación entre sus habitantes mediante espacios de conversación asociados al territorio.

El proyecto será desarrollado como tesis durante el período comprendido entre agosto y diciembre de 2026. El repositorio se utilizará para documentar el proceso, almacenar los avances y construir el sistema de manera incremental.

---

## Estado del proyecto

**Etapa actual:** definición y planificación inicial.

**Período de desarrollo:** agosto a diciembre de 2026.

**Plataformas objetivo:**

* Android
* iOS

**Tecnologías principales:**

* Laravel
* Flutter
* Base de datos relacional
* API REST

---

## Descripción

Ahora San Carlos permitirá que una persona pueda consultar lugares útiles dentro de la comuna, revisar su información y encontrarlos mediante un mapa.

En su primera versión, la aplicación trabajará con las siguientes categorías:

* Tiendas
* Plazas
* Cajeros automáticos
* Farmacias

La aplicación también contará con espacios de conversación para la comunidad. Existirá un chat general de San Carlos y chats territoriales vinculados a las cuatro plazas consideradas dentro del sistema.

El proyecto se concentra en información local y comunicación comunitaria. Las funciones relacionadas con delivery, transporte de productos o gestión de pedidos quedan fuera del alcance de esta etapa.

---

## Problema

La información sobre servicios y lugares de interés de San Carlos se encuentra distribuida entre mapas, redes sociales, publicaciones y recomendaciones informales.

Esto dificulta tareas cotidianas como:

* Encontrar un cajero cercano.
* Consultar dónde hay una farmacia.
* Identificar tiendas de una categoría determinada.
* Conocer las plazas disponibles.
* Conversar con personas vinculadas a un sector específico.

Ahora San Carlos busca reunir esta información en una aplicación centrada en la comuna y organizada según las necesidades de sus habitantes.

---

## Objetivo general

Desarrollar una aplicación móvil multiplataforma que permita consultar puntos de interés de San Carlos y participar en espacios de comunicación comunitaria vinculados a la comuna y sus plazas.

---

## Objetivos específicos

1. Diseñar una base de datos normalizada para administrar usuarios, lugares, categorías, plazas, chats y mensajes.

2. Desarrollar una API REST con Laravel para centralizar la lógica del sistema.

3. Construir una aplicación móvil con Flutter compatible con Android e iOS.

4. Implementar un mapa para visualizar puntos de interés dentro de San Carlos.

5. Permitir la búsqueda y filtrado de lugares según su categoría.

6. Crear un chat general para la comuna.

7. Crear un espacio de conversación independiente para cada plaza registrada.

8. Aplicar autenticación y autorización para proteger las funciones asociadas a los usuarios.

9. Documentar el proceso de análisis, diseño, implementación y pruebas.

---

## Alcance inicial

### Incluido

* Registro e inicio de sesión.
* Administración básica del perfil del usuario.
* Visualización de puntos de interés en un mapa.
* Consulta de información de cada lugar.
* Clasificación de lugares por categoría.
* Búsqueda y filtros.
* Chat general de San Carlos.
* Chat independiente para cada plaza.
* Envío y consulta de mensajes.
* Administración de lugares y categorías.
* Compatibilidad con Android e iOS.
* Consumo de una API REST desde Flutter.

### Fuera del alcance

* Delivery.
* Gestión de pedidos.
* Pagos dentro de la aplicación.
* Seguimiento de repartidores.
* Venta directa de productos.
* Reservas.
* Cobros a comercios.
* Expansión inicial hacia otras comunas.
* Mensajería privada entre usuarios.

Estas funciones podrían evaluarse después de finalizar la primera versión, pero no forman parte de los objetivos de la tesis.

---

## Actores del sistema

### Visitante

Persona que todavía no ha iniciado sesión.

Podrá:

* Revisar información pública.
* Consultar puntos de interés.
* Visualizar categorías y lugares.
* Registrarse.
* Iniciar sesión.

### Usuario registrado

Habitante o visitante que posee una cuenta.

Podrá:

* Utilizar todas las funciones públicas.
* Participar en el chat general.
* Participar en los chats de las plazas.
* Administrar la información básica de su perfil.
* Reportar contenido inapropiado, si esta función alcanza a implementarse.

### Administrador

Responsable de mantener la información del sistema.

Podrá:

* Crear, editar y desactivar lugares.
* Administrar categorías.
* Administrar plazas.
* Revisar usuarios.
* Moderar mensajes.
* Revisar reportes.
* Mantener actualizada la información publicada.

---

## Módulos principales

### 1. Autenticación

Gestionará:

* Registro.
* Inicio de sesión.
* Cierre de sesión.
* Recuperación de acceso.
* Perfil del usuario.
* Tokens de autenticación.

### 2. Puntos de interés

Gestionará los lugares registrados dentro de San Carlos.

Cada punto podrá contener:

* Nombre.
* Descripción.
* Categoría.
* Dirección.
* Latitud.
* Longitud.
* Horario.
* Teléfono.
* Imagen.
* Estado.
* Fecha de actualización.

### 3. Categorías

Permitirá organizar los puntos de interés.

Categorías iniciales:

* Tienda.
* Plaza.
* Cajero automático.
* Farmacia.

El modelo debe permitir agregar categorías nuevas sin modificar la estructura principal del sistema.

### 4. Mapa

Permitirá:

* Mostrar puntos de interés.
* Diferenciar lugares mediante iconos.
* Seleccionar un marcador.
* Consultar la información del lugar.
* Filtrar marcadores por categoría.
* Centrar el mapa en San Carlos.
* Utilizar la ubicación del dispositivo cuando el usuario otorgue permiso.

### 5. Chat comunitario

El sistema tendrá dos niveles de conversación.

#### Chat general

Espacio común para usuarios de San Carlos.

#### Chats por plaza

Cada plaza registrada tendrá su propio chat.

Estructura inicial:

* Plaza 1.
* Plaza 2.
* Plaza 3.
* Plaza 4.

Los nombres definitivos se incorporarán cuando se registren las plazas reales consideradas por el proyecto.

### 6. Administración

Permitirá mantener los datos del sistema sin modificar directamente la base de datos.

Funciones previstas:

* Gestión de usuarios.
* Gestión de lugares.
* Gestión de categorías.
* Gestión de plazas.
* Moderación de mensajes.
* Activación y desactivación de registros.

---

## Modelo conceptual inicial

### Entidades principales

* Usuario
* Rol
* Lugar
* Categoría
* Plaza
* Sala de chat
* Mensaje
* Reporte
* Imagen

### Relaciones principales

* Un rol puede estar asociado a muchos usuarios.
* Un usuario pertenece a un rol.
* Una categoría puede clasificar muchos lugares.
* Un lugar pertenece a una categoría.
* Una plaza puede estar representada como un lugar.
* Una sala de chat puede estar asociada a una plaza.
* El chat general no necesita estar asociado a una plaza.
* Una sala de chat contiene muchos mensajes.
* Un usuario puede enviar muchos mensajes.
* Un mensaje pertenece a una sala y a un usuario.
* Un usuario puede generar reportes sobre mensajes.
* Un lugar puede tener una o más imágenes.

---

## Arquitectura general

El sistema estará dividido en tres componentes principales.

```text
┌───────────────────────────┐
│       Aplicación móvil    │
│          Flutter          │
│                           │
│  Interfaz, estados, mapa  │
│  formularios y navegación │
└─────────────┬─────────────┘
              │
              │ HTTPS / JSON
              ▼
┌───────────────────────────┐
│         API REST          │
│          Laravel          │
│                           │
│ Autenticación, reglas de  │
│ negocio y autorización    │
└─────────────┬─────────────┘
              │
              │ ORM / Eloquent
              ▼
┌───────────────────────────┐
│      Base de datos        │
│         relacional        │
│                           │
│ Usuarios, lugares, chats  │
│ mensajes y categorías     │
└───────────────────────────┘
```

### Responsabilidad de Flutter

Flutter se encargará de:

* Mostrar las pantallas.
* Administrar los estados de la interfaz.
* Capturar eventos del usuario.
* Consumir la API.
* Renderizar los datos recibidos.
* Mostrar el mapa.
* Actualizar visualmente los chats.
* Almacenar de manera segura el token de acceso.

### Responsabilidad de Laravel

Laravel se encargará de:

* Validar solicitudes.
* Aplicar reglas de negocio.
* Autenticar usuarios.
* Autorizar acciones.
* Consultar y modificar la base de datos.
* Entregar respuestas JSON.
* Moderar el acceso a salas y mensajes.
* Mantener una estructura centralizada para la aplicación móvil.

---

## Flujo general del sistema

```text
Usuario abre la aplicación
        ↓
Flutter revisa si existe una sesión
        ↓
El usuario inicia sesión o continúa como visitante
        ↓
Flutter solicita información a la API
        ↓
Laravel valida la solicitud
        ↓
Laravel consulta la base de datos
        ↓
La API devuelve una respuesta JSON
        ↓
Flutter actualiza su estado
        ↓
La interfaz muestra lugares, chats o mensajes
```

---

## Flujo del mapa

```text
Usuario entra al mapa
        ↓
Flutter solicita los lugares activos
        ↓
Laravel consulta lugares y categorías
        ↓
La API devuelve coordenadas e información
        ↓
Flutter crea los marcadores
        ↓
Usuario selecciona un punto
        ↓
La aplicación muestra el detalle del lugar
```

---

## Flujo del chat

```text
Usuario selecciona una sala
        ↓
Flutter solicita los mensajes
        ↓
Laravel verifica la autenticación
        ↓
La API devuelve el historial permitido
        ↓
Usuario escribe un mensaje
        ↓
Flutter envía el contenido a Laravel
        ↓
Laravel valida y almacena el mensaje
        ↓
La conversación se actualiza
```

La primera versión podrá utilizar actualización periódica de mensajes. La comunicación en tiempo real mediante WebSockets se evaluará según el avance y el tiempo disponible.

---

## Estados principales en Flutter

La interfaz se modelará mediante estados explícitos.

### Estado de autenticación

```text
Inicial
  ↓
Comprobando sesión
  ├── Sesión activa
  ├── Sesión expirada
  └── Sin sesión
```

### Estado de puntos de interés

```text
Inicial
  ↓
Cargando
  ├── Datos disponibles
  ├── Sin resultados
  └── Error
```

### Estado del chat

```text
Inicial
  ↓
Cargando mensajes
  ├── Conversación disponible
  ├── Conversación vacía
  └── Error
```

### Estado de envío de mensaje

```text
Escribiendo
  ↓
Enviando
  ├── Enviado
  └── Error de envío
```

---

## Estructura propuesta del repositorio

Inicialmente se puede trabajar con un repositorio principal dividido en backend, aplicación móvil y documentación.

```text
ahora-san-carlos/
│
├── backend/
│   ├── app/
│   ├── config/
│   ├── database/
│   ├── routes/
│   ├── tests/
│   └── README.md
│
├── mobile/
│   ├── lib/
│   ├── assets/
│   ├── test/
│   └── README.md
│
├── docs/
│   ├── arquitectura/
│   ├── base-de-datos/
│   ├── diagramas/
│   ├── requisitos/
│   ├── pruebas/
│   └── tesis/
│
├── .gitignore
├── CHANGELOG.md
└── README.md
```

Esta organización permitirá separar el código de la documentación sin perder la relación entre ambos componentes.

---

## Organización propuesta del backend

```text
backend/app/
│
├── Http/
│   ├── Controllers/
│   ├── Middleware/
│   └── Requests/
│
├── Models/
├── Policies/
├── Services/
└── Exceptions/
```

### Capas iniciales

* **Models:** representación de entidades y relaciones.
* **Requests:** validación de datos de entrada.
* **Controllers:** recepción de solicitudes y construcción de respuestas.
* **Services:** reglas de negocio que no deben quedar dentro de los controladores.
* **Policies:** autorización de acciones.
* **Routes:** definición de endpoints.

---

## Organización propuesta de Flutter

```text
mobile/lib/
│
├── core/
│   ├── constants/
│   ├── errors/
│   ├── network/
│   ├── routes/
│   └── theme/
│
├── features/
│   ├── auth/
│   ├── places/
│   ├── map/
│   ├── chat/
│   └── profile/
│
└── main.dart
```

Cada funcionalidad podrá dividirse internamente en:

```text
feature/
├── data/
├── domain/
└── presentation/
```

La estructura definitiva se ajustará según la complejidad real del proyecto. La prioridad será mantener una separación clara entre datos, lógica y presentación.

---

## API inicial prevista

### Autenticación

```http
POST /api/register
POST /api/login
POST /api/logout
GET  /api/user
PUT  /api/user
```

### Categorías

```http
GET    /api/categories
POST   /api/categories
GET    /api/categories/{id}
PUT    /api/categories/{id}
DELETE /api/categories/{id}
```

### Lugares

```http
GET    /api/places
POST   /api/places
GET    /api/places/{id}
PUT    /api/places/{id}
DELETE /api/places/{id}
```

### Plazas

```http
GET    /api/plazas
POST   /api/plazas
GET    /api/plazas/{id}
PUT    /api/plazas/{id}
DELETE /api/plazas/{id}
```

### Salas de chat

```http
GET /api/chat-rooms
GET /api/chat-rooms/{id}
GET /api/chat-rooms/{id}/messages
```

### Mensajes

```http
POST   /api/chat-rooms/{id}/messages
PUT    /api/messages/{id}
DELETE /api/messages/{id}
```

Las rutas administrativas deberán estar protegidas mediante autenticación, roles y políticas de autorización.

---

## Requisitos funcionales iniciales

| Código | Requisito                                                  |
| ------ | ---------------------------------------------------------- |
| RF-01  | El sistema permitirá registrar usuarios.                   |
| RF-02  | El sistema permitirá iniciar y cerrar sesión.              |
| RF-03  | El sistema mostrará puntos de interés en un mapa.          |
| RF-04  | El usuario podrá filtrar lugares por categoría.            |
| RF-05  | El usuario podrá consultar el detalle de un lugar.         |
| RF-06  | El usuario registrado podrá ingresar al chat general.      |
| RF-07  | El usuario registrado podrá ingresar al chat de una plaza. |
| RF-08  | El usuario registrado podrá enviar mensajes.               |
| RF-09  | El administrador podrá gestionar lugares.                  |
| RF-10  | El administrador podrá gestionar categorías.               |
| RF-11  | El administrador podrá gestionar plazas.                   |
| RF-12  | El administrador podrá moderar mensajes.                   |

---

## Requisitos no funcionales iniciales

| Código | Requisito                                                                |
| ------ | ------------------------------------------------------------------------ |
| RNF-01 | La aplicación deberá funcionar en Android e iOS.                         |
| RNF-02 | La comunicación con el servidor deberá realizarse mediante HTTPS.        |
| RNF-03 | Las contraseñas deberán almacenarse mediante mecanismos seguros de hash. |
| RNF-04 | La API deberá entregar respuestas JSON consistentes.                     |
| RNF-05 | Las funciones administrativas deberán estar protegidas por roles.        |
| RNF-06 | La interfaz deberá adaptarse a diferentes tamaños de pantalla.           |
| RNF-07 | El sistema deberá manejar estados de carga, error y ausencia de datos.   |
| RNF-08 | La base de datos deberá mantener integridad referencial.                 |
| RNF-09 | El código deberá mantenerse versionado mediante Git.                     |
| RNF-10 | Las funciones principales deberán contar con pruebas.                    |

---

## Plan de desarrollo

### Agosto: análisis y diseño

* Definir el problema.
* Redactar objetivos.
* Levantar requisitos funcionales y no funcionales.
* Definir actores.
* Construir casos de uso.
* Diseñar el modelo entidad-relación.
* Transformar el MER en modelo relacional.
* Diseñar la arquitectura.
* Crear los proyectos de Laravel y Flutter.
* Preparar el repositorio.

### Septiembre: backend

* Crear migraciones.
* Crear modelos y relaciones.
* Implementar autenticación.
* Crear controladores.
* Crear servicios.
* Crear rutas.
* Implementar roles y permisos.
* Probar endpoints con Postman.
* Documentar la API.

### Octubre: aplicación móvil

* Diseñar navegación.
* Implementar autenticación en Flutter.
* Conectar Flutter con Laravel.
* Crear listado de categorías.
* Crear listado y detalle de lugares.
* Implementar mapa y marcadores.
* Administrar estados de carga y error.

### Noviembre: chats e integración

* Crear chat general.
* Crear chats por plaza.
* Implementar envío de mensajes.
* Implementar actualización de conversaciones.
* Agregar moderación básica.
* Completar integración entre módulos.
* Realizar pruebas funcionales.

### Diciembre: cierre

* Corregir errores.
* Mejorar experiencia de uso.
* Ejecutar pruebas finales.
* Completar documentación.
* Preparar demostración.
* Finalizar informe de tesis.
* Publicar una versión estable del proyecto.

---

## Estrategia de avance diario

El proyecto se construirá mediante cambios pequeños y verificables.

Cada jornada debería terminar con al menos uno de estos resultados:

* Un requisito definido.
* Una entidad modelada.
* Una migración creada.
* Una relación implementada.
* Un endpoint funcionando.
* Una prueba registrada.
* Una pantalla terminada.
* Un estado de Flutter implementado.
* Una conexión con la API validada.
* Una sección de documentación actualizada.

La meta del “5 % diario” representa continuidad. Cada avance debe quedar registrado mediante un commit que explique claramente qué cambió.

### Ejemplos de commits

```bash
git commit -m "docs: define alcance inicial del proyecto"
git commit -m "docs: agrega requisitos funcionales"
git commit -m "feat: crea modelo y migración de categorías"
git commit -m "feat: implementa listado de lugares"
git commit -m "feat: conecta Flutter con endpoint de categorías"
git commit -m "fix: corrige validación al enviar mensajes"
git commit -m "test: agrega pruebas para autenticación"
```

---

## Convención de ramas

```text
main
develop
feature/nombre-funcionalidad
fix/nombre-correccion
docs/nombre-documentacion
```

Ejemplos:

```text
feature/autenticacion
feature/mapa-lugares
feature/chat-general
feature/chat-plazas
fix/envio-mensajes
docs/modelo-entidad-relacion
```

---

## Criterios para considerar terminado un avance

Una funcionalidad se considerará terminada cuando:

* Su propósito esté definido.
* Sus datos estén modelados.
* La API valide las entradas.
* La regla de negocio funcione.
* La respuesta pueda probarse.
* Flutter maneje los estados necesarios.
* Los errores previsibles estén controlados.
* Exista evidencia de prueba.
* La documentación esté actualizada.

---

## Instalación

Las instrucciones definitivas se incorporarán cuando estén creados los proyectos de Laravel y Flutter.

### Requisitos previstos

* PHP
* Composer
* Laravel
* Base de datos relacional
* Flutter SDK
* Dart
* Android Studio
* Xcode para compilaciones de iOS
* Git
* Postman

### Clonar el repositorio

```bash
git clone URL_DEL_REPOSITORIO
cd ahora-san-carlos
```

### Backend

```bash
cd backend
composer install
cp .env.example .env
php artisan key:generate
php artisan migrate
php artisan serve
```

### Aplicación móvil

```bash
cd mobile
flutter pub get
flutter run
```

---

## Documentación

La carpeta `docs` almacenará los documentos técnicos y académicos.

```text
docs/
├── requisitos/
├── casos-de-uso/
├── arquitectura/
├── base-de-datos/
├── api/
├── pruebas/
└── tesis/
```

Entre los documentos esperados se encuentran:

* Descripción del problema.
* Justificación.
* Objetivos.
* Alcance.
* Requisitos.
* Casos de uso.
* Modelo entidad-relación.
* Modelo relacional.
* Diagrama de arquitectura.
* Documentación de endpoints.
* Plan de pruebas.
* Registro de resultados.
* Decisiones técnicas.
* Evidencias del desarrollo.

---

## Registro de avances

Los cambios relevantes se documentarán en `CHANGELOG.md`.

Formato sugerido:

```markdown
## [0.1.0] - 2026-08-01

### Agregado

- Estructura inicial del repositorio.
- README general.
- Definición preliminar del alcance.
- Primer listado de requisitos.
```

---

## Versión mínima esperada

La tesis deberá entregar una versión funcional que permita:

1. Registrar e iniciar sesión.
2. Consultar lugares de San Carlos.
3. Filtrar lugares por categoría.
4. Visualizar los puntos en un mapa.
5. Consultar información de un lugar.
6. Participar en el chat general.
7. Participar en el chat de una plaza.
8. Administrar lugares y categorías.
9. Ejecutarse en Android.
10. Mantener una estructura compatible con iOS.

La publicación comercial en las tiendas de aplicaciones dependerá de las cuentas, certificados y procesos de revisión correspondientes. La compilación y compatibilidad con ambas plataformas formarán parte del diseño técnico.

---

## Posibles mejoras posteriores

Estas funciones se mantienen fuera de la primera entrega:

* Favoritos.
* Calificaciones y comentarios de lugares.
* Notificaciones.
* Eventos comunitarios.
* Alertas locales.
* Geolocalización en segundo plano.
* Chats en tiempo real mediante WebSockets.
* Panel web avanzado.
* Validación de comercios.
* Incorporación de nuevas comunas.
* Estadísticas de uso.

---

## Autor

Proyecto desarrollado como trabajo de tesis.

**Nombre:** [Nombre del estudiante]
**Institución:** [Institución]
**Carrera:** [Carrera]
**Año:** 2026

---

## Licencia

Este proyecto tiene fines académicos.

La licencia definitiva será establecida antes de publicar una versión distribuible.
