
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

# Paginas

La pagina es un componente que tiene otros componentes

# Componente

1. Siempre se debe importar el paquete react para poder crear el componente
1. Creamos una clase con un nombre del cual como se llamara nuestro componente y este debe extenderse(heredar) del React.Component para poder usarlo como un componente en react.
1. Al final tenemos que exportar nuestro componente osea el nombre de la clase que nosotros hemos creado

~~~
	import react from 'react';

	class Titulo extends React.Component{
		render(){
			return (
				<h1>Hello World!</h1>
			)
		}
	}

	export default Titulo;
~~~

# Pintar el componente

Para pintar el componente nosotros necesitamos usar el paquete 'react-dom' para poder renderear en pantalla

1- ReactDOM.render(__qué__,__donde__)

ej:

~~~
	// JSX Necesita react y react-dom
	import React from 'react';
	import ReactDOM from 'react-dom';
	import 'bootstrap/dist/css/bootstrap.css';
	import './global.css'
	// Componentes
	import Badge from './components/Badge';
	import BadgeNew from './pages/BadgeNew';
	// JSX
	// const jsx = <h1>Hello, Platzi Badges from React!</h1>;
	// tipo elemento, atributos(props o propiertes),contenido
	const element = React.createElement
	     (
	         'h1',
	         // props(funcionalidades o caracteristicas como un objeto)
	        { href: 'https://platzi.com' },
	         'hola! Soy los hijos.'
	    );
~~~