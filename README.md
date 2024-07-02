# Angular

... **DOCUMENTO EN DESARROLLO** ...

## Introducción

**Angular es un framework** de desarrollo de aplicaciones web desarrollado y mantenido por Google. Angular está basado en el lenguaje de programación **TypeScript** y sigue el patrón de diseño de arquitectura MVC (Modelo-Vista-Controlador), específicamente la variante MVVM (Modelo-Vista-VistaModelo).

**AngularJS** fue desarrollado en 2009 por Misko Hevery y Adams Abrons. Posteriormente fue liberado el proyecto como una biblioteca de código abierto. Adams Abrons abandonó el proyecto pero Misko Hevery, como empleado de Google, continuó con el desarrollo y mantenimiento del proyecto.

A partir de la versión **2.0**, anunciada en Septiembre de 2014, AngularJS fue reescrito utilizando el lenguaje TypeScript y se rediseñó por completo todo el framework. Esta nueva versión pasó a llamarse únicamente **Angular**. Ambas versiones conviven, aunque AngularJS ha quedado acotada en versiones 1.X.Y mientras que Angular continúa su evolución. Ambos proyectos tiene ciclos de vida independientes.

**Angular** se utiliza para construir aplicaciones web de una sola página (SPA) y facilita la creación de interfaces de usuario dinámicas y interactivas.

Las aplicaciones de una sola página, conocidas como **SPAs** (_Single Page Applications_), representan un enfoque revolucionario en el desarrollo web al ofrecer una experiencia de usuario más fluida y dinámica. A diferencia de las aplicaciones tradicionales, donde la navegación implica cargar páginas completas, las SPAs cargan una única página HTML inicial y actualizan dinámicamente el contenido según las interacciones del usuario.

Las principales **características** de Angular incluyen la vinculación bidireccional de datos, que permite la sincronización automática entre la vista y el modelo de datos; inyección de dependencias, que promueve la modularidad y la reutilización de código; y un conjunto de herramientas y bibliotecas que simplifican tareas comunes como la manipulación del DOM, la gestión de eventos y la realización de peticiones HTTP.

Angular aprovecha la tecnología de los componentes web o _'web components'_ y el _'Shadow DOM'_ para apoyar el desarrollo impulsado por componentes. La **arquitectura** de Angular puede resumirse en:

- **Módulos**: Angular organiza la aplicación en módulos, que son conjuntos lógicos de componentes, servicios, directivas y otros artefactos relacionados. Los módulos ayudan a estructurar y organizar la aplicación, facilitando la carga y gestión de diferentes partes de la misma.

- **Componentes**: son los bloques de construcción fundamentales de una aplicación Angular. Cada componente está asociado a una vista y un controlador (o en términos de Angular, un ViewModel). La vista define la interfaz de usuario, mientras que el controlador maneja la lógica y los datos relacionados con esa vista.

- **Templates**: son archivos que definen la estructura y el diseño de las vistas en Angular. Utilizan una sintaxis especial, que combina HTML con extensiones específicas de Angular para la vinculación de datos y la manipulación de la interfaz de usuario.

- **Directivas**: son atributos especiales en el HTML que permiten extender o modificar el comportamiento de los elementos DOM. Angular incluye directivas integradas, como `*ngIf` para controlar la visibilidad de elementos, o `*ngFor` para realizar bucles sobre conjuntos de datos.

- **Servicios**: los servicios en Angular son objetos singleton que realizan funciones específicas y que pueden ser compartidos entre componentes. Se utilizan para encapsular la lógica de negocio, la manipulación de datos, o para realizar operaciones asíncronas, como llamadas HTTP.

- **Inyección de dependencias**: Angular utiliza un sistema de inyección de dependencias para proporcionar a los componentes y servicios las dependencias que necesitan. Esto facilita la modularidad y la reutilización de código al tiempo que mejora la testabilidad.

- **Vinculación de datos (_Data Binding_)**: Angular ofrece una potente vinculación de datos bidireccional, lo que significa que los cambios en el modelo de datos se reflejan automáticamente en la vista y viceversa. Esto simplifica la actualización de la interfaz de usuario en respuesta a eventos o cambios en los datos de la aplicación.

- **Enrutamiento**: Angular proporciona un módulo de enrutamiento que permite la navegación entre las distintas vistas de la aplicación sin necesidad de recargar la página. Esto es esencial para construir aplicaciones de una sola página (SPA).

> Sección generada por ChatGPT

## Primeros pasos

### Instalación

