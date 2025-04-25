# Despliegue de la Aplicación PokeDex en Azure Static Web Apps

Este documento describe el proceso paso a paso para desplegar la aplicación PokeDex en Azure Static Web Apps. Azure Static Web Apps es un servicio que compila y despliega aplicaciones web estáticas y/o front-end fullstack a Azure desde un repositorio de código.

## 1. Requisitos Previos

Antes de comenzar, asegúrate de tener lo siguiente:

* Una cuenta de Azure activa (se recomienda Azure for Students).
* El código fuente de la aplicación PokeDex alojado en un repositorio de GitHub.
* Azure CLI instalado y configurado en tu máquina local (opcional, pero recomendado para algunos pasos).

## 2. Crear el Recurso de Azure Static Web App

Puedes crear el recurso de Azure Static Web App usando el Azure Portal o la Azure CLI.

###   2.1. Usando el Azure Portal

1.  **Inicia sesión en Azure Portal:**
    * Ve al [Azure Portal](https://portal.azure.com/) e inicia sesión con tus credenciales de Azure.
2.  **Crea un nuevo recurso:**
    * Haz clic en "Crear un recurso" en la página de inicio.
    * Busca "Static Web Apps" y selecciona "Static Web Apps".
    * Haz clic en "Crear".
3.  **Configura los detalles básicos:**
    * Selecciona la suscripción y el grupo de recursos donde deseas crear la aplicación web estática.
    * Ingresa un nombre para tu aplicación web estática.
    * Selecciona la región más cercana a tus usuarios.
4.  **Conecta a GitHub:**
    * Inicia sesión en GitHub y autoriza a Azure para acceder a tu repositorio.
    * Selecciona el repositorio y la rama que contiene el código fuente de la aplicación PokeDex.
5.  **Configura la compilación (Build Details):**
    * Azure Static Web Apps necesita saber cómo construir tu aplicación. Configura la "Ubicación de la aplicación" (generalmente "/"), la "Ubicación de la API" (si tienes una API, sino déjalo en blanco), y la "Ubicación del artefacto estático" (donde se guardan los archivos construidos, como "dist" o "build"). Esto depende de tu framework de desarrollo.
6.  **Revisar y crear:**
    * Revisa todos los detalles y haz clic en "Revisar + crear" para crear el recurso de Azure Static Web App.
    * Haz clic en "Crear" para iniciar el proceso de creación y despliegue.
## 3. Proceso de Despliegue

* Azure Static Web Apps configurará un flujo de trabajo de GitHub Actions en tu repositorio.
* Cada vez que realices un push a la rama especificada, GitHub Actions construirá y desplegará automáticamente tu aplicación en Azure.
* Puedes encontrar la URL de tu aplicación en la sección "Información general" de tu recurso de Static Web App en el Azure Portal.

## 4. Configuración Adicional (Opcional)

* **Dominios personalizados:** Puedes configurar un dominio personalizado para tu aplicación web estática.
* **Certificados SSL:** Azure Static Web Apps proporciona automáticamente certificados SSL gratuitos.
* **Autenticación/Autorización:** Puedes configurar la autenticación y autorización para restringir el acceso a tu aplicación.
* **Variables de entorno:** Si tu aplicación necesita variables de entorno, puedes configurarlas en la sección "Configuración" de tu recurso de Static Web App.

## 5. Notas Importantes

* Asegúrate de que la configuración de la compilación en Azure Static Web Apps coincida con la estructura de tu proyecto.
* Revisa los registros de GitHub Actions para solucionar cualquier problema de compilación o despliegue

Este documento proporciona una guía general para desplegar una aplicación en Azure Static Web Apps. Los detalles específicos pueden variar según la aplicación.
