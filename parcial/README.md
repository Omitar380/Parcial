# Sistema Gestor de Ventas e Inventario (Mini-POS)

Aplicación de consola desarrollada en C# con .NET 8 para gestionar productos, inventario y ventas.

## Requisitos

- .NET SDK 8.0 o superior.

## Ejecución

1. Abrir una terminal en la carpeta del proyecto.
2. Compilar el proyecto:

```bash
dotnet build
```

3. Ejecutar la aplicación:

```bash
dotnet run
```
## ¿Cómo funciona el código?
El programa es una aplicación de consola que funciona como un pequeño sistema de ventas e inventario. Toda la información se almacena temporalmente en cuatro listas: una para los nombres de los productos, otra para los precios, otra para el stock disponible y otra para las unidades vendidas. Los datos se mantienen únicamente mientras el programa está ejecutándose.

Al iniciar, el método Main crea las listas y las variables que almacenan el total de ventas y el dinero acumulado en caja. Después muestra un menú dentro de un ciclo do-while. Este ciclo mantiene el programa activo hasta que el usuario selecciona la opción 5, que finaliza la ejecución.

La opción 1 permite registrar un producto. El programa solicita su nombre, precio y stock inicial. Valida que el nombre no esté vacío, que el precio sea mayor que cero y que el stock sea un número válido. También compara el nombre ingresado con los productos existentes para evitar duplicados, sin diferenciar entre mayúsculas y minúsculas.

La opción 2 muestra el inventario completo. Para cada producto se imprime su identificador, nombre, precio y stock actual. Cuando un producto tiene menos de cinco unidades disponibles, se muestra la alerta [ALERTA: BAJO STOCK].

La opción 3 registra una venta. Primero muestra los productos disponibles y permite seleccionar uno mediante su número. Luego solicita la cantidad que se desea comprar y verifica que no sea mayor que el stock existente. Si la cantidad es válida, pregunta si el cliente tiene descuento. Finalmente calcula el subtotal, el descuento del 10 %, el IVA del 19 % y el total a pagar.

El método CalcularFactura centraliza las operaciones matemáticas. Recibe el precio, la cantidad y la respuesta sobre el descuento. Devuelve el total de la venta y utiliza los parámetros out para entregar por separado el valor del IVA y del descuento.

Después de completar una venta, el programa descuenta las unidades del inventario, aumenta las unidades vendidas del producto, incrementa el número total de ventas y suma el valor de la venta al dinero acumulado en caja. Luego imprime un ticket con el detalle de la operación.

La opción 4 genera un reporte con el número de ventas, el total ingresado a caja, el promedio por venta y el producto con mayor cantidad de unidades vendidas. Si todavía no existen ventas, informa que no hay datos registrados.

Los métodos LeerEntero, LeerDecimal y LeerSiNo validan las entradas del usuario mediante ciclos y métodos como int.TryParse y decimal.TryParse. Esto evita que el programa se cierre cuando el usuario introduce letras, números fuera de rango o valores inválidos. Además, el bloque try-catch del menú captura errores inesperados y muestra un mensaje sin finalizar abruptamente la aplicación.

## Instrucciones de ejecución

1. Clonar el repositorio:
   git clone https://github.com/Omitar380/Parcial.git

2. Entrar a la carpeta del proyecto:
   cd Parcial/parcial

3. Ejecutar el proyecto:
   dotnet run