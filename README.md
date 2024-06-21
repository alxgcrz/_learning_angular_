# Angular

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

## Componentes

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

### Importar y usar componentes

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

[Más información](https://angular.dev/guide/components/importing)

### Selectores

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

### Styling

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

[Más información](https://angular.dev/guide/components/styling)

### Accepting data with input properties

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

#### Customizing inputs

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

#### Type checking

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

#### Built-in transformations

Angular incluye dos funciones de transformación integradas para los dos escenarios más comunes: convertir valores a booleanos y números:

```typescript
import {Component, Input, booleanAttribute, numberAttribute} from '@angular/core';
@Component({...})
export class CustomSlider {
  @Input({transform: booleanAttribute}) disabled = false;
  @Input({transform: numberAttribute}) number = 0;
}
```

#### Inputs aliases

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

[Más información](https://angular.dev/guide/components/inputs)

---

## Enlaces de interés

- <https://angular.dev/>
- <https://www.typescriptlang.org/>
- <https://www.youtube.com/@Angular>

## Licencia

[![Licencia de Creative Commons](https://i.creativecommons.org/l/by-sa/4.0/80x15.png)](http://creativecommons.org/licenses/by-sa/4.0/)
Esta obra está bajo una [licencia de Creative Commons Reconocimiento-Compartir Igual 4.0 Internacional](http://creativecommons.org/licenses/by-sa/4.0/).
