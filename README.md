# Metodo-de-matriz-JavaScript
Los métodos de arrays en JavaScript son funciones predefinidas que se pueden aplicar a los objetos de tipo array para realizar diversas operaciones. Estos métodos permiten agregar, eliminar, modificar, buscar y transformar elementos dentro de un array de manera eficiente. 

A contiunacion, definiiremos cada uno de los metodos, sus sintaxis, ejemplos y una situacion en el que podriamos aplicarlo dentro de una aplicacion.


#  push()

El método push() se utiliza para agregar uno o más elementos al final de un array y devuelve la nueva longitud del array actualizado.

Sintaxis:

        array.push(elemento1, elemento2, ..., elementoN)

Ejemplo:
         let frutas = ['manzana', 'platano'];
         let nuevaFrutas = frutas.push('naranja', 'mango');
        // nuevaFrutas es 4, fruits ahora es ['manzana', 'platano', 'naranja', 'mango']
        
Situacion: Un cliente le solicita crear una tienda online de venta de articulos electronicos, donde los usuarios pueda ir seleccionado los articulos que desean, como hariamos para ir agregando los articulos seleccionado al carrito de compras?

        let carrito = []
        carrito.push('Televisor Samsug 40 pulgadas');
        carrito.push('Celular Samsugn P7');
        carrito.push('Microonda Midas');
        console.log(carrito); // ['Televisor Samsug 40 pulgadas', 'Celular Samsugn P7', 'Microonda Midas'];
        carrito.push('Plancha marca Midas');
        console.log(carrito); // ['Televisor Samsug 40 pulgadas', 'Celular Samsugn P7', 'Microonda Midas', 'Plancha marca Midas'];

# pop()

La función pop() se utiliza para eliminar el último elemento de un array y devuelve el elemento eliminado. Además de eliminar el elemento, el tamaño (longitud) del array se reduce en 1.

Sintaxis:

    array.pop()

Ejemplo:

    let frutas = ['manzana', 'plátano', 'naranja'];
    let ultimaFruta = frutas.pop();
    // ultimaFruta es 'naranja', frutas ahora es ['manzana', 'plátano']

Siempre que necesites eliminar y obtener el último elemento de un array, el método pop() es una opción útil y práctica.

Situacion: Dentro de un arreglo se encuentran los productos agregados al carrito de compras de un cliente, el cliente desea cancelar el ultimo pedido.
    
    let carrito = ['mochila', 'pelota','zapatillas', 'televisor'];
    let ultimoPedido = carrito.pop();
    
    console.log(carrito); // ['mochila', 'pelota','zapatillas'];
    console.log(ultimoPedido); // 'televisor'

# .concat()

Se utiliza para combinar dos o más arrays y crear un nuevo array resultante de la concatenación. No modifica los arrays originales, sino que devuelve un nuevo array que contiene los elementos de los arrays combinados.

Sintaxis:

        array.concat(array1, array2)

Ejemplo:

        let arreglo1 = ['a', 'b', 'c'];
        let arreglo2 = ['d', 'e', 'f'];
        let nuevoArreglo = array1.concat(arreglo2);
        // nuevoArreglo es ['a', 'b', 'c', 'd', 'e', 'f']

Situacion:  En una tienda online, puedes tener diferentes arreglos de productos, como "productos nuevos", "productos en oferta", "productos más vendidos", etc. Al utilizar .concat(), puedes combinar estos arreglos en uno solo para mostrar una lista de productos completa que incluya todos los tipos de productos.

        let televisores = ['Tv Samsung', 'Tv Tokio']
        let celulares = ['Celular Samsung P5', 'Iphone 12']
        
        productosDisponibles = televisores.concat(celulares);
        console.log(productosDisponibles); // [ 'Tv Samsung', 'Tv Tokio', 'Celular Samsung P5', 'Iphone 12' ]
        
# .find()

Se utiliza para encontrar el primer elemento en un array que cumple con una condición especificada. Devuelve el valor del primer elemento que satisface la condición o undefined si ningún elemento cumple con la condición.

Sintaxis:

        arreglo.find(funcion(elemento, indice, arreglo) {
             // Condición de búsqueda
        });

