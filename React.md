
# Curiosidades en contenedor de contenidos en JSX con react

Se tiene por obligacion con react con JSX establecer el estilo(html) que tendra cuyo componente debe estar lo que queremos devolver dentro de un contenedor.

Pero tambien si queremos retornar una estructura fuera de un contenedor entonces debes usar

~~~
	<React.Fragment>
		<h1>Hello</h1>
		<p>How are you ?</p>
	</React.Fragment>
~~~

# Estilos

Cuando nosotros queremos que un componente en react tenga estilos de css nosotros solamente debemos importarles sin hacer nada mas ya que react por defecto se encarga de montarlo en todo el componente en el cual nosotros añadimos estos estilos 🧐.

~~~
import style '../components/component_name/styles/estilo.css'
~~~

# Poner los estilos por clase

~~~

<div>
	<h1 className="nombreDeTuClase">Hola Mundo!</h1>
</div>

~~~

# Props

Los props es una abreviacion de propierties en react, Podemos crear propiedaes(argumentos) dentro de nuestros componentes cuando nosotros queramos mandar datos para renderizar el componente con datos dinamicamente le pasaremos los valores de esas propiedades.

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


# Manejo de Eventos cuando cambia un estado dentro del componente

1. Ver lo que nosotros queremos queremos ver cuando se lance una accion por hacer algo, ya sea guardar o escribir tu nombre por un formulario o modal
1. Obtener los valores mediante la persona interactue con nuestra pagina manejando el evento de cambios

ej:

~~~
	class BadgeForm extends React.Component{

    handleChange = e => {
        console.log({
        	//Obtener el nomber que se le asigno dentro del evento de cambios
        	//EJ: nombre_input
            name: e.target.name,
            //Se obtiene el valor dentro de esa etiqueta controlando los cambios que ocurran dentro de este
            value: e.target.value
        });
    };

    render(){
        return (
            <div>
                <h1>New Attendant</h1>

                <form>
                    <div className="form-group">
                        <label>First Name</label>
                        //En esta parte nosotros creamos un evento controlador de cambios
                        <input onChange={this.handleChange} className="form-control" type="text" name="name_form"></input>
                    </div>

                    <button className="btn btn-primary">Save</button>
                </form>
            </div>
        );
    }
}
~~~


Si tuvieramos que obtener el evento cuando alguien haga click en un boton que tengamos en nuestros componentes seria:

~~~
	handleClick = e => {
		console.log("Se ha activado el evento click")
	}

	<button onClick={this.handleClick}></button>
~~~

# Ciclo de Vida

## Montaje

El artista que aparece en escena que tenemos en nuestros componentes.

Cuando se monta suceden tres cosas:

1. Constructor (Todos los estados que se necesitan)
1. render (Cuando empiezes a crear cosas)
1. componentDidMount (Cuando te vayas a mostrar)

## Actualizacion

Cuando el artista cambia de actitud y vestimentan en nuestros componentes.

Cuando este va a hacerlo primero tiene que seguir estos pasos:

1. render (Se pone la ropa sin color)
1. componentDidUpdate (Estados Nuevos, Estados antiguos) (Este colorea la ropa y recuerda que colores tenia antess)

## Desmontar

Cuando el artista se retira de nuestros escenarios 😿 y tenemos que dejar todo limpio para la proxima escena.

Por lo cual lo que debemos hacer es lo siguiente:

1. componentWillUnmount (Dejamos todo como nuevo y sacamos todo lo usado sillas, limpiamos el piso, retiramos cortinas y telones, apagamos las luces)

# LLamadas a una api

Cuando nosotros vamos a obtener informacion tendremos 3 estados:

1. Loading (Se envia la peticion y se espera)
1. Error (Respuesta de la api indicando un error)
1. Datos (Respuesta de la api que pudo enviarnos bien el dato y puede estar vacio por que aun no tiene datos)

# Hooks

Permite a los componentes funcionales tener caracteristicas que solo las clases tienen:

1- Manejo de los estados
2- Control de un ciclo de vida
3- Ejecutar acciones

## Manejo de estados

Nosotros usarios en este punto dentro de nuestros componentes funcionales el metodo:

useState
//para manejar los estados dentro del componente funcional

## Manejo de un ciclo de vida

Para el manejo de los ciclos de vida usariamos:

useEffect

Para suscribir el componente a su ciclo de vida, osea podemos estar pendientes del efecto de uno para cuando desaparesca de escena hagamos algo.

## Ejecutar acciones

useReducer

Este ejecutara todas las acciones que nos vengan como props.

Tambien nosotros podemos crear nuestros propios hooks para agregarle superpoderes a nuestros componentes funcionales!

# Reglas para Custom Hooks

1. Usamos los hooks fundamentales apra crear nuevos hooks custom, estos hooks iran en su propia funcion y su nombre comenzara con la palabra 'use'.

2. un hook jamas lo podemos ejecutar condicionalmente

La ventaja de usar los personalizados por nosotros que podemos añadirle logica para que haga una serie de cosas y validar si queremos como una suma de un conteo por ejemplo:

~~~
function useIncreaseCount(max){
	//useState siempre nos devuelve un array por eso lo usamos y le agregamos un valor por defecto dentro de los parentesis en este caso es 0 para la variable count
	
	// Es como decir:

    // const [state, setState] que mayormente usamos con regularidad en componentes de clase :o

    // Por lo cual este funciona como crear variable y crear funcion para setearle valor cosa que nosotros haremos la logica despues que sera el encargado de hacer algo

	const [count, setCount] = React.useState(0);

	if(count > max){
		setCount(0);
	}

	return [count, setCount]
}
~~~