Angular requiere **Node.js** que se instala descargándolo de su [página oficial](https://nodejs.org/).

Cuando se instala **Node.js** también se instala **_NPM_** (_Node Package Manager_) que nos permite, entre otras cosas, gestionar las dependencias de un proyecto.

Para desarrollar en Angular se puede utilizar como lenguaje de programación tanto **Javascript** como **TypeScript**, pero dado que **Angular está implementado con TypeScript**, se recomienda usar este lenguaje.

Para instalar **Typescript** se utiliza la herramienta **_NPM_** ya que también está publicado como paquete.

[Más información sobre las versiones de Angular](https://angular.dev/reference/versions)

```sh
// Comprobar la versión de Node.js
$ node -v

// Comprobar la versión de NPM
$ npm -v

// Instalar TypeScript
$ npm install -g typescript

// Comprobar la versión de TypeScript
$ tsc --version
```

### Angular CLI

**_'Angular CLI'_** es la herramienta de línea de comandos estándar para crear, depurar construir y publicar aplicaciones Angular.

Esta herramienta está publicada en **_NPM_** como el paquete `@angular/cli` e incluye el binario `ng`:

```sh
// Instalación de 'Angular CLI' de forma global
$ npm install -g @angular/cli

// Comprobar la versión de 'Angular CLI'
$ ng version

// Ver la ayuda general
$ ng help

// Ver la ayuda de un comando en concreto como 'ng serve'
$ ng serve --help
```

[Más información sobre CLI](https://angular.dev/tools/cli)

#### Puesta en marcha del proyecto

Las aplicaciones Angular se desarrollan en el contexto de una espacio de trabajo o **_'workspace'_**. Un espacio de trabajo puede contener múltiples aplicaciones y bibliotecas.

Para crear un nuevo espacio de trabajo y una aplicación inicial dentro de este nuevo espacio de trabajo, se utiliza el comando:

```sh
ng new my-app  // Cambiando 'my-app' por el nombre de la nueva aplicación
```

Este comando nos solicitará información para configurar la aplicación inicial, pudiendo utilizar la configuración que viene por defecto.

A continuación se instalarán todas las bibliotecas y dependencias necesarias. Finalmente tendremos una aplicación inicial completamente funcional y las configuraciones necesarias para su depuración, pruebas y ejecución.

Por defecto la aplicación se crea con el prefijo `app` que se usará en todos los componentes pero puede personalizarse usando el modificador `--prefix`.

[Más información](https://angular.dev/tools/cli/setup-local)

#### Desarrollo del proyecto

**'Angular CLI'** incluye un servidor de desarrollo lo que permite servir la aplicación fácilmente a nivel local.

El comando `ng serve` inicia el servidor, observa el código fuente, reconstruye automáticamente la aplicación cuando detecta algún cambio en el código y recarga la página en el navegador:

```sh
// Navegar dentro del espacio de trabajo
cd my-app

// Arranca el servidor y abre el navegador en 'http://localhost:4200'
ng serve --open
```

#### Compilación del proyecto

Para compilar el proyecto se utiliza el comando `ng build`.

Se compilará el código TypeScript en código JavaScript, se optimizará el código, se empaquetará y se comprimirán (_'minify'_) los ficheros según sea necesario.

Este comando ejecuta el constructor o _'builder'_ definido en el fichero `angular.json`.

Por defecto, cuando se inicializa la aplicación con `ng new` se utiliza el constructor `@angular-devkit/build-angular:application`.

Existen **4 constructores disponibles**, según el tipo de aplicación que se necesite construir.

[Más información](https://angular.dev/tools/cli/build)

#### Despliegue del proyecto

Una vez la aplicación está lista para su despliegue, se puede realizar de varias formas, tanto manual como automática.

Para realizar el despliegue **de forma automática**, disponemos del comando `ng deploy`.

Por ejemplo, podemos añadir un paquete de terceros para realizar el despliegue en **Firebase**:

```sh
# Añade el 'package' en 'angular.json'
$ ng add @angular/fire
# Ejecuta el despliegue
$ ng deploy
```

[Más información](https://angular.dev/tools/cli/deployment)

### Estructura de una aplicación Angular

Cuando se ejecuta el comando `ng new` se instalan las bibliotecas y dependencias necesarias en el nuevo espacio de trabajo, además del **esqueleto funcional** de una aplicación dentro de la carpeta `src/`. Esta aplicación se considera la **aplicación principal** o **aplicación raíz**. El directorio raíz del espacio de trabajo contiene todos los ficheros de configuración, etc.. necesarios para construir y servir la aplicación Angular.

La aplicación inicial creada es la aplicación **por defecto** para todos los comandos lanzados a través de `ng`.

Para un espacio de trabajo que contendrá una sóla aplicación, la subcarpeta `src/` del espacio de trabajo contendrá los ficheros de código (lógica de la aplicación, datos y assets) de la aplicación raíz.

Para espacios de trabajo de tipo _'multi-project'_ cada proyecto estará en su propia carpeta dentro de la carpeta `projects/`.

#### Ficheros de configuración

Todos los proyectos dentro del mismo espacio de trabajo o _'workspace'_ comparten los ficheros de configuración que están en la raíz del espacio de trabajo. Estos ficheros de configuración tienen ámbito del espacio de trabajo y por tanto su configuración afecta a todos los proyectos.

Los archivos de configuración que están en la raíz del espacio de trabajo son los ficheros de configuración de la aplicación raíz. Para un espacio de trabajo de múltiples proyectos, los archivos de configuración específicos de cada proyecto estarán en la carpeta raíz de cada proyecto, dentro de `projects/project-name`.

El fichero `'package.json'` es el fichero estándar de **_NPM_** donde se almacenan las dependencias de terceros que se utilizará para todos los proyectos del espacio de trabajo. Contiene las bibliotecas que necesita la aplicación para ejecutarse tanto en desarrollo como producción:

```json
{
  "dependencies": {
    "@angular/core": "^7.2.0"
  },
  "devDependencies": {
    "@angular/cli": "7.2.0"
  }
}
```

Además de las dependencias el fichero `'package.json'` sirve para indicar información sobre el proyecto como el nombre, versión, nombre del autor, url del repositorio, etc.. y también como contenedor de scripts para automatizar tareas de operaciones rutinarias:

```json
{
  "name": "my-app",
  "version": "0.0.0",
  "scripts": {
    "ng": "ng",
    "start": "ng serve",
    "build": "ng build",
    "test": "ng test",
    "lint": "ng lint",
    "e2e": "ng e2e"
  },
  "devDependencies": {
    // ...
  }
}
```

El fichero `'tsconfig.json'` contiene los parámetros de configuración por defecto de [TypeScript](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html).

El fichero `angular.json` contiene los valores predeterminados de configuración para todos los proyectos en el área de trabajo, incluidas las opciones de configuración para compilar, servir y probar la aplicación.

**Los cambios en los ficheros de configuración no se recargan automáticamente**. Hay que parar la servidor y volver a lanzarlo para que se carguen.

[Más información](https://angular.dev/reference/configs/workspace-config)

#### Carpetas y ficheros de la aplicación

Dentro de la carpeta `/src` tenemos:

- **`app/`**: contiene los componentes Angular que componen la aplicación.

- **`assets/`**: contiene imágenes y otros archivos servidos de forma estática y que se copiarán tal cual cuando se cree la aplicación.

- **`index.html`**: la página HTML principal que se sirve cuando alguien visita el sitio. Los archivos JavaScript y CSS se agregan automáticamente al crear la aplicación, por lo que normalmente no se necesita agregar ninguna etiqueta `<script>` o `<link>` manualmente.

- **`main.ts`**: punto de entrada para la aplicación

- **`styles.css`**: los estilos CSS globales de la aplicación

Dentro de la carpeta `src/`, la carpeta `app/` contiene la lógica y los datos de la aplicación:
  
- **`app.config.ts`**: define la configuración de la aplicación que informa a Angular sobre cómo debe construir la aplicación. Sólo se genera cuando se usa la opción `--standalone`.

- **`app.component.ts`**: define la lógica para el componente raíz de la aplicación, llamado `AppComponent`.

- **`app.component.html`**: define la plantilla HTML asociada con el componente raíz `AppComponent`. Esta vista se convierte en la raíz de la jerarquía de vistas a medida que agrega componentes y servicios a su aplicación

- **`app.component.css`**: define la hoja de estilo CSS básica para el componente raíz `AppComponent`.

- **`app.module.ts`**: define el módulo raíz, llamado `AppModule`, que le dice a Angular cómo ensamblar la aplicación. Inicialmente declara solo el `AppComponent`. A medida que agregue más componentes a la aplicación, deberá declararlos aquí. Sólo se genera cuando se utiliza la opción `--standalone false`.

[Más información](https://angular.dev/reference/configs/file-structure#application-project-files)

## [Components](https://angular.dev/guide/components)

En el contexto de Angular, un componente es una **parte fundamental** de la arquitectura de este framework para el desarrollo de aplicaciones web. Angular utiliza una arquitectura basada en componentes, lo que significa que la interfaz de usuario se construye mediante la composición de componentes individuales.

Todo componente tiene que tener:

- Una **clase** TypeScript que contiene la lógica del componente

- Un **decorador** `@Component` sobre esta clase TypeScript

- Una **plantilla HTML** que controla lo que se renderiza en el DOM

- Un **selector CSS** que define como se utiliza ese componente en el HTML

Opcionalmente puede incluir una lista de estilos CSS que se aplicarán al componente. Por defecto esos estilos **sólo aplican** al componente donde se definen.

```typescript
@Component({
  selector: 'profile-photo',
  template: `<img src="profile-photo.jpg" alt="Your profile photo">`,
  styles: ` img { border-radius: 50%; } `,
})
export class ProfilePhoto { }
```

Como alternativa, se pueden escribir la plantilla y los estilos en ficheros **separados**:

```typescript
@Component({
  selector: 'profile-photo',
  templateUrl: 'profile-photo.html',
  styleUrl: 'profile-photo.css',
})
export class ProfilePhoto { }
```

Los metadatos `templateUrl` y `styleUrl` son relativos al directorio donde reside el componente.

El objeto que se pasa al decorador `@Component` son los **metadatos** del componente.

Angular crea una instancia del componente para cada elemento HTML coincidente que encuentra. El elemento DOM que coincide con el selector de un componente se denomina elemento **anfitrión o host** de ese componente. El contenido de la plantilla de un componente se representa dentro de su elemento anfitrión.

El DOM representado por un componente, correspondiente a la plantilla de ese componente, se denomina **vista o _view_** de ese componente.

[Más información](https://angular.dev/guide/components)

### [Importing and using components](https://angular.dev/guide/components/importing)

Angular dispone de **dos formas** de hacer disponible los componentes:

- Mediante los componentes **_'standalone'_**, siendo la forma recomendada

- Mediante `@NgModule`

Un componente **_'standalone'_** es un componente que tiene `standalone: true` en los metadatos del componente.

Este tipo de componentes de pueden importar **de forma directa** en otros componentes.

```typescript
// profilePhoto.ts
@Component({
  standalone: true,
  selector: 'profile-photo',
})
export class ProfilePhoto { }

// userProfile.ts
@Component({
  standalone: true,
  imports: [ProfilePhoto],
    template: `
      <profile-photo />
      <button>Upload a new profile photo</button>`,
})
export class UserProfile { }
```

### [Selectors](https://angular.dev/guide/components/selectors)

Los selectores se utilizan para identificar los componentes en el DOM y son esenciales para el mecanismo de plantillas de Angular.

Un selector en Angular es una **cadena** que especifica el nombre que se usará para insertar un componente en una plantilla. Los selectores son **_case-sensitive_**.

Además, un único componente puede coincidir exactamente con un selector. Si varios componentes coinciden con un selector, Angular devuelve un error.

Angular realiza esta asociación entre selectores y componentes en **tiempo de compilación**.

Angular dispone de varios tipos de selectores:

1. **Selectores de etiqueta**. Este es el tipo más común. Utiliza el nombre del selector como una etiqueta HTML.

```typescript
@Component({
  selector: 'app-mi-componente',
  templateUrl: './mi-componente.component.html',
  styleUrls: ['./mi-componente.component.css']
})
export class MiComponenteComponent { }
```

```html
<!-- ... -->
<app-mi-componente></app-mi-componente>
<!-- ... -->
```

1. **Selectores de Atributo**. Empareja elementos basándose en la presencia de un atributo HTML y, opcionalmente, un valor exacto para ese atributo.

```typescript
@Component({
  selector: '[app-mi-componente]',
  templateUrl: './mi-componente.component.html',
  styleUrls: ['./mi-componente.component.css']
})
export class MiComponenteComponent { }
```

```html
<!-- ... -->
<div app-mi-componente></div>
<!-- ... -->
```

1. **Selectores de clase**. Coincide con elementos según la presencia de una clase CSS.

```typescript
@Component({
  selector: '.app-mi-componente',
  templateUrl: './mi-componente.component.html',
  styleUrls: ['./mi-componente.component.css']
})
export class MiComponenteComponent { }
```

```html
<!-- ... -->
<div class="app-mi-componente"></div>
<!-- ... -->
```

Los selectores se pueden **combinar** como por ejemplo un selector que seleccione todos los `<button>` de un tipo `type="reset"`:

```typescript
@Component({
  selector: 'button[type="reset"]',
  ...
})
export class ResetButton { }
```

También se pueden definir selectores múltiples separados por comas:

```typescript
@Component({
  selector: 'drop-zone, [dropzone]',
  ...
})
export class DropZone { }
```

Hay que evitar prefijos como `app-` que pueden generar confusión. También hay que evitar el prefijo `ng` ya que es utilizado por Angular.

[Más información](https://angular.dev/guide/components/importing)

### [Styling](https://angular.dev/guide/components/styling)

Los componentes pueden incluir estilos CSS que se aplicarán a todos los elementos que pueda tener el _template_ del componente:

```typescript
@Component({
  selector: 'profile-photo',
  template: `<img src="profile-photo.jpg" alt="Your profile photo">`,
  styles: ` img { border-radius: 50%; } `,
})
export class ProfilePhoto { }
```

Otro modo es escribir los estilos CSS en un fichero separado y referenciado en el decorador:

```typescript
@Component({
  selector: 'profile-photo',
  templateUrl: 'profile-photo.html',
  styleUrl: 'profile-photo.css',
})
export class ProfilePhoto { }
```

Cada componente se puede configurar como el framework aplica los estilos al componente:

- **_ViewEncapsulation.Emulated_**. Este es el modo por defecto. Los estilos sólo aplican al _template_

- **_ViewEncapsulation.ShadowDom_**

- **_ViewEncapsulation.None_**. Desactiva la encapsulación de estilos y se vuelve globales.

En el _template_ del componente se puede usar `<link>` para referenciar un fichero CSS externo. Además, dentro del CSS se puede utilizar la regla `@import` para referenciar un fichero CSS externo.

Estos ficheros externos son tratados por Angular como **estilos externos**, por lo que no se ven afectos por el ámbito de aplicación de los estilos.

### [Accepting data with input properties](https://angular.dev/guide/components/inputs)

Al crear un componente, puede marcar propiedades de clase específicas como **vinculables** agregando el decorador `@Input` en la propiedad:

```typescript
import { Component, Input } from '@angular/core';
@Component({
  selector: 'app-card',
  standalone: true,
  template: `
    <div class="card">
      <h2>{{ title }}</h2>
      <p>{{ description }}</p>
    </div>
  `,
  styleUrl: ['./card.component.css']
})
export class CardComponent {
  @Input() title: string = '';
  @Input() description: string = '';
}
```

Esto le permite vincularse a la propiedad en una plantilla, permitiendo pasar datos entre componentes:

```typescript
import { Component } from '@angular/core';
@Component({
  selector: 'app-root',
  standalone: true,
  template: `
    <h1>My Card Example</h1>
    <app-card [title]="cardTitle" [description]="cardDescription"></app-card>
  `,
  styleUrl: './card.component.css'
})
export class AppComponent {
  cardTitle = 'Card Title';
  cardDescription = 'This is a description of the card.';
}
```

Angular registra los _'input'_ estáticamente en tiempo de compilación. Los _'input'_ no se pueden agregar ni eliminar en tiempo de ejecución.

Al extender una clase de componente, los _'input'_ son heredados por la clase secundaria.

Los nombres utilizados son _'case-sensitive'_. Por tanto, el nombre de la propiedad en el componente debe coincidir con el nombre de la propiedad en la plantilla.

#### [Customizing inputs](https://angular.dev/guide/components/inputs#customizing-inputs)

El decorador `@Input` acepta un objeto de configuración que permite modificar su comportamiento.

Se puede especificar la opción `'required'` para exigir que una entrada determinada siempre deba tener un valor. Si no se especifica un _'input'_ requerido, Angular reporta un error en tiempo de compilación:

```typescript
@Component({...})
export class CustomSlider {
  @Input({required: true}) value = 0;
}
```

Otra forma de personalización de los _'input'_ es mediante **funciones transformadoras** que modifiquen el valor de la propiedad cuando sean asignados por Angular. Este ejemplo, se pone en mayúsculas el título de la tarjeta llamando automáticamente a la función `upperCaseString(...)`:

```typescript
import { Component, Input } from '@angular/core';
@Component({
  selector: 'app-card',
  standalone: true,
  template: `
    <div class="card">
      <h2>{{ title }}</h2>
      <p>{{ description }}</p>
    </div>
  `,
  styleUrl: ['./card.component.css']
})
export class CardComponent {
  @Input({transform: upperCaseString}) title: string = '';
  @Input() description: string = '';
}

function upperCaseString(value: string | undefined) {
  return value?.toUpperCase() ?? '';
}
```

#### [Type checking](https://angular.dev/guide/components/inputs#type-checking)

Cuando se especifica una transformación, el tipo de parámetro de la función de transformación determina los tipos de valores que se pueden establecer para la entrada en una plantilla.

Por ejemplo, el _'input'_ acepta un `number` mientras que la propiedad de la clase es un `string`:

```typescript
@Component({...})
export class CustomSlider {
  @Input({transform: appendPx}) widthPx: string = '';
}
function appendPx(value: number) {
  return `${value}px`;
}
```

#### [Built-in transformations](https://angular.dev/guide/components/inputs#built-in-transformations)

Angular incluye dos funciones de transformación integradas para los dos escenarios más comunes: convertir valores a booleanos y números:

```typescript
import {Component, Input, booleanAttribute, numberAttribute} from '@angular/core';
@Component({...})
export class CustomSlider {
  @Input({transform: booleanAttribute}) disabled = false;
  @Input({transform: numberAttribute}) number = 0;
}
```

#### [Inputs aliases](https://angular.dev/guide/components/inputs#input-aliases)

Se puede especificar un alias opcional para cambiar el nombre de una entrada en las plantillas:

```typescript
@Component({...})
export class CustomSlider {
  @Input({alias: 'sliderValue'}) value = 0;
}
```

```html
<custom-slider [sliderValue]="50" />
```

## [Template syntax](https://angular.dev/guide/templates)

En Angular, una _'plantilla'_ es un fragmento de HTML. Se utiliza una **sintaxis especial** dentro de una plantilla para aprovechar muchas de las funciones de Angular.

Cada plantilla de Angular es una sección de HTML que se incluye como parte de la página que muestra el navegador. Una plantilla HTML en Angular representa una vista o interfaz de usuario en el navegador, como HTML normal, pero con mucha más funcionalidad.

Casi toda la sintaxis HTML es sintaxis de plantilla válida. Sin embargo, debido a que una plantilla de Angular es parte de una página web general y no de la página completa, no es necesario incluir elementos como `<html>`, `<body>` o `<base>`.

:warning: NOTA IMPORTANTE: para eliminar el riesgo de ataques de tipo _'script injection'_, Angular **no soporta** la etiqueta `<script>` en las plantillas.

Cuando se genera una aplicación Angular con la herramienta de Angular CLI, el archivo `app.component.html` es la plantilla **predeterminada** que contiene HTML general.

### [Text interpolation](https://angular.dev/guide/templates/interpolation)

La interpolación se refiere a incrustar expresiones en texto marcado. De forma predeterminada, la interpolación utiliza las llaves dobles `{{` y `}}` como delimitadores:

```typescript
import {Component} from '@angular/core';
import {NgFor} from '@angular/common';
import {CUSTOMERS} from './customers';
@Component({
  standalone: true,
  selector: 'app-root',
  templateUrl: './app.component.html',
  imports: [NgFor],
  styleUrls: ['./app.component.css'],
})
export class AppComponent {
  customers = CUSTOMERS;
  currentCustomer = 'Maria';
  title = 'Featured product:';
  itemImageUrl = '../assets/potted-plant.svg';
  getVal(): number {
    return 2;
  }
}
```

Se utiliza la interpolación para mostrar el valor de las variables en la plantilla de componente correspondiente:

```html
<div>
  <h1>Interpolation and Template Expressions</h1>
  <hr />
  <div>
    <h2>Interpolation</h2>
    <h3>Current customer: {{ currentCustomer }}</h3>
    <p>{{ title }}</p>
    <div><img alt="item" src="{{ itemImageUrl }}"></div>
    <h3>Evaluating template expressions </h3>
    <h4>Simple evaluation (to a string):</h4>
    <!-- "The sum of 1 + 1 is 2" -->
    <p>The sum of 1 + 1 is {{ 1 + 1 }}.</p>
    <h4>Evaluates using a method (also evaluates to a string):</h4>
    <!-- "The sum of 1 + 1 is not 4" -->
    <p>The sum of 1 + 1 is not {{ 1 + 1 + getVal() }}.</p>
  </div>
  <hr />
<h2>Expression Context</h2>
<div>
  <h4>Template context, template input variables (let customer):</h4>
  <ul>
    @for (customer of customers; track customer) {
      <li>{{ customer.name }}</li>
    }
  </ul>
</div>
```

### [Template statements](https://angular.dev/guide/templates/template-statements)

Las declaraciones de plantilla o **_'template statements'_** son métodos o propiedades que se pueden utilizar en el HTML para responder a los eventos del usuario:

```html
<button type="button" (click)="deleteHero()">Delete hero</button>
```

Cuando el usuario pulsa en el botón _'Delete hero'_, Angular llama al método `deleteHero()`.

Al igual que la interpolación de texto, los _'template statements'_ utilizan un lenguaje que parece JavaScript. Sin embargo, hay algunas diferencias con la interpolación de texto. Concretamente, los _'template statements'_ soportan el uso de la asignación mediante el signo igual `=` y el encadenado de expresiones con el uso de semicolons `;`:

```html
<button (click)="mostrarMensaje(); contarClicks()">Haz clic</button>
<!-- ... -->
<button (click)="contador = contador + 1; showMessage('Contador:', contador)">Incrementar Contador</button>
```

```typescript
@Component({
  selector: 'app-root',
  standalone: true,
  imports: [],
  templateUrl: './app.component.html',
  styleUrl: './app.component.css'
})
export class AppComponent {
  title = "my-app";
  contador = 0;

  showMessage(message: string, contador: number) {
    console.log(message, contador);
  }
}
```

Las declaraciones tienen un **contexto**: una parte particular de la aplicación a la que pertenece la declaración.

El contexto de la declaración también puede hacer referencia a propiedades del propio contexto de la plantilla. En el siguiente ejemplo, el método de manejo de eventos del componente, `onSave()` toma el objeto `$event` de la plantilla como argumento:

```html
<button type="button" (click)="onSave($event)">Save</button>
```

### [Property binding](https://angular.dev/guide/templates/property-binding)

La vinculación de propiedades o **_'property binding'_** en Angular permite establecer valores para las propiedades de elementos o directivas HTML.

Este _'property binding'_ mueve el valor en una dirección, desde la propiedad de un **componente** a la propiedad del elemento de destino en el **HTML**.

```typescript
@Component({
  ...
})
export class ExampleBindingComponent {
  itemImageUrl = '../assets/phone.svg';
}
```

Para vincular la propiedad, se encierra el nombre de la propiedad entre corchetes `[]`. Si no se encierra entre corchetes, Angular interpreta la cadena de forma literal.

```html
<img alt="item" [src]="itemImageUrl">
```

Para **desactivar** un botón por ejemplo, se puede vincular la propiedad `disabled` del DOM con un booleano en la clase:

```typescript
@Component({
  ...
})
export class ExampleBindingComponent {
  isUnchanged = true;
}
```

```html
<!-- Bind button disabled state to `isUnchanged` property -->
<button type="button" [disabled]="isUnchanged">Disabled Button</button>
```

A menudo se puede elegir entre interpolación o _'property binding'_. Los siguientes ejemplos son equivalentes:

```html
<p><img src="{{itemImageUrl}}"> is the <i>interpolated</i> image.</p>
<p><img [src]="itemImageUrl"> is the <i>property bound</i> image.</p>

<p><span>"{{interpolationTitle}}" is the <i>interpolated</i> title.</span></p>
<p>"<span [innerHTML]="propertyTitle"></span>" is the <i>property bound</i> title.</p>
```

### [Attribute binding](https://angular.dev/guide/templates/attribute-binding)

La vinculación de atributos o _'attribute binding'_ en Angular permite establecer valores para los atributos directamente.

La sintaxis de vinculación de atributos se parece a la vinculación de propiedades, pero en lugar de una propiedad de elemento entre corchetes, se antepone el nombre del atributo con el prefijo `attr`, seguido de un punto. Luego, se establece el valor del atributo con una expresión que se resuelve en una cadena:

```html
<p [attr.attribute-you-are-targeting]="expression"></p>
```

NOTA: cuando la expresión se resuelve con un `null` o un `undefined`, Angular elimina el atributo.

Uno de los usos más frecuentes es establecer atributos ['ARIA'](https://developer.mozilla.org/es/docs/Web/Accessibility/ARIA).

```html
<!-- create and set an aria attribute for assistive technology -->
<button type="button" [attr.aria-label]="actionName">{{ actionName }} with Aria</button>
```

Otro uso podría ser establecer el atributo `colspan` de una tabla HTML, lo que permitiría ajustar de forma dinámica una tablas:

```html
<!--  expression calculates colspan=2 -->
<tr><td [attr.colspan]="1 + 1">One-Two</td></tr>
```

### [Class and style binding](https://angular.dev/guide/templates/class-binding)

La vinculación de clases y estilos permite agregar y eliminar nombres de clases CSS del atributo de clase de un elemento o establecer estilos dinámicamente.

#### Binding to a single CSS class

Para realizar la vinculación con una **única clase CSS** se utiliza la forma `[class.classname]="expression"` siendo `expression` una expresión que se evalúa como `true` o `false` para indicar si se aplica o no la clase CSS.

La expresión también puede ser una propiedad que se evalúe a `true` o `false`:

```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-other-component',
  standalone: true,
  imports: [],
  template: `
    <p [class.background]="mark" [class.larger]="true">
      other-component works!
    </p>
  `,
  styles: `
    .background {
      background-color: yellow;
    }
    .larger {
      font-size: 2em;
    }
  `
})
export class OtherComponentComponent {
  mark: boolean = true;
}
```

#### Binding to multiple CSS clasess

Para vincular **más de una clase CSS** se utiliza la forma `[class]="classExpression"` donde `classExpression` puede ser:

- Una cadena de nombres de clases delimitada por espacios como por ejemplo `"my-class-1 my-class-2 my-class-3"`.

- Un objeto con nombres de clases como claves y expresiones verdaderas o falsas como valores.

- Un array de nombres de clase, como por ejemplo `['my-class-1', 'my-class-2']`

```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-other-component',
  standalone: true,
  imports: [],
  template: `
    <p [class]="['background', 'larger']">
      other-component works!
    </p>
  `,
  styles: `
    .background {
      background-color: green;
    }
    .larger {
      font-size: 2em;
    }
  `
})
export class OtherComponentComponent {}
```

#### Binding to a single style

Para vincular un **único estilo CSS**, se utiliza la forma `[style.styleName]="expression"`. Según el estilo, la expresión será una cadena o numérico, como por ejemplo para indicar un '%' o un tamaño en 'em'.

```typescript
import {Component} from '@angular/core';
@Component({
  standalone: true,
  selector: 'app-nav-bar',
  template: `
    <a [style.text-decoration]="activeLinkStyle">Home Page</a>
    <a [style.text-decoration]="linkStyle">Login</a>
  `,
})
export class NavBarComponent {
  linkStyle = 'underline';
  activeLinkStyle = 'overline';
  /* . . . */
}
```

#### Binding to multiple styles

Para vincular **múltiples estilos**, se utiliza la forma `[style]="styleExpression"`, donde `styleExpression` será:

- Una lista de cadenas que corresponden a los estilos, como por ejemplo `"width: 100px; height: 100px; background-color: cornflowerblue;"`.

- Un objeto con el nombre del estilo como clave y el valor del estilo como valor, como por ejemplo `{width: '100px', height: '100px', backgroundColor: 'cornflowerblue'}`.

```typescript
import {Component} from '@angular/core';
@Component({
  standalone: true,
  selector: 'app-nav-bar',
  template: ` <nav [style]="navStyle">
    <a [style.text-decoration]="activeLinkStyle">Home Page</a>
    <a [style.text-decoration]="linkStyle">Login</a>
  </nav>`,
})
export class NavBarComponent {
  navStyle = 'font-size: 1.2rem; color: cornflowerblue;';
  linkStyle = 'underline';
  activeLinkStyle = 'overline';
  /* . . . */
}
```

### [Event binding](https://angular.dev/guide/templates/event-binding)

La vinculación de eventos o **_'event binding'_** permite escuchar y responder a las acciones del usuario, como pulsaciones de teclas, movimientos del mouse, clics y toques.

Para vincularse a un evento, se utiliza la sintaxis de vinculación de eventos Angular:

```html
<button (click)="onSave()">Save</button>
```

La vinculación de eventos "escucha" los eventos de 'click' en el botón e invoca el método `onSave()` del componente cuando este evento se produce.

También se pueden realizar vinculaciones de eventos de teclado usando la sintaxis de Angular:

```html
<input (keydown.shift.t)="onKeydown($event)" />
```

Los campos `key` y `code` son una parte nativa del objeto de evento del teclado del navegador.

### [Two-way binding](https://angular.dev/guide/templates/two-way-binding)

El enlace bidireccional o **_'two-way binding'_** brinda a los componentes de una aplicación una forma de compartir datos. Se utiliza el enlace bidireccional para escuchar eventos y actualizar valores simultáneamente entre los componentes principal y secundario.

Este tipo de vinculación combina el [_'property binding'_](#property-binding) con el [_'event binding'_](#event-binding).

Por tanto la sintaxis del _'two-way binding'_ es una mezcla de ambas sintaxis:

```html
<app-sizer [(size)]="fontSizePx"></app-sizer>
```

En los formularios, se utiliza la directiva `ngModel`.

### [Control flow](https://angular.dev/guide/templates/control-flow)

Las plantillas en Angular admiten bloques de flujo de control que le permiten mostrar, ocultar y repetir elementos condicionalmente.

Esta característica se introdujo en Angular en la **v.17** como experimental y en la **v.18** se convirtió en estable. En versiones previas se utilizan directivas estructurales como **NgIf**, **NgFor** o **NgSwitch**.

#### Bloques condicionales

El bloque condicional con `@if` muestra el contenido cuando la expresión de condición es verdadera:

```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-jupiter',
  standalone: true,
  imports: [],
  template: `
    @if (showSection) {
      <p>jupiter works!</p>
    }
  `,
  styles: ``
})
export class JupiterComponent {
  showSection = true;
}
```

El bloque `@if` puede tener uno o más bloques `@else` asociados. Inmediatamente después de un bloque `@if`, puede opcionalmente especificar cualquier número de bloques `@else if` y un bloque `@else`:

```typescript
@if (a > b) {
  {{a}} is greater than {{b}}
} @else if (b > a) {
  {{a}} is less than {{b}}
} @else {
  {{a}} is equal to {{b}}
}
```

El nuevo condicional @if incorporado admite la referencia de resultados de expresiones para mantener una solución para patrones de codificación comunes:

```typescript
// El resultado del pipe 
@if (users$ | async; as users) {
  {{ users.length }}
}
```

En el ejemplo, el resultado del pipe `users$ | async;` se asigna a la variable _'users'_, un patrón común en la evaluación del patrón observable.

#### Bloques en bucle

La anotación `@for` renderiza repetidamente el contenido de un bloque para cada elemento en una colección. La colección puede ser representada como cualquier iterable de JavaScript, pero existen ventajas de rendimiento al usar un Array regular. Un bucle básico `@for` se ve así:

```typescript
@for (item of items; track item.id) {
  {{ item.name }}
}
```

Utilizar `track` de manera efectiva puede mejorar significativamente el rendimiento de tu aplicación, especialmente en bucles que iteran sobre colecciones de datos.

Para colecciones que no sufren modificaciones (es decir, ningún elemento se mueve, añade o elimina), usar `track $index` es una estrategia eficiente. Esto aprovecha el índice de posición en el array como clave de seguimiento.

Sin embargo, para colecciones con datos mutables o cambios frecuentes, es mejor seleccionar una propiedad que identifique de manera única cada elemento y utilizarla como expresión de seguimiento, como por ejemplo `item.id`.

Dentro de los contenidos `@for`, siempre están disponibles varias variables implícitas:

- **$count**: número de elementos de una colección iterados

- **$index**: índice de la fila actual

- **$first**: si la fila actual es la primera fila

- **$last**: si la fila actual es la última fila

- **$even**: si el índice de fila actual es par

- **$odd**: si el índice de la fila actual es impar

```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-jupiter',
  standalone: true,
  imports: [],
  template: `
    @for (item of numeros; track $index) {
      @if ($odd) {
        <p>{{item}}</p>
      }
    }
  `,
  styles: ``
})
export class JupiterComponent {
  numeros = [1, 2, 3, 4, 5];
}
```

En caso de bloques `@for` anidados, el uso de estas variables puede provocar colisiones. Para ello se puede usar un **alias** con `let`:

```typescript
@for (item of items; track item.id; let idx = $index, e = $even) {
Item #{{ idx }}: {{ item.name }}
}
```

Opcionalmente, puede incluir una sección `@empty` inmediatamente después del contenido del bloque `@for`. El contenido de este bloque se mostrará cuando no hay elementos disponibles:

```html
@for (item of items; track item.name) {
  <li> {{ item.name }}</li>
} @empty {
  <li> There are no items.</li>
}
```

#### Bloques de selección

La sintaxis de `@switch` es muy similar a `@if` y está inspirada en la declaración de `switch` de JavaScript:

```typescript
@switch (condition) {
  @case (caseA) {
    Case A.
  }
  @case (caseB) {
    Case B.
  }
  @default {
    Default case.
  }
}
```

El valor de la expresión condicional se compara con la expresión de caso utilizando el operador '==='.

`@switch` no tiene falla, por lo que no necesita un equivalente a una declaración de `break` o `return`.

El bloque `@default` es opcional y puede ser omitido. Si ningún bloque `@case` coincide con la expresión evaluada y no hay un bloque `@default`, no se mostrará nada.

### [Pipes](https://angular.dev/guide/pipes)

Las **_'pipes'_** se utilizan para transformar cadenas, importes de moneda, fechas y otros datos para su visualización.

Las _'pipes'_ son funciones simples de usar en plantillas que aceptan un valor de entrada y devuelven un valor transformado. Son útiles porque se pueden utilizar en toda la aplicación, declarando cada _'pipe'_ sólo una vez.

Angular provee de una serie de _'pipes'_ para transformaciones típicas:

- [DatePipe](https://angular.dev/api/common/DatePipe)

- [UpperCasePipe](https://angular.dev/api/common/UpperCasePipe)

- [LowerCasePipe](https://angular.dev/api/common/LowerCasePipe)

- [CurrencyPipe](https://angular.dev/api/common/CurrencyPipe)

- [DecimalPipe](https://angular.dev/api/common/DecimalPipe)

- [PercentPipe](https://angular.dev/api/common/PercentPipe)

- [AsyncPipe](https://angular.dev/api/common/AsyncPipe)

- [JsonPipe](https://angular.dev/api/common/JsonPipe)

Para usar una _'pipe'_ hay que usar el operador `|` tal y como se muestra en el ejemplo. Además, se tiene que importar del paquete `@angular/common`:

```typescript
import { Component } from '@angular/core';
import { DatePipe } from '@angular/common';
@Component({
  standalone: true,
  template: `
    <p>The hero's birthday is {{ birthday | date }}</p>
  `,
  imports: [DatePipe],
})
export class AppComponent {
  birthday = new Date();
}
```

Las _'pipes'_ pueden tomar parámetros adicionales que permitan configurar la transformación. Estos parámetros pueden ser **obligatorios** u **opcionales**:

```html
<p>The hero's birthday is in {{ birthday | date:'yyyy' }}</p>
```

Algunas _'pipes'_ pueden tomar múltiples parámetros. Para ello se utiliza el operador `:`:

```html
<p>The current time is: {{ currentTime | date:'hh:mm':'UTC' }}</p>
```

Por último, las _'pipes'_ se pueden **encadenar** de forma que la salida de la _'pipe'_ anterior es la entrada de la siguiente:

```html
<p>The hero's birthday is {{ birthday | date }}</p>
<p>The hero's birthday is in {{ birthday | date:'yyyy' | uppercase }}</p>
```

## [Directives](https://angular.dev/guide/directives)

Las directivas son clases que agregan comportamiento adicional a los elementos de una aplicación Angular.

Angular dispone de tres tipos de directivas:

- **_Components_**: los componentes en Angular son una forma especial de directiva con una plantilla asociada.

- **_Attributes directives_**: cambiar la apariencia o el comportamiento de un elemento, componente u otra directiva.

- **_Structural directives_**: cambiar el diseño DOM agregando y eliminando elementos DOM.

### [Built-in attribute directives](https://angular.dev/guide/directives#built-in-attribute-directives)

Las directivas de atributos más comunes son **NgClass**, **NgStyle** y **NgModel**.

#### [NgClass](https://angular.dev/guide/directives#adding-and-removing-classes-with-ngclass)

Con `NgClass` se pueden añadir o eliminar **múltiples clases CSS** de forma simultánea. Para añadir o eliminar una única clase CSS es mejor utilizar el _'class binding'_.

En el siguiente ejemplo se muestra el uso de `NgClass` y un _'class binding'_ para una única clase CSS:

```typescript
import { Component } from '@angular/core';
import { NgClass } from '@angular/common';

@Component({
  selector: 'app-moon',
  standalone: true,
  imports: [NgClass],
  template: `
    <p [ngClass]="isLarger ? 'larger' : 'shorter'" [class.background]="withBackground">
      moon works!
    </p>
  `,
  styles: `
    .background {
      background-color: green;
    }
    .larger {
      font-size: 2em;
    }
    .shorter {
      font-size: 1em;
    }
  `
})
export class MoonComponent {
  withBackground = true;
  isLarger = true;
}
```

#### [NgStyle](https://angular.dev/guide/directives#setting-inline-styles-with-ngstyle)

Con `NgStyle` se pueden aplicar estilos inline a un elemento:

```typescript
import { Component } from '@angular/core';
import { NgStyle } from '@angular/common';

@Component({
  selector: 'app-mars',
  standalone: true,
  imports: [NgStyle],
  template: `
    <p [ngStyle]="currentStyles">
      mars works!
    </p>
  `,
  styles: ``
})
export class MarsComponent {
  canSave = true;
  isUnchanged = true;
  isSpecial = true;

  currentStyles = {
    'font-style': this.canSave ? 'italic' : 'normal',
    'font-weight': !this.isUnchanged ? 'bold' : 'normal',
    'font-size': this.isSpecial ? '24px' : '12px',
    'background-color': 'red'
  };
}
```

#### [NgModel](https://angular.dev/guide/directives#displaying-and-updating-properties-with-ngmodel)

Utilice la directiva `NgModel` para mostrar una propiedad de datos y actualizar esa propiedad cuando el usuario realice cambios:

```typescript
import { Component } from '@angular/core';
import { FormsModule } from '@angular/forms';

@Component({
  selector: 'app-venus',
  standalone: true,
  imports: [FormsModule],
  template: `
    <input [(ngModel)]="nombre" placeholder="Ingrese su nombre">
    <p>Tu nombre ingresado es: {{ nombre }}</p>
  `,
  styles: ``
})
export class VenusComponent {
  nombre: string = ''; // Variable para almacenar el nombre ingresado
}
```

Para personalizar su configuración, escriba el formulario ampliado, que separa el enlace de propiedad y evento. Utilice el enlace de propiedad para establecer el enlace de propiedad y evento para responder a los cambios:

```html
<input [ngModel]="currentItem.name" (ngModelChange)="setUppercaseName($event)" id="example-uppercase">
```

### [Structural directives](https://angular.dev/guide/directives#built-in-structural-directives)

Las directivas estructurales son responsables del diseño HTML. Dan forma o remodelan la estructura del DOM, generalmente agregando, eliminando y manipulando los elementos host a los que están adjuntos.

#### [Using NgIf](https://angular.dev/guide/directives#using-ngif)

Para agregar o eliminar un elemento, vincule `*ngIf` a una expresión de condición, es decir, que se evalúe a verdadero o falso:

```typescript
import { Component } from '@angular/core';
import { NgIf } from '@angular/common';

@Component({
  selector: 'app-ejemplo-ngif',
  template: `
    <div *ngIf="mostrarElemento">
      Este elemento se muestra si mostrarElemento es true.
    </div>
    <button (click)="toggleElemento()">Toggle Elemento</button>
  `
})
export class EjemploNgIfComponent {
  mostrarElemento: boolean = true;

  toggleElemento() {
    this.mostrarElemento = !this.mostrarElemento;
  }
}
```

Si se aplica a un componente, cuando la expresión es verdadera, Angular añade el componente al DOM. Sin embargo, cuando es falsa, suprime el componente del DOM:

```html
<app-item-detail *ngIf="isActive" [item]="item"></app-item-detail>
```

De forma predeterminada, la directiva `NgIf` impide la visualización de un elemento vinculado a un valor nulo.

### [Using NgFor](https://angular.dev/guide/directives#using-ngfor)

la directiva `*ngFor` en Angular se utiliza para iterar sobre elementos en una colección, como un array o una lista, y renderizar dinámicamente elementos HTML basados en cada elemento de la colección:

```typescript
import { Component } from '@angular/core';
import { NgFor } from '@angular/common';

@Component({
  selector: 'app-jupiter',
  standalone: true,
  imports: [NgFor],
  template: `
    <ul>
      <li *ngFor="let num of numeros; let i = index">
        Índice: {{ i + 1 }} - Número: {{ num }}
      </li>
    </ul>
  `,
  styles: ``
})
export class JupiterComponent {
  numeros = [2, 4, 6, 8, 10, 12];
}
```

Para repetir un elemento componente, aplique `*ngFor` al selector:

```html
<app-item-detail *ngFor="let item of items" [item]="item"></app-item-detail>
```

### [Using NgSwitch](https://angular.dev/guide/directives#using-ngswitch)

La directiva `NgSwitch` muestra un elemento entre varios elementos posibles, según una condición de cambio. Angular coloca solo el elemento seleccionado en el DOM.

Esta directiva se compone de tres directivas que deberán ser importadas: `NgSwitch`, `NgSwitchCase` and `NgSwitchDefault`.

```html
<div [ngSwitch]="currentItem.feature">
  <app-stout-item    *ngSwitchCase="'stout'"    [item]="currentItem"></app-stout-item>
  <app-device-item   *ngSwitchCase="'slim'"     [item]="currentItem"></app-device-item>
  <app-lost-item     *ngSwitchCase="'vintage'"  [item]="currentItem"></app-lost-item>
  <app-best-item     *ngSwitchCase="'bright'"   [item]="currentItem"></app-best-item>
...
  <app-unknown-item  *ngSwitchDefault           [item]="currentItem"></app-unknown-item>
</div>
```

### [Hosting a directive without a DOM element](https://angular.dev/guide/directives#hosting-a-directive-without-a-dom-element)

La directiva de Angular `<ng-container>` es un elemento de agrupación que no interfiere con los estilos o el diseño porque Angular no lo coloca en el DOM.

Es decir, `<ng-container>` es útil cuando se necesita aplicar directivas estructurales (`*ngIf`, `*ngFor`) a múltiples elementos sin introducir un nodo extra en el DOM final.

No se renderiza en el DOM final, por lo que es una herramienta poderosa para controlar la estructura del HTML sin afectar el renderizado.

Por ejemplo, con la directiva `ngIf`. Se condiciona la renderización del mensaje sin agregar elementos HTML adicionales al DOM final según la propiedad booleana:

```html
<div>
  <ng-container *ngIf="showMessage">
    <p>This is a conditional message.</p>
  </ng-container>
</div>
```

Otro ejemplo con la directiva `*ngFor`:

```html
<ul>
  <ng-container *ngFor="let num of numbers">
    <li *ngIf="num % 2 === 0">
      {{ num }}
    </li>
  </ng-container>
</ul>
```

## [Dependency injection in Angular](https://angular.dev/guide/di)

Cuando se desarrolla una parte más pequeña del sistema, como un módulo o una clase, puede ser necesario utilizar funcionalidades de otras clases. Por ejemplo, es posible que se necesite un servicio HTTP para realizar llamadas al backend. La **inyección de dependencias**, o DI, es un patrón de diseño y un mecanismo para crear y proporcionar algunas partes de una aplicación a otras partes que las necesiten. Angular soporta este patrón de diseño y se puede utilizar en las aplicaciones para aumentar la flexibilidad y la modularidad.

En Angular, las dependencias suelen ser **servicios**, aunque también pueden ser valores como cadenas o funciones. Un inyector para una aplicación (creado automáticamente durante el arranque) instancia las dependencias cuando son necesarias, utilizando un proveedor configurado del servicio o valor.

### [Understanding dependency injection](https://angular.dev/guide/di/dependency-injection)

La inyección de dependencias, o DI, es uno de los conceptos fundamentales en Angular. La DI está integrada en el marco de Angular y permite a las clases con decoradores de Angular, como **Componentes**, **Directivas**, **Pipes** e **Inyectables**, configurar las dependencias que necesitan.

En el sistema de DI existen dos roles principales: el **consumidor** de dependencias y el **proveedor** de dependencias.

TODO

---

## Referencias

- <https://angular.dev>
- <https://www.typescriptlang.org>
- <https://www.youtube.com/@Angular>

## Licencia

[![Licencia de Creative Commons](https://i.creativecommons.org/l/by-sa/4.0/80x15.png)](http://creativecommons.org/licenses/by-sa/4.0/)
Esta obra está bajo una [licencia de Creative Commons Reconocimiento-Compartir Igual 4.0 Internacional](http://creativecommons.org/licenses/by-sa/4.0/).
