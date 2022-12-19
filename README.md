# AuthTicketService 🔐

El presente proytecto es un **Microservicio** desarrollado en el lenguaje de programacion C#, que provee una **API** para gestionar **autenticación de usuarios** de un sistema

Para manejar la seguridad de la informacion, el mismo utiliza el cirfrado de los datos mediante **Hash** y **JWT** como Token de acceso

El actual microservicio en conjunto con [TicketService](https://github.com/diloretoignacio/TicketService) son consumidos por la aplicacion web [TicketsFrontend](https://github.com/diloretoignacio/TicketsFrontend)

A continuacion se demuestran los principales endpoints para realizar acciones sobre la informacion:
## Crear Usuario
### Request
```
POST /api/Users
```
### Body
```
{
  "userName": "diloretoignacio",
  "firstName": "Ignacio",
  "lastName": "Di Loreto",
  "phone": "1561990876",
  "dni": "32845146",
  "email": "diloretoignacio@gmail.com",
  "rolId": 1
}
```

## Loguearse
```
POST /api/Users/login/
```
### Body
```
{
  "userName": "diloretoignacio",
  "password": "pass"  
}
```
### Response
Si las credenciales son correctas se devuelve un Token, el cual debera ser utilizado en cada solicitud, para dee sta forma lograr identificar al usuario que la realiza


Ademas se permite:

* Obtener un usuario por ID
* Crear un rol
* Crear un permiso
* Editar usuario, rol y/o permiso

Todos los endpoints correspondientes se encuentran en el archivo **Collección Postman AuthService.json** que contiene la coleccion de Postman utilizada