Ejemplo:

            let frutas = [
              { nombre: 'manzana', color: 'rojo' },
              { nombre: 'plátano', color: 'amarillo' },
              { nombre: 'naranja', color: 'naranja' }
            ];

            let frutaRoja = frutas.find(function(fruta) {
              return fruta.color === 'rojo';
            });
            // frutaRoja es { nombre: 'manzana', color: 'rojo' }

Situacion: Cuando un usuario agrega un artículo al carrito de compras en una tienda online, puedes utilizar .find() para verificar si el artículo ya existe en el carrito. Esto te permite evitar duplicados y realizar acciones específicas, como aumentar la cantidad del artículo existente en lugar de agregarlo nuevamente.

            // Arreglo para almacenar los productos en el carrito de compras
            let carrito = [];

            // Función para agregar un artículo al carrito de compras
            function agregarAlCarrito(articulo) {
              // Verificar si el artículo ya existe en el carrito
              let productoExistente = carrito.find(function(item) {
                return item.id === articulo.id;
              });

              if (productoExistente) {
                // Si el artículo ya existe, aumentar la cantidad en lugar de agregarlo nuevamente
                productoExistente.cantidad++;
                console.log('Se aumentó la cantidad del artículo en el carrito.');
              } else {
                // Si el artículo no existe, agregarlo al carrito
                carrito.push(articulo);
                console.log('El artículo se agregó al carrito.');
              }
            }

            // Ejemplo de uso
            let articulo1 = { id: 1, nombre: 'Camiseta', precio: 20, cantidad: 1 };
            let articulo2 = { id: 2, nombre: 'Pantalón', precio: 30, cantidad: 1 };

            agregarAlCarrito(articulo1); // El artículo se agregó al carrito.
            agregarAlCarrito(articulo2); // El artículo se agregó al carrito.

            agregarAlCarrito(articulo1); // Se aumentó la cantidad del artículo en el carrito.

            console.log(carrito);
            // Resultado: [{ id: 1, nombre: 'Camiseta', precio: 20, cantidad: 2 }, { id: 2, nombre: 'Pantalón', precio: 30, cantidad: 1 }]


# .includes()

Se utiliza para verificar si un array contiene un determinado elemento y devuelve un valor booleano (true o false) según el resultado de la búsqueda.

Sintaxi:
    array.includes(elemento)

Ejemplo:

    var numeros = [1, 2, 3, 4, 5];
    var incluyeTres = numeros.includes(3);
    // incluyeTres es true

    var incluyeDiez = numeros.includes(10);
    // incluyeDiez es false

Situacion: Qué hay en la tienda

Usaremos el método includes para buscar un elemento en un arreglo. arreglo.includes() devolverá true o false dependiendo de si el elemento se encuentra.

     let productosExistentes = [
          'camisa',
          'televisor',
          'plancha',
          'radio',
          'celulares',
          'ventilador',
          'libros',
      ];

      let listaCompras = [
          'zapato',
          'camisa',
          'libros'
      ];


      for (producto of listaCompras){
          console.log(producto + ':' + productosExistentes.includes(producto));
      };


Utilizamos el método .includes() con un for loop para verificar si cada elemento en el arreglo listaCompras se puede encuentran en el arreglo productosExistentes.

Resultado:

    zapato:false
    camisa:true
    libros:true


# .indexOf()

Se utiliza para obtener el índice de la primera aparición de un elemento especificado en un array. Devuelve el índice del elemento si se encuentra en el array, y -1 si el elemento no está presente.

Sintaxis:

    array.indexOf(elemento)

Ejemplo:

    let frutas = ['manzana', 'plátano', 'naranja'];
    let indiceManzana = frutas.indexOf('manzana');
    // indiceManzana es 0

    var indicePera = frutas.indexOf('pera');
    // indicePera es -1
    
Utilizaremos el método indexOf para encontrar el número de indice de nuestra fruta favorita.

    let frutas = ['manzana', 'plátano', 'naranja'];

    let favorita = 'naranja';
    
    let frutaFavorita = frutas.includes(favorita) ? frutas.indexOf(favorita) : 'No se encuentra en la lista';
    console.log('Posicion:', frutaFavorita);
    
Dentro de la variable frutaFavorita, obtenemos el indice de nuestra fruta que deseamos, primeramente verificamos si existe dentro de la lista, para posteriormente obtener su indice, en caso contrario nos arrojara una mensaje que no se encuentra en la lista;


