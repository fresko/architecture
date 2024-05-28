# Arquitectura Aereolinia

El sistema debe gestionar reservas de vuelos, realizar cambios
y cancelaciones, gestionar asientos y proporcionar información en tiempo real sobre vuelos y precios.

##Modulos
 -Resgitro Usuarios 
 -Gestion de Reservas
 -Gestion Asientos
 -Canales de Pagos
 -Sitemas externos (Estado de aeropuertos / Imigración)

 ##Arquitectura

<img src="/Aerolinea.drawio.png" alt="image"  height="600px">

Arquitedctura con estilo de microservicios  para este casos de uso que requieren escalamiento dinámico, según la cantidad de demanda del cliente, sin incurrir en contrapresión ni problemas de cuellos de botella en el rendimiento.

## Responsabilidades

- Componenete de Gestion de reserva  con patrones de arquitectura de APIs como API gateway para separar responsabilidades  con son los apis de reservas y asientos  
- Se separa el componete de consultar precios debido a su complejidad y consulta a sistemas externo 
- Se separa los sistemas externos de pago , imigracion y estados de areopuesrtos (se diseñara arquitectura posterio debidona su importacia y despliegue)

 ##Infraestuctura de solucion  
 Se utilizan componetes de de OCI y nube externa  , componentesde de esaclamiento como Kubernetes y los servicios de API,

<img src="/infraestructura.drawio.png" alt="image"  height="600px">

##Componentes

- Autenticación : Se utiliza IAM para gestion de usuarios y sus diferentes roles con Auth2 y otros
- Base de Datos Autonomo : utilizada para seprar responsabilidades y rendimiento de las transaciones y utlizzacion de cache
- COntenedores
- Servicios de integracion para sistemas externos
- Colas 
- Región
Una región OCI es un área geográfica localizada que contiene uno o más centros de datos, llamados dominios de disponibilidad. Las regiones son independientes de otras regiones y grandes distancias pueden separarlas (entre países o incluso continentes).

-Dominios de disponibilidad
Los dominios de disponibilidad son centros de datos independientes dentro de una región. Los recursos físicos de cada dominio de disponibilidad están aislados de los recursos de los otros dominios de disponibilidad, lo que proporciona tolerancia a fallos. Los dominios de disponibilidad no comparten servicios de infraestructura como energía, refrigeración o la red interna del dominio de disponibilidad. Por lo tanto, es poco probable que un error en un dominio de disponibilidad afecte a los demás dominios de disponibilidad de la región.

 
    
    
## Topics  

