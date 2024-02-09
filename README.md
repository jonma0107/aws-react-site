# Aplicación React desplegada en AWS con S3

Este proyecto es una aplicación introductoria y muy simple elaborada con [Vite](https://vitejs.dev/), un servidor de desarrollo local, para crear una plantilla básica de [React](https://es.reactjs.org/). La finalidad de esta plantilla es proporcionar un proyecto de ejemplo que pueda ser desplegado en [AWS](https://aws.amazon.com/) mediante el servicio [S3](https://aws.amazon.com/s3/).

## Requisitos Previos

Este proyecto requiere algunas instalaciones previas. Asegúrate de tener Node.js, npm y Vite instalados en tu entorno de desarrollo.

# Creación del Proyecto con Vite

Para crear el proyecto con Vite, ejecuta el siguiente comando npm:

```bash
npm create vite
```
Este comando te llevará a través del proceso de configuración de tu proyecto. Al ejecutarlo, Vite presentará algunas opciones. Selecciona la plantilla para React y JavaScript. Luego, simplemente presiona "Enter" para continuar.

<p align="center">
  <img src="https://github.com/jonma0107/aws-react-site/assets/53632260/95d1a612-ca4d-4dc4-94a4-8cdb624cf26b" width="400px">
  <img src="https://github.com/jonma0107/aws-react-site/assets/53632260/355a2cf4-6623-4a93-a1d8-6a9dd3d4398f" width="517px">
</p>

Una vez que hayas creado el proyecto Vite, dirígete a la carpeta del proyecto en tu terminal y ejecuta el siguiente comando para instalar las dependencias:

```bash
npm i
```

# Generar Archivo index.html con el Comando 'npm run build'

Después de configurar tu proyecto React con Vite, puedes generar el archivo `index.html` y otros archivos estáticos en la carpeta `dist` utilizando el siguiente comando:

```bash
npm run build
```

Luego, para ver tu aplicación de forma local, ejecuta el siguiente comando:

```bash
npm run dev
```

Esto iniciará el servidor de desarrollo local y podrás acceder a tu aplicación en [__http://localhost:5173__](http://localhost:5173).

# Introducción a Amazon S3

Amazon S3, o Amazon Simple Storage Service, es un servicio de almacenamiento en la nube proporcionado por Amazon Web Services (AWS). Este servicio permite almacenar y recuperar datos de manera escalable y segura a través de internet. S3 es altamente utilizado para alojar archivos estáticos, almacenar copias de seguridad, distribuir contenido web y como un repositorio de datos para aplicaciones.

# Proceso de AWS - Configuración en la Consola de AWS para S3

Antes de comenzar con la configuración en la consola de AWS para AWS S3, asegúrate de tener una cuenta de AWS con privilegios de root y en la capa gratuita. Si aún no tienes una cuenta, puedes registrarte [aquí](https://aws.amazon.com/es/free/) y obtener más información .

### Consejo para Registrarse con Tarjeta Débito:

Para aquellos que desean registrarse con una tarjeta de débito, se puede utilizar el número de tarjeta de débito de Nequi u otras tarjetas que cumplan con los requisitos de AWS.

# Pasos para Configurar AWS S3:

1. Accede a la [Consola de AWS](https://aws.amazon.com/console/).
   
3. En el panel de servicios, selecciona **S3** bajo la categoría **Almacenamiento**.

4. En el panel de S3, haz clic en **Crear bucket** para iniciar el proceso de creación de un nuevo bucket.

3. Ingresa un nombre único para tu bucket. Ten en cuenta que los nombres de los buckets en S3 deben ser únicos en toda la plataforma de AWS.

5. Selecciona la región en la que deseas crear tu bucket. Esto puede estar en la esquina superior derecha de la consola.

6. Haz clic en **Siguiente** hasta llegar a la sección de configuración de permisos.

7. Puedes configurar las opciones de configuración de permisos según tus necesidades. Si deseas que tu bucket sea accesible públicamente, asegúrate de establecer las políticas de acceso adecuadas. De lo contrario, configura las políticas de acceso según tus requisitos de seguridad.

8. Haz clic en **Siguiente** hasta llegar a la sección de revisión.

9. Revisa la configuración y haz clic en **Crear bucket** para finalizar la creación del bucket.

10. Ahora que tu bucket está creado, puedes seleccionarlo en el panel de S3 y comenzar a cargar tus archivos. Haz clic en **Cargar** para agregar archivos a tu bucket.









