Documentación API
Endpoints
Autenticación
POST /api/Autenticacion/Validar - Genera un token JWT para autorizar el acceso a los endpoints protegidos.

Requiere en el body:
json

Copy code

{
 "correo": "c@gmail.com",
 "clave": "123" 
}
Productos
GET /api/Producto/Lista - Obtiene el listado de todos los productos (requiere autenticación)

GET /api/Producto/Obtener/{idProducto} - Obtiene los datos de un producto por ID (requiere autenticación)

POST /api/Producto/Guardar - Crea un nuevo producto (requiere autenticación)

Requiere en el body un objeto Producto con los datos a guardar
PUT /api/Producto/Editar - Actualiza los datos de un producto existente (requiere autenticación)

Requiere en el body un objeto Producto con los datos a actualizar
DELETE /api/Producto/Eliminar/{idProducto} - Elimina un producto por ID (requiere autenticación)

Pronóstico del tiempo
GET /WeatherForecast - Obtiene una lista de pronósticos (no requiere autenticación)
Requisitos de autenticación
Los endpoints marcados como "requiere autenticación" deben enviar en el header Authorization el token JWT retornado por el endpoint de /Autenticacion/Validar.

Ejemplo:

Copy code

Authorization: Bearer <token>
El token tiene una duración de 5 minutos. Una vez vencido, se debe solicitar uno nuevo.