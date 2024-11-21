#### ID:
	Cargar mueble

#### Titulo:
	`Como encargado quiero cargar un mueble para que los usuarios lo puedan alquilar.`

#### Reglas de negocio:
	`- No pueden existir codigos de muebles repetidos`
	`- El encargado debe estar autenticado`

#### Criterios de aceptacion:

##### Escenario 1: Carga exitosa.
>**Dado** el codigo de inventario '213' que no se encuentra cargado en el sistema y el encargado se encuentra autenticado
>**Cuando** el encargado ingresa los datos:
> - Codigo: 213
> - Tipo de mueble: Silla
> - Fecha de creacion: 23/04/2025
> - Fecha de ultimo mantenimiento: 20/04/2025
> - Estado: libre
> - Precio: 20USD
> Y presiona "Cargar mueble"
>**Entonces** el sistema almacena los datos del mueble y muestra un mensaje de exito.

##### Escenario 2: Carga fallida por codigo de inventario ya existente.
>**Dado** el codigo de inventario "77" el cual ya se encuentra cargado en el sistema y el encargado se encuentra autenticado
>**Cuando** el encargado ingresa los datos:
> - Codigo: 77
> - Tipo de mueble: Mesa
> - Fecha de creacion: 23/04/2025
> - Fecha de ultimo mantenimiento: 20/04/2025
> - Estado: libre
> - Precio: 20USD
> Y presiona "Cargar mueble"
>**Entonces** el sistema informa que la operacion es cancelada porque el codigo de inventario ya se encuentra cargado y *no* almacena el mueble en el sistema

##### Escenario 3: Carga fallida por encargado no autenticado.
>**Dado** el codigo de inventario "13" el cual no se encuentra cargado en el sistema y el encargado no se encuentra autenticado
>**Cuando** el encargado ingresa los datos:
> - Codigo: 13
> - Tipo de mueble: Mesa
> - Fecha de creación: 11/02/2025
> - Fecha de último mantenimiento: 3/04/2024
> - Estado: libre
> - Precio: 27USD
> Y presiona "Cargar mueble"
>**Entonces** el sistema solicita la autenticación