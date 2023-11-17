# API de Registro de Personas
## Ruta General del Proyecto

localhost:9090/v1/


## Endpoint: /persona

### 1. Obtener todas las personas

- **Método:** GET
- **Ruta:** `/persona/all`
- **Descripción:** Obtiene la lista de todas las personas registradas.
- **Restricciones:**
  1. El usuario debe estar autenticado.
  2. Solo los administradores tienen acceso.
- **Códigos de Estado:**
  - 200 OK: Éxito.
  - 401 Unauthorized: No autorizado.
  - 403 Forbidden: Acceso prohibido.

### 2. Registrar una nueva persona

- **Método:** POST
- **Ruta:** `/persona/save`
- **Descripción:** Registra una nueva persona en el sistema.
- **Restricciones:**
  1. Todos los campos obligatorios deben estar presentes.
  2. El correo electrónico debe tener un formato válido.
- **Códigos de Estado:**
  - 201 Created: Persona creada con éxito.
  - 400 Bad Request: Parámetros de entrada incorrectos.
  - 422 Unprocessable Entity: Error de validación.

### 3. Actualizar información de una persona

- **Método:** PUT
- **Ruta:** `/persona/update/{id}`
- **Descripción:** Actualiza la información de una persona existente por su ID.
- **Restricciones:**
  1. El ID de la persona debe ser válido.
  2. El usuario que realiza la actualización debe ser el propietario o un administrador.
- **Códigos de Estado:**
  - 200 OK: Actualización exitosa.
  - 401 Unauthorized: No autorizado.
  - 403 Forbidden: Acceso prohibido.
  - 404 Not Found: Persona no encontrada.

### 4. Obtener información de una persona por ID

- **Método:** GET
- **Ruta:** `/persona/findById/{id}`
- **Descripción:** Obtiene la información de una persona por su ID.
- **Restricciones:**
  1. El ID de la persona debe ser válido.
  2. La información solo es accesible para usuarios autenticados.
- **Códigos de Estado:**
  - 200 OK: Éxito.
  - 401 Unauthorized: No autorizado.
  - 404 Not Found: Persona no encontrada.

### 5. Eliminar una persona

- **Método:** DELETE
- **Ruta:** `/persona/delete/{id}`
- **Descripción:** Elimina una persona por su ID.
- **Restricciones:**
  1. Solo los administradores pueden realizar esta acción.
  2. El ID de la persona debe ser válido.
- **Códigos de Estado:**
  - 204 No Content: Eliminación exitosa.
  - 401 Unauthorized: No autorizado.
  - 403 Forbidden: Acceso prohibido.
  - 404 Not Found: Persona no encontrada.

