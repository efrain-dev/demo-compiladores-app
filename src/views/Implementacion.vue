<template>
  <div>
    <div class="">
      <b-navbar toggleable="lg" class="nav-im">
        <b-navbar-toggle target="nav-collapse1"></b-navbar-toggle>
        <b-collapse id="nav-collapse1" is-nav>
          <b-nav vertical>
            <b-nav-item href="#que-es-una-api" target="_self">Que es una Api?</b-nav-item>
            <b-nav-item href="#que-es-una-analizador-lexico" target="_self">Que es un analizador lexico?</b-nav-item>
            <b-nav-item href="#que-es-una-analizador-sintactico" target="_self">Que es un analizador sintactico?
            </b-nav-item>
            <b-nav-item href="#uso-de-api-analizador" target="_self">Uso de api analizador</b-nav-item>
            <b-nav-item href="#uso-de-api-analizador-lexico" target="_self">Uso de api analizador lexico</b-nav-item>
            <b-nav-item href="#uso-de-api-analizador-sintactico" target="_self">Uso de api analizador sintactico
            </b-nav-item>
            <b-nav-item href="#uso-ejemplo" target="_self">Ejemplos de uso</b-nav-item>

          </b-nav>
        </b-collapse>
      </b-navbar>
      <div class="contenido m-5">
        <section class="my-5">
          <h1>Implementacion de api</h1>
          <a name="que-es-una-api"></a>
          <h2 class="text-white">Que es una Api?</h2>
          <p class="text-justify text-white">Las apis son un conjunto de protocolos que sirven para el desarrollo de
            software y la integración de aplicaciones, con la finalidad de permitir a dos aplicaciones comunicarse entre
            sí a través de una serie de reglas. Una API se puede definir como una especificación formal que establece
            cómo un módulo de un software se comunica o interactúa con otro para cumplir una o muchas funciones. </p>
          <p class="text-justify text-white">En la programación las APIS son las que le permiten al programador
            comunicarse de manera más fácil con el lenguaje de programación que se está utilizando, las API´s en resumen
            son instrucciones y líneas de código ya definidas que un lenguaje de programación tiene preparado para hacer
            más sencilla la programación.</p>
          <div style="text-align: center">
            <img style="width: 40%;" src="../assets/api.png" alt="">
          </div>
        </section>
        <section class="my-5">
          <a name="que-es-una-analizador-lexico"></a>
          <h2 class="text-white">Que es un analizador Léxico</h2>
          <p class="text-justify text-white">Su principal función consiste en leer los caracteres de entrada y elaborar
            como salida una secuencia de componentes léxicos que utiliza el analizador sintáctico para hacer el
            análisis. Esta interacción, suele aplicarse convirtiendo al analizador léxico en una subrutina o corrutina
            del analizador sintáctico. Recibida la orden "obtén el siguiente componente léxico" del analizador
            sintáctico, el analizador léxico lee los caracteres de entrada hasta que pueda identificar el siguiente
            componente léxico.</p>
        </section>
        <section class="my-5">
          <a name="que-es-una-analizador-sintactico"></a>
          <h2 class="text-white">Que es un analizador Sintáctico</h2>
          <p class="text-justify text-white">Un analizador sintáctico o parser (viene del inglés: parse - analizar una
            cadena o texto en componentes sintácticos lógicos) es un programa que normalmente es parte de un compilador.
            El compilador se asegura de que el código se traduce correctamente a un lenguaje ejecutable. La tarea del
            analizador es, en este caso, la descomposición y transformación de las entradas en un formato utilizable
            para su posterior procesamiento. Se analiza una cadena de instrucciones en un lenguaje de programación y
            luego se descompone en sus componentes individuales.</p>
        </section>
        <section class="my-5">
          <h1>Forma de uso</h1>
          <a name="uso-de-api-analizador"></a>
          <h2 class="text-white">Uso de api analizador</h2>
          <p class="text-justify text-white">Como primero debemos tomar en cuenta que es un request tipo GET la url es
            <u>https://devartworks.online/ProyectoCompiladores/Analizador</u> y necesita
            de dos parámetros que son opt y dataText, opt tiene 2 variables aceptables que son "Lexico" y "Sintactico"
            el parámetro dataText solo permite información tipo de String y en
            este se debe proporcionar el código a analizar y una vez realizado esto el servidor respondería con la
            respuesta.
          </p>
        </section>
        <section class="my-5">
          <a name="uso-de-api-analizador-lexico"></a>
          <h2 class="text-white">Uso de api analizador lexico</h2>
          <p class="text-justify text-white">Al mandar en opt "Lexico" la api retornaría la siguiente respuesta tipo
            json:</p>

          <p class="text-justify text-white">[ { "token": "Tipo de dato", "lexema": "int", "cadena": "int", "linea": 0,
            "columna": 0 }, { "token": "Marcador de inicio", "lexema": "main", "cadena": "main", "linea": 0, "columna":
            4 }, { "token": "Parentesis", "lexema": "De apertura", "cadena": "(", "linea": 0, "columna": 8 }, { "token":
            "Parentesis", "lexema": "De Cierre", "cadena": ")", "linea": 0, "columna": 9 } ]</p>
          <div style="text-align: center">
            <img style="width: 80%;" src="../assets/lexico-post.png" alt="">
          </div>

        </section>
        <section class="my-5">
          <a name="uso-de-api-analizador-sintactico"></a>
          <h2 class="text-white">Uso de api analizador sintactico</h2>
          <p class="text-justify text-white">Al mandar en opt "Sintactico" la api retornaría la siguiente respuesta tipo
            json:</p>
          <p class="text-justify text-white">{ "mensaje":"Error de sintaxis. Linea: 0 Columna: 0 Texto:null",
            "tipo":"error" }</p>
          <div style="text-align: center">
            <img style="width: 80%;" src="../assets/sintactico-post.png" alt="">
          </div>
        </section>

        <section class="my-5">
          <a name="uso-ejemplo"></a>
          <h2 class="text-white">Ejemplo de Uso</h2>
          <p class="text-justify text-white">En este caso mostraremos un ejemplo de uso en js utilizando vue.</p>
          <div style="text-align: center">
            <img style="width: 60%;" src="../assets/ejemplo.png" alt="">
          </div>
        </section>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Implementacion"
}
</script>

<style scoped>
.nav-im {
  background-color: transparent;
  display: inline-block;
  height: 100vh;
  top: 10px;
  position: sticky;
}

.contenido {
  display: inline-block;
  position: absolute;
}


</style>