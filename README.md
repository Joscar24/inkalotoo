🎰 InkaLoto – Plataforma Web de Juegos y Sorteos en Línea

InkaLoto es una plataforma web desarrollada para la gestión de sorteos y juegos en línea, permitiendo a los usuarios registrarse, administrar su billetera digital, participar en juegos como bingo, tragamonedas y sorteos, y recibir notificaciones automáticas sobre premios y jugadas realizadas.

El sistema sigue una arquitectura MVC por capas implementada con JSF, CDI, JPA, DAOs y Services, garantizando una aplicación modular, mantenible y escalable.

🚀 Características principales
🔐 Registro y autenticación de usuarios

El usuario puede crear una cuenta y acceder mediante login seguro.

👛 Billetera digital

Recargas

Retiros

Movimientos de saldo

Historial completo

🎲 Juegos disponibles

Bingo automático

Tragamonedas 

Sorteos automáticos

🔔 Notificaciones en tiempo real

El usuario recibe notificaciones automáticas sobre:

Premios obtenidos

Resultados de sorteos

Movimientos de la billetera

📜 Historiales

Historial de jugadas

Historial de premios

Historial de transacciones

🛠 Tecnologías utilizadas
Frontend

JSF (JavaServer Faces) con XHTML

CSS puro (sin Bootstrap ni frameworks externos)

Backend

Java

JSF Managed Beans

CDI (Inyección de dependencias)

Servicios (Capa de lógica)

DAO (Acceso a BD con JPA)

EclipseLink

MySQL

Base de Datos

MySQL 8

Persistencia JPA con EclipseLink

Consultas y transacciones mediante DAOs

Servidor

GlassFish 7 / 8

Arquitectura

MVC por capas, separando:

Vista (XHTML)

Beans (Controladores JSF)

Servicios (Lógica)

DAOs (Acceso a BD)

Modelo JPA

🗂 Estructura del proyecto
inkaloto/
│
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/inkaloto/
│   │   │       ├── modelo/       # Entidades JPA (Usuario, Billetera, Jugada, etc.)
│   │   │       ├── dao/          # Clases DAO para consultas y persistencia
│   │   │       ├── servicio/     # Lógica del negocio (Services)
│   │   │       └── web/bean/     # Managed Beans (controladores JSF)
│   │   │
│   │   ├── resources/
│   │   │   └── META-INF/persistence.xml  # Configuración JPA
│   │   │
│   │   └── webapp/               # Vista (XHTML)
│   │       ├── *.xhtml           # Todas las páginas UI
│   │       ├── css/              # Estilos personalizados
│   │       ├── imagenes/         # Recursos gráficos
│   │       └── WEB-INF/
│   │           └── beans.xml     # Activación de CDI
│   │
│   └── database/
│       └── prueba1.sql           # Script SQL para crear la base de datos
│
├── pom.xml                       # Dependencias Maven
└── README.md                     # Este archivo

🧠 Arquitectura interna (Backend)

Tu proyecto usa una arquitectura profesional en capas:

🟦 1. Managed Beans (JSF)

Ubicación:
src/main/java/com/inkaloto/web/bean/

Función:
Controladores de la vista.
Conectan los formularios XHTML con los servicios y la lógica.

Ejemplos:
LoginBean, CargarSaldoBean, BingoBean, TragamonedasBean, MiCuentaBean.

🟩 2. CDI (Inyección de Dependencias)

Ubicación:
WEB-INF/beans.xml

Permite:

Usar @Named para exponer beans a JSF

Manejar el ciclo de vida (@RequestScoped, @SessionScoped)

Inyectar Beans dentro de otros Beans con @Inject

Ejemplo real:

@Inject
private LoginBean loginBean;

🟨 3. Servicios (Lógica de negocio)

Ubicación:
src/main/java/com/inkaloto/servicio/

Qué hacen:

Manejan las reglas del juego

Validan datos

Actualizan saldo

Registran apuestas y premios

Generan números ganadores

Ejemplos:

UsuarioService

BilleteraService

JugadaService

SorteoService

🟥 4. DAOs (Acceso a la Base de Datos)

Ubicación:
src/main/java/com/inkaloto/dao/

Qué hacen:

Ejecutan consultas y transacciones JPA

Guardan y actualizan entidades

No contienen lógica del negocio

Ejemplos:

UsuarioDAO

MovimientoBilleteraDAO

SorteoDAO

🟪 5. Modelo (Entidades JPA)

Ubicación:
src/main/java/com/inkaloto/modelo/

Representan tablas de la base de datos.
Ejemplo:

Usuario

BilleteraUsuario

MovimientoBilletera

Jugada

Sorteo

Notificacion

📦 Instalación y Ejecución
1️⃣ Clonar el proyecto
git clone https://github.com/jeonxvix/inkalotoo.git

2️⃣ Configurar la base de datos

Crear la base:

CREATE DATABASE inkaloto;


Importar el script:

/database/prueba1.sql

3️⃣ Configurar GlassFish

Entrar a Admin Console

Ir a: Applications > Deploy

Subir el .war generado por Maven

Iniciar la aplicación

Acceso (ejemplo):

http://localhost:8080/inkaloto

🛠 Dependencias principales (pom.xml)

EclipseLink – JPA Provider

Jakarta Faces – JSF

CDI – Inyección de dependencias

Jakarta Persistence – ORM

MySQL Connector/J – Conexión BD

Jakarta Servlet API

🤝 Contribuciones

Hacer fork

Crear rama: nueva-funcionalidad

Commit:

git commit -am "Añadí nueva funcionalidad"


Push

Crear Pull Request

📜 Licencia

Proyecto licenciado bajo MIT License.

📧 Contacto

Si necesitas soporte o más información:
joscarcornejo@gmail.com

🎉 ¡Gracias por usar InkaLoto!
