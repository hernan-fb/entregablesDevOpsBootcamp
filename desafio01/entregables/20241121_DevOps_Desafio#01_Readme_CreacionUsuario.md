### README - Creación de Usuarios

# Creación de Usuarios

Este pipeline de Jenkins permite la creación de usuarios en el sistema de manera sencilla y controlada. A continuación, se describe cómo utilizar este job y los parámetros requeridos.

## Funcionamiento del Pipeline

1. **Parámetros de Entrada**:
   - **`login`**: Identificador único para el usuario (opcional). Si no se proporciona, se genera automáticamente a partir del nombre y apellido.
   - **`Nombre`**: Nombre del usuario a crear (requerido).
   - **`Apellido`**: Apellido del usuario a crear (requerido).
   - **`Departamento`**: Área de trabajo del usuario (requerido). Las opciones disponibles son: 'Contabilidad', 'Finanzas', 'Tecnología'.

2. **Procesamiento**:
   - Se valida que `Nombre`, `Apellido` y `Departamento` no estén vacíos.
   - Se genera un login a partir del nombre y apellido y se convierte a minúsculas. Si se ha ingresado el parámetro login, también se convierte a minúsculas.
   - Se verifica si el usuario existe en el sistema a través de la búsqueda en `/etc/passwd`. Si existe el usuario que se va a crear, se arroja un error.
   - Se crea una contraseña inicial basada en el formato `nombre-apellido@empresa_año`.

3. **Creación de Usuario**:
   - Se ejecuta el comando `useradd` para crear el usuario, y se establece una contraseña temporal que deberá ser cambiada en el primer inicio de sesión.

## Cómo Utilizar el Job

1. Accede al job de Creación de Usuarios en Jenkins.
1. Rellena los parámetros obligatorios:
   - Especifica el `Nombre`, `Apellido`, y selecciona un `Departamento`.
   - Opcionalmente, puedes ingresar un `login` único.
1. Ejecuta el job.
1. Al finalizar, recibirás un mensaje confirmando la creación del usuario y la contraseña inicial.

### Contacto
Si encuentras problemas o tienes preguntas sobre el uso de este pipeline, no dudes en contactar al administrador del sistema.