# .findLastIndexOf()

Se utiliza para encontrar el índice del último elemento en un array que cumple con una condición especificada. Retorna el índice del último elemento que satisface la condición de una función de prueba proporcionada, o -1 si no se encuentra ningún elemento que cumpla con la condición. Es similar a indexOf, pero busca de forma inversa desde el final de un arreglo.

Sintaxis:

    array.lastIndexOf(elemento)

Ejemplo: 

        let colores = ['rojo', 'verde', 'azul', 'verde', 'amarillo'];
        let ultimoIndiceVerde = colores.lastIndexOf('verde');
        // ultimoIndiceVerde es 3

        let ultimoIndiceBlanco = colores.lastIndexOf('blanco');
        // ultimoIndiceBlanco es -1

En este ejemplo, el array colores contiene cinco elementos: 'rojo', 'verde', 'azul', 'verde' y 'amarillo'. El método lastIndexOf() se utiliza para obtener el índice de la última aparición de 'verde' en el array. Como 'verde' se encuentra en el índice 3 (contando desde el final del array), la variable ultimoIndiceVerde es 3. Luego, se busca el índice de 'blanco', que no está presente en el array, por lo que la variable ultimoIndiceBlanco es -1.

El método lastIndexOf() es útil cuando necesitas obtener la posición de la última aparición de un elemento específico en un array. Al buscar hacia atrás, puedes obtener la última instancia del elemento en lugar de la primera, como lo hace el método indexOf().

Situacion: Al pagar en la caja del supermercado, 'leche' se escaneó accidentalmente dos veces. Buscaremos el índice de la segunda 'leche' escaneada accidentalmente usando .lastIndexOf().

        let productos = ['leche', 'harina', 'gaseosa', 'leche', 'lechuga'];
        let productoExtra = colores.lastIndexOf('leche');
        // productoExtra es 3

# .shift()

Se utiliza para eliminar el primer elemento de un array. Desplaza todos los elementos restantes hacia una posición inferior y devuelve el elemento eliminado. Además, actualiza la longitud del array.

Sintaxis:

        array.shift()

El método .shift() no requiere argumentos, ya que siempre elimina el primer elemento del array. Al eliminar el primer elemento, todos los demás elementos se desplazan hacia una posición inferior. La longitud del array se actualiza automáticamente después de la eliminación.

Ejemplo:

        let frutas = ['manzana', 'plátano', 'naranja'];
        let primeraFruta = frutas.shift();
        // primeraFruta es 'manzana', frutas ahora es ['plátano', 'naranja']

Situacion: Utilizaremos el metodo .shift(), para eliminar el primer elemento de un arreglo, colocarlo en una variable e imprimirlo en consola. Se presenta un arreglo que contiene televisores con diferentes tamaño, ordenados de menor a mayor.

        let televisores = ['32 pulgadas', '40 pulgadas', '50 pulgadas', '55 pulgadas'];
        let primerTelevisor = televisores.shift();

        console.log('El primer televisor eliminado es:', primerTelevisor);
        // primerTelevisor es '32 pulgadas'
        console.log('El arreglo actualizado de televisores es:', televisores);
        // Lista actualizada de televisores ['40 pulgadas', '50 pulgadas', '55 pulgadas'];
        
# .unshift()

Se utiliza para agregar uno o más elementos al inicio de un array. Desplaza todos los elementos existentes hacia una posición superior para hacer espacio para los nuevos elementos. Además, actualiza la longitud del array.

Sintaxis:
        
        array.unshift(elemento1, elemento2, ..., elementoN)

Ejemplo:

        let frutas = ['plátano', 'naranja'];
        frutas.unshift('manzana', 'uva');
        // frutas ahora es ['manzana', 'uva', 'plátano', 'naranja']
        
Situacion: Utilizaremos el metodo .unshift(), para agregar a un arreglo de televisores ordenadas por tamaño un nuevo televisor en el que este es el mas pequeño en pulgadas.

        let televisores = ['40 pulgadas', '50 pulgadas', '55 pulgadas'];
        let nuevoTelevisor = '32 pulgadas';
        televisores.unshift(nuevoTelevisor);

        console.log('El arreglo actualizado de televisores es:', televisores);
        // El resultado seria televisores ['32 pulgadas', 40 pulgadas', '50 pulgadas', '55 pulgadas'];

