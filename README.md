# Culqi Integration - Wordpress Plugin

Bienvenido al respositorio de Culqi Integración para Wordpress. Este plugin te permite sincronizar tus pagos con Culqi y activar la pasarela de pagos para Woocommerce y capturar pagos si lo requieres.


## Requisitos ##

- Version PHP mínimo requerido es 5.6
- [Credenciales de Culqi](https://www.culqi.com)


## Instalación desde el repositorio de WP ##

Podes descargar el plugin desde el repositorio de Wordpress :
[https://wordpress.org/plugins/culqi-full-integration/](https://wordpress.org/plugins/culqi-full-integration/)


O podes instalarlo desde el mismo Wordpress. Ir a Plugins > Agregar nuevo

![Alt text](https://www.letsgodev.com/wp-content/uploads/2015/08/install_plugin1.png "Add New Plugin")

Buscar "Culqi", instalar y activar

![Alt text](https://www.letsgodev.com/wp-content/uploads/2015/07/plugin.jpg "Add New Plugin")


## Instalación desde Github ##

**1. Clonar Repositorio**
```git clone git@github.com:gonzalesc/wp-culqi-integration.git```

**2. Descargar Biblioteca Culqi**
```composer update```


## Credenciales de Culqi ##

Debes registrarte en [https://www.culqi.com](https://www.culqi.com) y luego accedes al panel de integración. Una vez ahi, irás a Desarrollo > ApiKey y así obtendrás tus credenciales:

![Alt text](https://www.letsgodev.com/wp-content/uploads/2019/04/apikey.png "Credenciales Culqi")

## Página de Bienvenida ##

Cuando actives el plugin, éste te redireccionará a una página de bienvenida donde deberás poner tus credenciales de Culqi y otras cosas más.

![Alt text](https://www.letsgodev.com/wp-content/uploads/2015/07/welcome.jpg "Welcome Page")


## Página de Configuración ##

Una vez llenado todo correctamente, al presionar "Guardar", éste le enviará a la página de configuración del plugin y empezará a sincronizar los pagos automáticamente.

![Alt text](https://www.letsgodev.com/wp-content/uploads/2015/07/settings.jpg "Configure you Settings page")


## Pasarela Culqi para Woocommerce ##

Si activaste el método de pago, debes ir a configurarlo.

![Alt text](https://www.letsgodev.com/wp-content/uploads/2015/07/woo2.jpg "Woocommerce Payment")


## Log de transacciones ##

El log siempre está habilitado, cada pedido tendrá un detalle de todos los pasos que sigue Culqi para hacer el pago. Aqui también se registrará los errores si los hay.

![Alt text](https://www.letsgodev.com/wp-content/uploads/2015/07/log.jpg "Log")


## Datos recomendados en el Checkout ##

Culqi recomienda que estos campos sean obligatorios:

- Email
- Nombre
- Apellido
- Dirección
- Ciudad
- Código de pais ( ejem: para Perú es PE)
- Teléfono

De todos estos puntos el más importante es el `email`, los otros campos son muy necesarios para un tema de antifraude pero no son obligatorios. Yo recomiendo que tengas todos estos campos en tu checkout. El plugin no validará estos campos.

## Multipagos - Configurar Evento ##

Puedes habilitar Multipagos en la sección de configuración de la pasarela de pago Culqi. Cada vez que se genera una orden de pago, le llegará al cliente un email con el CIP de pago.

![Alt text](https://www.letsgodev.com/wp-content/uploads/2015/07/webhook_settings.jpg "Multipagos")


Cuando el cliente page su código CIP, Culqi avisará al comercio mediante un `evento` el cual debemos configurar: para ello, debemos entrar al panel de Culqi e ir a la sección de `eventos` y al submenu de `webhooks`. Finalmente le damos click al botón `Añadir` que está arriba a la derecha.

![Alt text](https://www.letsgodev.com/wp-content/uploads/2015/07/webhook_create.jpg "Event")


Debes elegir el evento : `order.status.changed`
y la URL que debes poner está en la configuración de la pasarela de pago Culqi para Woocommerce: `URL del Webhook`


## Problemas Comunes desde el servicio de Culqi ##

El servicio de Culqi suele ser óptimo cuando se trata de registrar pagos simples pero, raras veces, cuando empiezas a interactuar con otros servicios puede traernos estos tipos de problemas, si sueles tener alguno, comunicate con ellos.

- `Ups! Algo salió mal en Culqi. Contáctate con soporte@culqi.com para obtener mas información` - *El servicio de Culqi, para el servicio solicitado, no está disponible en ese momento*

- `Endpoint request timed out` - *El endpoint del API de Culqi a agotado su tiempo de solicitud*


**Para hacer una verificación del servicio de Culqi, [te invito a seguir esta guía simple y sencilla](https://blog.letsgodev.com/tips-es/verificar-servicio-de-culqi-en-10-minutos/). Sólo te tomará 10 minutos.**