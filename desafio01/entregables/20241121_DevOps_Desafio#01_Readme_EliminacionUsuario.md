### README - Eliminación de Usuarios

# Eliminación de Usuarios

Este pipeline de Jenkins permite eliminar usuarios del sistema de manera segura y controlada. A continuación, se describe cómo utilizar este job y los parámetros requeridos.

## Funcionamiento del Pipeline

1. **Parámetros de Entrada**:
   - **`username`**: Nombre del usuario que se desea eliminar (requerido).

2. **Procesamiento**:
   - Se valida que el `username` no esté vacío.
   - Se verifica si el usuario existe en el sistema a través de la búsqueda en `/etc/passwd`.

3. **Eliminación de Usuario**:
   - Si el usuario existe, se ejecuta el comando `userdel` para eliminar el usuario y su directorio home.
   - Se eliminará también el grupo correspondiente asociado al usuario mediante `groupdel`.

## Cómo Utilizar el Job

1. Accede al job de Eliminación de Usuarios en Jenkins.
2. Ingresa el `username` del usuario que deseas eliminar.
3. Ejecuta el job.
4. Recibirás un mensaje confirmando la eliminación del usuario y del grupo correspondiente.

### Contacto
Si encuentras problemas o tienes preguntas sobre el uso de este pipeline, no dudes en contactar al administrador del sistema.