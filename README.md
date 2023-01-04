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
```
{
    "userId": 5,
    "userName": "diloretoignacio",
    "firstName": "Ignacio",
    "lastName": "Di Loreto",
    "email": "diloretoignacio@gmail.com",
    "activeUser": true,
    "rol": {
        "rolId": 3,
        "title": "Agente",
        "description": "Perfil de Agente, permite tomar, derivar y/o resolver un ticket",
        "permissions": [
            {
                "permissionId": 2,
                "title": "AM Tickets",
                "description": "Permiso que otorga la posibilidad de crear y/o editar tickets"
            },
            {
                "permissionId": 3,
                "title": "Resolucion Tickets",
                "description": "Permiso que otorga la posibilidad de tomar, resolver y/o derivar tickets"
            }
        ]
    },
    "areaId": 3,
    "token": "eyJhbGciOiJIUzUxMiIsInR5cCI6IkpXVCJ9.eyJuYW1laWQiOiI1IiwidW5pcXVlX25hbWUiOiJjYW5kZWxhZ2FicmllbGUiLCJlbWFpbCI6ImNhbmRlbGFnYWJyaWVsZUBvdXRsb29rLmNvbSIsInJvbGUiOiIzIiwiZ2VuZGVyIjoiMiwzIiwiYWN0b3J0IjoiMyIsIm5iZiI6MTY3Mjg1ODE2NSwiZXhwIjoxNjczNDYyOTY1LCJpYXQiOjE2NzI4NTgxNjV9.FRvCTUWEFXclRd78_rGSn3co13rf7gc9vASP0lHVv5rqFG40WFNNZGILGPNnuNUYaFmS3SGrGEpeD1PTLm8swQ"
}
```

Ademas se permite:

* Obtener un usuario por ID
* Crear un rol
* Crear un permiso
* Editar usuario, rol y/o permiso
* Obtener rol y/o permiso

Todos los endpoints correspondientes se encuentran en el archivo **Collección Postman AuthService.json** que contiene la coleccion de Postman utilizada

