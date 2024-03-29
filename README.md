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
   
2. En el panel de servicios, selecciona **S3** bajo la categoría **Almacenamiento**.

3. En el panel de S3, haz clic en **Crear bucket** para iniciar el proceso de creación de un nuevo bucket.

4. Ingresa un nombre único para tu bucket. Ten en cuenta que los nombres de los buckets en S3 deben ser únicos en toda la plataforma de AWS.

5. Selecciona la región en la que deseas crear tu bucket. 

<p align="center">
  <img src="https://github.com/jonma0107/aws-react-site/assets/53632260/2c0f1f3a-8a82-43f0-9bf7-540bf33178b5" width="500px">
</p>

6. Puedes configurar las opciones de configuración de permisos según tus necesidades. Si deseas que tu bucket sea accesible públicamente, asegúrate de establecer las políticas de acceso adecuadas. De lo contrario, configura las políticas de acceso según tus requisitos de seguridad. Por lo general los buckets están configurados para que no cualquier usuario pueda acceder a los elementos que allí se guardan, está bloqueado el acceso público, pero como necesitamos que a nuestro sitio web estático accedan a ver los elementos desde el navegador de internet porque en este caso estamos sirviendo una página web, para ello desmarcamos la casilla como se muestra en la imagen:

<p align="center">
  <img src="https://github.com/jonma0107/aws-react-site/assets/53632260/8aa5eca3-c570-453b-b335-818b11f4592e" width="500px">
  <img src="https://github.com/jonma0107/aws-react-site/assets/53632260/475dfa0e-e0e7-4bf2-bcb5-e9adb410d6c8" width="500px">
</p>


7. Finalmente no cambiamos nada más en esta sección y hacemos clic en **Crear bucket** para finalizar la creación del bucket y listo tenemos nuestro bucket creado en este caso se llama **react-first-site**.

<p align="center">
  <img src="https://github.com/jonma0107/aws-react-site/assets/53632260/280b06b4-d2a7-4405-99bd-9ac12cab7b30" width="650px">
</p>

Ahora que tu bucket está creado, puedes seleccionarlo en el panel de S3 y comenzar a cargar tus archivos. Haz clic en **Cargar** para agregar archivos a tu bucket. Pero cargaremos los archivos estáticos de otra manera.

# Generar la URL que se utilizará para acceder a la aplicación

1. Obtén la URL de tu bucket S3 seleccinando el nombre del bucket creado y accediendo en el para encontrarse con el tablero de opciones del cual elegimos  la pestaña **Propiedades**.

