
# Curiosidades en contenedor de contenidos en JSX con react

Se tiene por obligacion con react con JSX establecer el estilo(html) que tendra cuyo componente debe estar lo que queremos devolver dentro de un contenedor.

Pero tambien si queremos retornar una estructura fuera de un contenedor entones debes usar

~~~
	<React.Fragment>
		<h1>Hello</h1>
		<p>How are you ?</p>
	</React.Fragment>
~~~

# Props

Los props es una abreviacion de propierties en react, Podemos crear propiedaes(argumentos) dentro de nuestros componentes mediante cuando nosotros queramos renderizar el componente le pasaremos los valores de esas propiedades.

Se usan dentro del componente de esta manera: {this.props.name}

ej:

~~~
	<div>
		<h1>{this.props.texto}</h1>
	</div>
~~~

Para poder entablecerle un valor a esta propieadesd que poseee el componente en el cual va insertar estos dato respectivo en el lugar es de esta forma:

#### Estructura

~~~
	ReactDOM.render(
		<componentName

		propiertieComponents

		/>,

		contenedor(etiqueta ej: div,h1,footer,body y etc(recordar que tenemos las capacidades del html por ende tambien podemos buscar un elemento en base al id que se le cree y muchas otras cositas mas))
	)
~~~


Ejemplo de insertado de datos dentro de un componente;

~~~
	ReactDOM.render(
		<Titulo

		texto="Estoy Vivo joder"

		/>,

		contenedorEtiquetaTitulo
	)
~~~