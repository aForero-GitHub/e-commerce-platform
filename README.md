# E-Commerce Project

## Durante los próximos 6 días (a partir del 28/SEP/2024), podrá acceder a este demo funcional en <a href="https://e-commerce-platform.payloadcms.app/" target="_blank">e-commerce-adforeroma</a>.

Este proyecto es un ejercicio de implementación de una plataforma de comercio electrónico con funcionalidades básicas como la gestión de catálogos de productos y la gestión de pedidos. La solución incluye un backend totalmente funcional, un panel de administración y un sitio web bien diseñado y listo para producción.

## Tecnologías Utilizadas

- **Frontend**: Next.js (React), TypeScript, React Hook Form, SEO Plugin
- **Backend**: Node.js, Express
- **Base de Datos**: MongoDB
- **Autenticación y Control de Acceso**: Payload CMS
- **Pago**: Integración con Stripe
- **Despliegue**: Docker y Docker Compose
- **Gestión de Contenedores**: Docker
- **Control de Versiones**: Git

## Características Principales

- Autenticación de usuarios y gestión de roles (cliente y administrador)
- Carrito de compras y proceso de checkout
- Gestión de productos y categorías
- Gestión de pedidos
- Módulo de SEO y Paywall
- Configuración de un pipeline CI/CD
- Creación de productos digitales y físicos
- Integración con Stripe para procesamiento de pagos

## Arquitectura

La solución sigue una arquitectura monolítica basada en Node.js y Next.js, donde todas las funcionalidades están centralizadas en un solo contenedor Docker. Los principales componentes del proyecto son:

1. **Frontend**: La aplicación frontend se desarrolló con Next.js y TypeScript. Ofrece la funcionalidad de un e-commerce con capacidad de autenticación, carrito de compras y checkout.

2. **Backend**: El backend está construido sobre Node.js y utiliza Payload CMS para la gestión de contenido y administración de usuarios.

3. **Base de Datos**: MongoDB es la base de datos principal utilizada para almacenar información de productos, pedidos y usuarios.

4. **Servicios de Pago**: La integración con Stripe permite manejar el procesamiento de pagos y sincronizar la información de productos entre Stripe y la aplicación.

5. **Despliegue y Orquestación**: Docker Compose se utiliza para orquestar los contenedores del backend y la base de datos.

### Diagrama de Arquitectura
(Adjunta aquí tu diagrama de arquitectura en formato visual)

## Cómo Iniciar el Proyecto Localmente

### Clonación del Repositorio

Clona el repositorio a tu máquina local:

```bash
git clone https://github.com/tu-repositorio/e-commerce-project.git
cd e-commerce-project
```

### Configuración de Entorno

1. Copia el archivo de variables de entorno de ejemplo:
   ```bash
   cp .env.example .env
   ```

2. Completa las variables de entorno en el archivo `.env` con tus credenciales y configuraciones.

### Ejecución del Proyecto

Para iniciar la aplicación localmente utilizando Docker:

1. Asegúrate de tener Docker y Docker Compose instalados.
2. Ejecuta el siguiente comando:
   ```bash
   docker-compose up
   ```

Esto levantará los contenedores de Node.js y MongoDB, y tu aplicación estará disponible en `http://localhost:3000`.

## Gestión del Proyecto

### Autenticación

El sistema de autenticación se implementa a través de Payload CMS, lo que permite gestionar roles de usuarios para administradores y clientes. Esto se maneja a través del control de acceso basado en roles (RBAC).

### Integración con Stripe

La integración con Stripe permite gestionar los pagos de productos. Sigue estos pasos para configurarlo:

1. Crea una cuenta en [Stripe](https://stripe.com) si no tienes una.
2. Coloca tus credenciales de Stripe en el archivo `.env`:
   ```bash
   STRIPE_SECRET_KEY=tu_secreto
   NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY=tu_clave_publicable
   ```

3. Inicia los webhooks de Stripe:
   ```bash
   stripe login # Sigue los pasos de autenticación
   yarn stripe:webhooks
   ```

## Desarrollo y Contribución

### Instalación de Dependencias

Para instalar las dependencias del proyecto, ejecuta:

```bash
yarn install
```

### Scripts de Desarrollo

- `yarn dev`: Inicia el entorno de desarrollo.
- `yarn build`: Genera el proyecto para producción.
- `yarn serve`: Inicia la aplicación en modo de producción.

### Semilla de Datos

Para poblar la base de datos con algunos productos y páginas de ejemplo, ejecuta:

```bash
yarn seed
```

## Pipeline CI/CD

El proyecto cuenta con una configuración básica de CI/CD utilizando GitHub Actions. Cada cambio en el repositorio activa la ejecución de los siguientes pasos:

1. Instalación de dependencias.
2. Construcción del proyecto.
3. Pruebas unitarias.
4. Generación de un changelog basado en los mensajes de commits.

El archivo de configuración se encuentra en `.github/workflows`.

## Despliegue

Para desplegar la aplicación en un entorno de producción:

1. Construye el proyecto:
   ```bash
   yarn build
   ```

2. Sirve la aplicación:
   ```bash
   yarn serve
   ```

### Opciones de Despliegue

- **Local**: Usando Docker y Docker Compose
- **Cloud**: Puedes optar por cualquier proveedor de cloud, como AWS o Azure, y simular la configuración utilizando LocalStack para fines de pruebas locales.

## Notas Adicionales

- La arquitectura monolítica utilizada facilita el desarrollo rápido y la prueba del proyecto.
- El proyecto es escalable y se puede migrar a una arquitectura de microservicios si se desea en el futuro.
- He redactado un breve artículo que podría resultarle de interés para conocer más sobre las tecnologías utilizadas en este proyecto: <a href="https://www.linkedin.com/pulse/building-e-commerce-solutions-faster-than-ever-power-forero-martinez-5dsce" target="_blank">Andrés David Forero Martínez - LinkedIn</a>.

