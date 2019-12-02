
# Curiosidades en contenedor de contenidos en JSX con react

Se tiene por obligacion con react con JSX establecer el estilo(html) que tendra cuyo componente debe estar lo que queremos devolver dentro de un contenedor.

Pero tambien si queremos retornar una estructura fuera de un contenedor entones debes usar

~~~
	<React.Fragment>
		<h1>Hello</h1>
		<p>How are you ?</p>
	</React.Fragment>
~~~