![image](https://github.com/jonma0107/aws-react-site/assets/53632260/975085cc-cb8d-48e8-ab5a-26e2284c4175)

2. Dentro de la pestaña **Propiedades** se desplaza hacia abajo hasta llegar a una sección llamada **Sitio web estático**.

![image](https://github.com/jonma0107/aws-react-site/assets/53632260/a9d7358b-85ee-4f60-9792-a320c1dfd38d)

3. Luego, haz clic en el botón **Editar** para habilitar la funcionalidad del sitio web estático. Una vez dentro de la ventana de edición configuramos la habilitación de la funcionalidad como se muestra en la siguiente imagen y se guardan cambios:

![image](https://github.com/jonma0107/aws-react-site/assets/53632260/43e44469-56df-4d11-9a0a-a82480d00ea1)

![image](https://github.com/jonma0107/aws-react-site/assets/53632260/bb6a9761-ce6d-44d3-b3bf-0a8bf6bfd26b)

# Configuración de Permisos para el Bucket en AWS S3

Para darle permisos específicos a tu bucket en Amazon S3, puedes seguir estos pasos:

1. Accede a la consola de AWS y navega hasta el servicio **S3**.

2. Selecciona el bucket al que deseas agregar permisos.

3. Ve a la pestaña **Permisos** y selecciona la opción **Política de bucket**.

![image](https://github.com/jonma0107/aws-react-site/assets/53632260/438c8eaa-58fd-4e10-85d4-201509f912ca)

![image](https://github.com/jonma0107/aws-react-site/assets/53632260/41d47e59-23f9-401c-8c63-bbdd690ee12b)

4. Haz clic en **Editar** para modificar la política del bucket.

5. Copia y pega la siguiente política como ejemplo, ajustando los valores según tus necesidades:

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "Statement1",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::nombre-de-tu-bucket/*"
        }
    ]
}
```

![image](https://github.com/jonma0107/aws-react-site/assets/53632260/baf001ed-c7e5-47ff-9fbf-e68c1aeb3ca3)


6. Dentro de la ventana de las políticas del bucket, es muy importante añadir un nuevo recurso (Resource), haz clic en Add a resource. 

![image](https://github.com/jonma0107/aws-react-site/assets/53632260/180568d1-61e2-4b09-9bc4-a53b4d5102eb)

7. Proporciona la URL del recurso o el ARN del recurso al que deseas otorgar permisos y configura según como se muestra en la imagen

![image](https://github.com/jonma0107/aws-react-site/assets/53632260/12a582a2-8271-49b8-b17e-60dd45a63a06)

8. Guarda los cambios realizados en la política del bucket. Al guardar los cambios aparece la regla de la politica del bucket creada. 

![image](https://github.com/jonma0107/aws-react-site/assets/53632260/64ffb7df-0e91-4ede-a831-4ac61e018bfe)

# Instalación y Uso de AWS CLI para Subir Archivos Estáticos a AWS S3

A continuación, se presentan los pasos para instalar y configurar AWS CLI según las [instrucciones oficiales de AWS](https://docs.aws.amazon.com/es_es/cli/latest/userguide/getting-started-install.html):

## Instalación de AWS CLI:

1. Abre tu terminal.

2. Sigue las instrucciones proporcionadas en la [página oficial de instalación de AWS CLI](https://docs.aws.amazon.com/es_es/cli/latest/userguide/install-cliv2.html) para tu sistema operativo específico.

3. Verifica la instalación ejecutando el siguiente comando:

   ```bash
   aws --version
   ```
   
## Configuración de AWS CLI con tus Credenciales:

Después de la instalación, ejecuta el siguiente comando y sigue las instrucciones para configurar tus credenciales de AWS:

```bash
aws configure
```

Ingresa la siguiente información cuando se te solicite:

- Access Key ID: Tu Access Key ID proporcionada por AWS.
- Secret Access Key: Tu Secret Access Key proporcionada por AWS.
- Región predeterminada: La región que deseas utilizar (p. ej., us-east-1).
- Formato de salida preferido: El formato de salida preferido, como json.
- Asegúrate de ingresar la información correcta para establecer la configuración de AWS CLI de manera adecuada.

## Acceso a Access Key ID y Secret Access Key en AWS S3 mediante IAM

Para obtener tu Access Key ID y Secret Access Key en AWS S3, sigue estos pasos:

1. Inicia sesión en la [Consola de AWS](https://aws.amazon.com/console/).

2. Navega al servicio **IAM (Identidad y Acceso de AWS)**.

3. En el panel izquierdo, haz clic en **Usuarios** y selecciona **Agregar usuario**.

4. Ingresa un nombre de usuario y configura sla creación del usuario como se muestra en la siguiente imagen.

![image](https://github.com/jonma0107/aws-react-site/assets/53632260/3e2b9023-dde8-417b-86e1-64848df23880)

5. Revisa la configuración y haz clic en **Crear usuario**.

![image](https://github.com/jonma0107/aws-react-site/assets/53632260/77f8055b-233e-46fa-a9c3-62ab9fa9f789)

6. Una vez creado el usuario, en la página de confirmación, accedemos a ese usuario y nos desplazamos hasta la pestaña llamada **Credenciales de Seguridad**.

![image](https://github.com/jonma0107/aws-react-site/assets/53632260/9f81ab58-0580-4fde-8feb-c528a2c3d6c9)

7. Dentro de la pestaña **Credenciales de Seguridad** hacer scroll hacia abajo hasta la sección **Claves de Acceso** y dar click en el cotón **Crear Clave de Acceso**

![image](https://github.com/jonma0107/aws-react-site/assets/53632260/db408754-ea97-4afa-8cc9-dd30c645b3d9)

8. Dentro de **Crear Clave de Acceso** configurar la creación de la clave como se muestra en la siguiente imagen

![image](https://github.com/jonma0107/aws-react-site/assets/53632260/c2506267-b902-48ab-88f2-0f9ade235f2e)

9. Al dar **Siguiente** nos lleva a la siguiente ventana en la cuál solo daremos click en el botón **Crear Clave de Acceso**

![image](https://github.com/jonma0107/aws-react-site/assets/53632260/7c299ed5-82d4-4db0-b6ef-c7a5856dbabc) 

10. Al crear la clave de acceso  podrás ver el **Access Key ID** y el **Secret Access Key**

![image](https://github.com/jonma0107/aws-react-site/assets/53632260/f61b58e3-2ef0-4ce7-954f-5fdbcfb2b2a6)

La información de las llaves de acceso, una vez obtenida, se agrega a la configuración de AWS CLI:

![image](https://github.com/jonma0107/aws-react-site/assets/53632260/bdb56279-f0be-4cae-9254-bcd667db0f97) 

**¡Importante!** Guarda estas credenciales de manera segura. Son necesarias para autenticar el acceso a tus recursos de AWS.

Recuerda que estas claves son sensibles y deben ser manejadas con cuidado para garantizar la seguridad de tu cuenta de AWS.

# Creación de Grupo y Asociación de Usuario en IAM

Para crear un grupo y asociar un usuario en IAM en AWS, sigue estos pasos:

Un grupo es una especie de reglas que están agrupadas, y que se pueden reutilizar esas reglas a varios usuarios.

1. Inicia sesión en la [Consola de AWS](https://aws.amazon.com/console/).

2. Navega al servicio **IAM (Identidad y Acceso de AWS)**.

3. En el panel izquierdo, haz clic en **Grupos de Usuarios** y selecciona **Crear grupo**.

![image](https://github.com/jonma0107/aws-react-site/assets/53632260/5001cb4f-b79e-4f46-8628-b1a4bc792d53)

4. Ingresa un nombre para el grupo y desplazate hasta ls siguiente sección **Adjuntar políticas de permisos**.

![image](https://github.com/jonma0107/aws-react-site/assets/53632260/a6cb0714-4bea-469f-b70f-18058b98b207)

5. Una vez en la sección de **Adjuntar políticas de permisos** marcamos las reglas de **AmazonS3FullAccess** y **AmazonS3ReadOnlyAccess** como se muestra en la imagen

![image](https://github.com/jonma0107/aws-react-site/assets/53632260/1392c6dc-fe94-44cf-bd0b-b1defda20512)

5. Una vez marcadas las reglas anteriormente mencionadas, hace scroll hacia abajo, y haz clic en **Crear grupo**.

6. Una vez creado el grupo, selecciona el grupo recién creado.

7. En la pestaña **Usuarios**, haz clic en **Agregar usuarios**.

8. Selecciona el usuario que creaste anteriormente y haz clic en **Agregar usuarios**.

![image](https://github.com/jonma0107/aws-react-site/assets/53632260/45c7c90f-2c73-4edf-9a06-1f9a9b2d9789)

Ahora, tu usuario está asociado al grupo que acabas de crear. Los permisos que asignes al grupo se aplicarán automáticamente al usuario asociado.

Ten en cuenta que los grupos en IAM te permiten asignar permisos de manera centralizada a varios usuarios, facilitando la gestión de permisos en entornos con múltiples usuarios. ¡Listo! Ahora tu usuario forma parte del grupo con los permisos necesarios.

# Subir Archivos Estáticos a AWS S3 con AWS CLI

Asegúrate de haber instalado y configurado AWS CLI según los pasos anteriores.

## Subir Archivos Estáticos:

1. Abre tu terminal.

2. Navega al directorio donde se encuentran tus archivos estáticos.

3. Ejecuta el siguiente comando para subir un archivo específico a tu bucket S3:

   ```bash
   aws s3 sync dist/ s3://react-first-site
   ```
<p align="center">
  <img src="https://github.com/jonma0107/aws-react-site/assets/53632260/632acf08-9286-4e28-8ac2-4bd3872a6d3e" width="800px">
</p>

Listo! Con estos pasos, tus archivos estáticos estarán disponibles en tu bucket S3. Puedes acceder a ellos a través de la URL proporcionada por AWS S3. Todo esto es simplemente para una aplicación de frontend que no necesita conectarse a un backend. Próximamente subiré un proyecto en dónde haya una integración de los tres módulos: Frontend, Backend y DataBase.

<p align="center">
  <img src="https://github.com/jonma0107/aws-react-site/assets/53632260/a5f28aea-d5fc-464d-bb19-f4b87bef534c" width="800px">
</p>











   
 