# .reverse()

Se utiliza para invertir el orden de los elementos en un array. El primer elemento se convierte en el último, el segundo en el penúltimo, y así sucesivamente. Este método modifica el array original y no devuelve un nuevo array.

Sintaxis:
        array.reverse()
        
Ejemplo:

        let numeros = [1, 2, 3, 4, 5];
        numeros.reverse();
        console.log(numeros); // [5, 4, 3, 2, 1]
        
Situacion: La variable televisores, contiene una lista de televisores disponible en una tienda de Electronica, el mismo esta ordenado de por tamaño, de menor a moyor pulgadas, utilzaremos el metodo .reverse() para invertir el orden.

        let televisores = ['32 pulgadas', '40 pulgadas', '50 pulgadas', '55 pulgadas'];
        televisores.reverse()
        
        console.log(televisores) // ['55 pulgadas','50 pulgadas', '40 pulgadas', '32 pulgadas']



# .splice()

Se utiliza para modificar un array al agregar, eliminar o reemplazar elementos existentes. Puede realizar varias operaciones en el array en función de los argumentos que se le pasen.

Sintaxis:

            array.splice(indice, cantidad, elemento1, elemento2, elemento3)
            // El índice en el que se desea realizar la operación. Indica la posición donde se va a empezar a realizar la                   modificación.
            // La cantidad de elementos a eliminar desde el índice especificado. Si se omite, todos los elementos a partir del                    índice hasta el final del array serán eliminados.
            // Elemento: Los elementos que se desean agregar al array en el índice especificado. Estos elementos se insertarán                en lugar de los elementos eliminados.

Ejemplo 1: Eliminar elementos del arreglo

        // Caso Numero 1, :
        
        let numeros = [1, 2, 3, 4, 5];
        numeros.splice(2, 2);
        console.log(numeros);
        // Al llamar a .splice(2, 2), se eliminan dos elementos a partir del índice 2. El array resultante será [1, 2, 5].
 
 
Ejemplo 2: Agregar elementos al arreglo
        
        let frutas = ['manzana', 'pera', 'naranja'];
        frutas.splice(1, 0, 'plátano', 'uva');
        console.log(frutas);
        // El array resultante será ['manzana', 'plátano', 'uva', 'pera', 'naranja']
        
Ejempo 3: Reemplazar elementos del array

        let colores = ['rojo', 'verde', 'azul'];
        colores.splice(1, 1, 'amarillo', 'morado');
        console.log(colores);
        // El array resultante será ['rojo', 'amarillo', 'morado', 'azul'].
        
 
 Obs: El método modifica el arreglo original y puede tener un efecto directo en su longitud.
 
Situacion: En una tienda de ropas, las camisas medianas ('M') y grandes ('L') están agotadas, de modo que se debe eliminar del arreglo. Pero las camisas 'XL' están disponibles nuevamente, por lo que se deben agregar otra vez al mismo.

        let camisas = ['M', 'L', 'S'];
        camisas.splice(0,2,'XL')

        console.log(camisas)
        // el resultado seria que la variable camisas contrendra ['XL','S']
    
        

 # .join()
 
Se utiliza para crear una cadena de texto a partir de los elementos de un array. Concatena todos los elementos en el orden en que aparecen en el array y los separa mediante un separador especificado.
        
Sintaxis:

        array.join(separador)
        
Separador: el carácter o cadena que se utilizará como separador entre los elementos del array al concatenarlos en la cadena resultante. Si se omite, se utilizará una coma (',') como separador por defecto.

Ejemplo:

        let frutas = ['manzana', 'plátano', 'uva'];
        let cadena = frutas.join(', ');

        console.log(cadena);
        // resultado seria: manzana, plátano, uva
        
Situacion: Tenemos un arreglo, con varios elementos, con el metodo .join() lo uniremos con el strign &.

             let productos = [
                  'Camisas',
                   'Pantalones',
                   'Calzados'
                 ]

              let cadena = productos.join(' & ')
              console.log('En venta: ' + cadena)
              // Resultado: "En venta: Camisas & Pantalones & Calzados"







