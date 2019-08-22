# Angular

Es una plataforma y un framework para crear aplicaciones cliente en HTML y TypeScript. Angular está escrito en TypeScript. Implementa funciones básicas y opcionales como un conjunto de librerías TypeScript que se importan en las aplicaciones. Angular aprovecha la tecnología de los componentes web o _'web components'_ y el _'Shadow DOM'_ para apoyar el desarrollo impulsado por componentes.

Los elementos más básicos de construcción de una aplicación Angular son los *NgModules*, que proporcionan un contexto de compilación para los componentes. Los *NgModules* agrupan el código relacionado en conjuntos funcionales; una aplicación Angular se define por un conjunto de *NgModules*. Una aplicación siempre tiene al menos un módulo raíz que permite el bootstrapping, y normalmente tiene muchos más módulos de características.

Los componentes definen **vistas**, que son conjuntos de elementos de pantalla entre los que Angular puede elegir y modificar según la lógica y los datos de su programa.

Los componentes utilizan **servicios** que proporcionan funciones específicas que no están directamente relacionadas con las vistas. Los proveedores de servicios pueden ser inyectados en los componentes como dependencias, haciendo que su código sea modular, reutilizable y eficiente.

Tanto los componentes como los servicios son simplemente clases, con decoradores que marcan su tipo y proporcionan metadatos que indican a Angular cómo utilizarlos.

Los metadatos para una clase de componente la asocian con una plantilla o _'template'_ que define una vista. Una plantilla combina HTML ordinario con directivas de Angular y _'binding markup'_ que permiten a Angular modificar el HTML antes de renderizarlo para mostrarlo.

Los metadatos para una clase de servicio proporcionan la información que Angular necesita para ponerla a disposición de los componentes a través de la inyección de dependencia (DI).

Los componentes de una aplicación suelen definir muchas vistas, ordenadas jerárquicamente. Angular proporciona el servicio de enrutado para ayudarle a definir rutas de navegación entre las vistas. El enrutador proporciona sofisticadas capacidades de navegación dentro del navegador.

Más información:

* <https://angular.io/docs>
* <https://angular.io/guide/architecture>
* <https://academia-binaria.com/cursos/angular-basic>

[StackBlitz](https://medium.com/stackblitz-blog/stackblitz-online-vs-code-ide-for-angular-react-7d09348497f4)
[StackBlitz — Online IDE for Angular & React powered by Visual Studio Code](https://stackblitz.com)

## Primeros pasos

<https://angular.io/guide/setup-local>
<https://angular.io/cli>
<https://academia-binaria.com/hola-angular-cli/>

### Prerequisitos

Angular requiere Node.js versión 10.0.9 o superior. Podemos instalar Node.js descargándolo de su [página oficial](https://nodejs.org/).

Cuando tengamos instalado _node.js_ o si ya lo teníamos instalado podemos comprobar si está correctamente configurado escribiendo en el terminal `node -v`. Si está todo correcto nos mostrará la versión de _node.js_.

Cuando se instala _node.js_ también se instala _NPM_. Para comprobar si está correctamente instalado escribimos en el terminal `npm -v` lo que nos mostrará la versión instalada.

Para desarrollar en Angular podemos usar simplemente Javascript, pero se recomienda usar TypeScript, dado que Angular está desarrollado con TypeScript y todos los ejemplos y código que se encuentra en la web estará escrito en TypeScript. Para instalar Typescript se utiliza también la herramienta *npm*. Abrimos un terminal/consola y ejecutamos `npm install -g typescript`.

```bash
//Summary
node -v
npm -v
npm install -g typescript
tsc --version
```

### Instalación de _'Angular CLI'_

_'Angular CLI'_ o simplemente _CLI_ es la herramienta de línea de comandos estándar para crear, depurar y publicar aplicaciones Angular.

Para instalar 'Angular CLI' abrimos un terminal/consola y ejecutamos el comando `npm install -g @angular/cli` lo que instala 'Angular CLI' de forma global lo que nos permitirá usar la herramienta desde cualquier directorio.

La sintaxis para instalar Angular (@angular/paquete) es una nueva característica de *npm* llamada **'scoped packages'**. Permite agrupar los paquetes en una misma carpeta.

Comprobamos la versión instalada ejecutando en un terminal/consola `ng version`. La ayuda está disponible tanto de modo general (`ng help`) como para cada comando de la herramiento (`ng new --help` o por ejemplo `ng generate --help`).

```terminal
npm install -g @angular/cli   // Instalar Angular CLI
ng version
ng help                       // Ver ayuda general
ng generate --help            // Ayuda de un comando en concreto
```

### Crear un _'workspace'_ y una aplicación inicial

Las aplicaciones Angular se desarrollan en el contexto de una espacio de trabajo o ['workspace'](https://angular.io/guide/glossary#workspace). Un espacio de trabajo puede contener múltiples aplicaciones y bibliotecas. La aplicación inicial creada con el comando `ng new` está en el nivel top del espacio de trabajo. Cuando generamos aplicaciones o librerías adicionales, éstas se crean dentro de la subcarpeta `projects/`.

Para crear un nuevo espacio de trabajo y una aplicación inicial dentro de este nuevo espacio de trabajo, abrimos un terminal y escribimos:

```terminal
ng new my-app  // Cambiando 'my-app' por el nombre de nuestra nueva aplicación
```

El comando `ng new` nos solicitará información para configurar la aplicación inicial. Lo más habitual es usar la configuración que viene por defecto. Para más información podemos consultar la documentación del comando [`ng new`](https://angular.io/cli/new).

'Angular CLI' instalará todas las librerías y dependencias necesarias, lo que se podrá demorar varios minutos.

Finalmente tendremos una aplicación inicial completamente funcional y las configuraciones necesarias para su depuración, pruebas y ejecución.

Por defecto la aplicación se crea con el prefijo `app` que se usará en todos los componentes. Puede personalizarse usando el modificador `--prefix`, como por ejmplo `ng new --prefix sigma`.

### Ejecutar la aplicación

'Angular CLI' incluye un servidor, para que pueda crear y servir su aplicación fácilmente a nivel local.

Entramos en el directorio de la apliación y lanzamos el servidor con `ng serve --open`. Con el parámetro `--open` le indicamos que abra el navegador y cargue la página <http://localhost:4200>:

```terminal
cd my-app
ng serve --open // Abre el navegador directamente
```

El comando `ng serve` inicia el servidor, observa el código fuente, reconstruye automáticamente la aplicación cuando detecta algún cambio en el código y recarga la página en el navegador.

### Estructura de una aplicación Angular

<https://angular.io/guide/file-structure>

Cuando ejecutamos el comando `ng new` se instalan las librerías y dependencias necesarias en el nuevo _workspace_ además del esqueleto funcional de una aplicación dentro de la carpeta `src/`. Esta aplicación se considera la aplicación principal o aplicación raíz. El directorio raíz del espacio de trabajo contiene todos los ficheros de configuración, etc.. necesarios para construir y servir la aplicación Angular.

La aplicación inicial creada es la apliación por defecto para todos los comandos lanzados a través de la CLI.

Para un espacio de trabajo que contendrá una sóla aplicación, la subcarpeta `src/` del espacio de trabajo contendrá los ficheros de código (lógica de la aplicación, datos y assets) de la aplicación raíz. Para espacios de trabajo de tipo _'multi-project'_ cada proyecto estará en su propia carpeta dentro de la carpeta `projects/`.

#### Ficheros de configuración

<https://angular.io/guide/file-structure#workspace-configuration-files>

Todos los proyectos dentro del mismo espacio de trabajo o _'workspace'_ comparten los ficheros de configuración que están en la raíz del espacio de trabajo. Estos ficheros de configuración tienen ámbito del espacio de trabajo y por tanto su configuración afecta a todos los proyectos.

Los archivos de configuración que están en la raíz del espacio de trabajo son los ficheros de configuración de la aplicación raíz. Para un espacio de trabajo de múltiples proyectos, los archivos de configuración específicos de cada proyecto estarán en la carpeta raíz de cada proyecto, dentro de `projects/project-name`.

El fichero `'package.json'` es el fichero estándar de *npm* donde se almacenan las dependencias de terceros que se utilizará para todos los proyectos del espacio de trabajo. Contiene las librerías que necesita la aplicación para ejecutarse tanto en desarrollo como producción.

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

El fichero `angular.json` contiene los valores predeterminados de configuración de la CLI para todos los proyectos en el área de trabajo, incluidas las opciones de configuración para compilar, servir y probar las herramientas que utiliza la CLI

**Los cambios en los ficheros de configuración no se recargan automáticamente**. Hay que parar la servidor y volver a lanzarlo para que se carguen.

#### Carpetas y ficheros de la aplicación

<https://angular.io/guide/file-structure#application-project-files>

Dentro de la carpeta `/src` tenemos:

* La carpeta `app/` contiene los componentes Angular que componen la aplicación.

* La carpeta `environments/` contiene dos ficheros, y puede contener más, para cada entorno de distribución necesario. En código siempre importaremos el fichero base, pero durante la compilación el CLI lo sustituirá por el adecuado como por ejemplo `title = environment.appName + 'hello world ;-)';`

* La carpeta `assets/` contiene imágenes y otros archivos de activos que se copiarán tal cual cuando cree su aplicación.

* `index.html`: La página HTML principal que se sirve cuando alguien visita el sitio. La CLI agrega automáticamente todos los archivos JavaScript y CSS al crear su aplicación, por lo que normalmente no necesita agregar ninguna etiqueta `<script>` o `<link>` manualmente.

* `main.ts`: El principal punto de entrada para su aplicación. Compila la aplicación con el compilador JIT y arranca el módulo raíz de la aplicación (`AppModule`) para ejecutarse en el navegador. También puede usar el compilador AOT sin cambiar ningún código agregando el indicador --aot a los comandos de compilación y servicio de la CLI.

Dentro tenemos la carpeta `/src/app/`:
  
* `app.module.ts`: Define el módulo raíz, llamado `AppModule`, que le dice a Angular cómo ensamblar la aplicación. Inicialmente declara solo el `AppComponent`. A medida que agregue más componentes a la aplicación, deberá declararlos aquí.

Una aplicación Angular es un árbol de componentes cuyo componente raíz es llamado `AppComponent`:

* `app.component.ts`: Define la lógica para el componente raíz de la aplicación. La vista asociada con este componente raíz se convierte en la raíz de la jerarquía de vistas a medida que agrega componentes y servicios a su aplicación.

* `app.component.html`: Define la plantilla HTML asociada con el componente raíz `AppComponent`

* `app.component.css`: Define la hoja de estilo CSS básica para el componente raíz `AppComponent`

## Arquitectura de una aplicación Angular

<https://angular.io/guide/architecture>
<https://academia-binaria.com/base-aplicacion-angular/>

### Introducción a los Módulos

<https://angular.io/guide/architecture-modules#introduction-to-modules>
<https://angular.io/guide/ngmodules>

Las aplicaciones en Angular son modulares y Angular tiene su propio sistema de módulos llamado *'NgModules'*.

Los módulos son **contenedores para almacenar los componentes y servicios** de una aplicación. En Angular toda aplicación se puede ver como un árbol de módulos jerárquico y por tanto como mínimo tendrá un módulo raíz, que por convención se llama **'AppModule'** y reside en el fichero `app.module.ts`. A partir de ese módulo raíz se enlazan el resto de módulos, si los hubiera.

Los módulos pueden exportar funcionalidad que será importada y utilizada por otros módulos.

Un _'NgModule'_ se define como una clase TypeScript decorada con la función decoradora `@NgModule()` que recibe un objeto con metadatos como único argumento. En las propiedades de ese objeto es donde se [configura el módulo.](https://angular.io/guide/bootstrapping)

Este es un ejemplo de un módulo raíz `AppModule` que reside en el fichero `'app.module.ts'`:

```typescript
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { AppComponent } from './app.component';

@NgModule({
  declarations: [ AppComponent ], // Componentes, directivos y/o pipes que pertenecen al módulo
  imports: [ BrowserModule ],     // Módulos que se importan para poder utilizar su funcionalidad
  providers: [],                  // Los proveedores son creadores de servicios
  bootstrap: [AppComponent]       // El componente raíz principal que inicia la aplicación
})
export class AppModule { }
```

Para crear un módulo abrimos un terminal/consola y ejecutamos el comando:

```terminal
ng generate module login // Substituir 'login' por el nombre del módulo
```

Esto creará el fichero `'login/login.module.ts'`. Para utilizar el nuevo módulo hay que añadirlo en la propiedad `imports:[]`, que es un array de punteros a otros módulos que está en el fichero `'app.module.ts'` que es el fichero del módulo raíz.

```typescript
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';

import { AppComponent } from './app.component';
import { LoginModule } from './login/login.module';

@NgModule({
  declarations: [ AppComponent ],
  imports: [ BrowserModule, LoginModule ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

El módulo raíz siempre tiene un **componente raíz** que se crea cuando se crea el módulo. Los módulos pueden tener más de un componente aunque sólo uno será el componente raíz. El componente raíz se indica en `bootstrap: [AppComponent]` de forma que cualquier componente con capacidad para actuar como [punto de entrada](https://angular.io/guide/entry-components) debe indicarse en esta propiedad.

### Introducción a los Componentes

<https://angular.io/guide/architecture-components>

**Los componentes son los bloques básicos** de construcción de las páginas web en Angular. Contienen una parte visual en HTML, que es una plantilla o _'template'_ (la parte visual) y una funcional en una clase en Typescript (el controlador). La clase interactúa con la plantilla a través de una API de propiedades y métodos.

Ambas partes, la plantilla y el controlador definen lo que es una **vista**. Un componente puede contener una jerarquía de vistas, lo que permite construir interfaces visuales complejas y modificar, crear, añadir o destruir determinadas partes según convenga. Además, no estamos limitados a un sólo módulo, de tal forma que una jerarquía de vistas puede mezclar vistas definidas en componentes que están en diferentes módulos.

La [sintaxis](https://angular.io/cli/generate#component) para crear nuevos componentes es:

```terminal
ng generate component <name>
```

El componente raíz que se genera en el módulo raíz es el `AppComponent`. Según la configuración del CLI este componente puede haber sido creado en un sólo fichero o en hasta cuatro:

* el controlador en `app.component.ts`
* la vista en `app.component.html`
* el estilo en `app.component.css`
* las pruebas unitarias en `app.component.spec.ts`

Angular crea, actualiza y destruye componentes a medida que el usuario se mueve a través de la aplicación. La aplicación puede realizar acciones en cada momento de este ciclo de vida a través de los ['lifecycle hooks'](https://angular.io/guide/lifecycle-hooks) como `ngOnInit()` al estilo de Android y los métodos `onCreate()`, `onStart()`, etc...

Los componentes, como el resto de artefactos en Angular, definen su lógica en **clases TypeScript decoradas** con una función específica. En este caso para que Angular sepa que es un componente la clase estará _'decorada'_ con la función `@Component()` que recibe un objeto de metadatos que define el componente. Al igual que en los módulos, este objeto contiene las propiedades con las que se configura el componente.

```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styles: []
})
export class AppComponent {}
```

Los metadatos de un componente le indican a Angular dónde obtener los bloques de construcción principales que necesita para crear y presentar el componente y su vista. En particular, asocia una plantilla con el componente, ya sea directamente con código en línea o por referencia. Juntos, el componente y su plantilla describen una vista.

**Los componentes definen nuevas etiquetas HTML** para ser usados dentro de otros componentes. Excepcionalmente, el componente raíz se utiliza en la página `'index.html'`. El nombre de la nueva etiqueta se conoce como *selector*. En el caso del componente raíz la propiedad `selector: "app-root"` permite el uso de este componente con esta invocación `<app-root></app-root>`. Otros componentes definirán sus etiquetas HTML dentro de la propiedad `selector` y Angular creará e insertará una instancia del componente donde encuentre esa etiqueta incluido dentro de otros componentes creando una jerarquía.

```html
// index.html
<body>
  <app-root></app-root>
</body>
```

La plantilla representa la parte visual del componente y le dice a Angular como renderizar el componente. De forma simplificada, o cuando tiene poco contenido, puede escribirse directamente en la propiedad `template` del objeto decorador. Pero es más frecuente encontrar la plantilla en su propio fichero html y referenciarlo como una ruta relativa en la propiedad `templateUrl`.

La propiedad `styles` y su gemela `stylesUrl` permiten asignar estilos CSS, SASS o LESS al componente. Estos estilos se incrustan durante la compilación en los nodos del DOM generado. Son exclusivos del componente y facilitan el diseño y maquetación granular de las aplicaciones.

En la clase del componente, que actua como controlador, nos encontraremos **la implementación de su funcionalidad**. Normalmente expondrá propiedades y métodos para ser consumidos e invocados de forma declarativa desde la vista.

Los componentes no deciden por sí mismos su visibilidad. Cuando un componente es generado se declara en un módulo contenedor en su propiedad `declares:[]`. Eso lo hace visible y utilizable por cualquier otro componente del mismo módulo. Para poder usarlo en otros módulos hay que exportarlo de forma explícita. Eso se hace en la propiedad `exports:[]` del módulo en el que se crea o indicarse con el flag `--export`.

Que un componente sea público es la primera condición para que se consuma fuera de su módulo. El siguiente paso es importarlo en la propiedad `imports:[]` del módulo. Como regla general, cuando en una plantilla se incruste otro componente, Angular lo buscará **dentro del propio módulo** en el que pretende usarse. Si no lo encuentra entonces lo buscará entre los componentes exportados por los módulos que hayan sido importados por el actual contenedor.

Los componentes privados suelen ser sencillos. A veces son creados para ser específicamente consumidos dentro de otros componentes. En esas situaciones interesa que sean privados y que generen poco ruido. Incluso, en casos extremadamente simples, si usamos el modificador `--flat` ni siquiera generan carpeta propia.

Cada módulo puede exportar sus propios componentes o los componentes de terceros, incluso un módulo completo, haciendo uso de la interesante **propiedad transitiva de los módulos**.

#### Sintaxis de las plantillas

Una plantilla contiene etiquetas HTML normales pero además contiene una [sintaxis de plantillas propia](https://angular.io/guide/template-syntax) qyue altera el HTML basado en la lógica de la aplicación, su estado y los datos del DOM.

La plantilla usan el _'data binding'_ para coordinar los datos de la aplicación con los datos del DOM, _'pipes'_ para transformar los datos antes de ser mostrados y _'directives'_ para aplicar la lógica de la aplicación a lo que se muestra.

##### Data binding

Angular admite el enlace de datos bidireccional o _'two-way data binding'_, un mecanismo para coordinar las partes de una plantilla con las partes de un componente. Para indicar a Angular como tiene que conectar ambas partes y la dirección de la conexión, se utiliza un marcado especial que tiene hasta 4 formas:

![Data binding](https://angular.io/generated/images/guide/architecture/databinding.png)

|                         |          Markup             |       Nombre          |
| :---------------------- | :-------------------------: | :-------------------: |
|  DOM <------- Component |          {{value}}          |  _'interpolation'_    |
|  DOM <------- Component |     [property] = "value"    |  _'property binding'_ |
|  DOM -------> Component |     (event) = "handler"     |  _'event binding'_    |
|  DOM <------> Component |  [(ng-model)] = "property"  |  _'two-way binding'_  |

```html
<li>{{hero.name}}</li>  <!-- Interpolation permite visualizar la propiedad 'hero.name' del componente en la etiqueta -->

<app-hero-detail [hero]="selectedHero"</app-hero-detail> <!-- Pasa el valor del 'selectedHero' del padre al componente hijo -->

<li (click)="selectedHero(hero)"></li> <!-- Llama al método 'selectedHero(hero)' cuando el usuario hace click sobre la etiqueta -->

<input [(ngModel)]="hero.name"> <!-- two-way binding -->
```

En _'two-way binding'_ un valor de propiedad de datos fluye al input desde el componente como con el enlace de propiedades o _'property binding'_. Los cambios del usuario también vuelven al componente, restableciendo la propiedad al último valor, como con el enlace de eventos o _'event binding'_. Por tanto es un enlace bidireccional que es la suma de ambos enlaces.

##### Pipes

Las _'pipes'_ le permiten declarar transformaciones de valor de visualización en su plantilla HTML. Una clase con el decorador `@Pipe` define una función que transforma los valores de entrada en valores de salida para mostrar en una vista.

Angular tiene definidas por defecto varias _'pipes'_ para trabajar con [fechas](https://angular.io/api/common/DatePipe) o [monedas](https://angular.io/api/common/CurrencyPipe). La lista completa se encuentra [aquí](https://angular.io/api?type=pipe).

Para especificar una transformación en HTML con las _'pipes'_ se utiliza el _'pipe operator (|)'_:

```html
<li>{{ interpolated value | pipe_name}}</li>
```

Las _'pipes'_ se pueden encadenar, enviando la salida de una tubería para que sea transformada por otra tubería. Una _'pipe'_ también puede tomar argumentos que controlan cómo realiza su transformación. Por ejemplo, puede pasar el formato deseado a la tubería de fecha:

```html
<!-- Default format: output 'Jun 15, 2015'-->
 <p>Today is {{today | date}}</p>

<!-- fullDate format: output 'Monday, June 15, 2015'-->
<p>The date is {{today | date:'fullDate'}}</p>

 <!-- shortTime format: output '9:43 AM'-->
 <p>The time is {{today | date:'shortTime'}}</p>
```

##### Directivas

Las plantillas en Angular son dinámicas. Cuando Angular las procesa, transforma el DOM de acuerdo con las instrucciones dadas por las directivas. Una directiva es una clase con un decorador `@Directive()`.

Un componente es técnicamente una directiva. Sin embargo, los componentes son tan distintivos y centrales para las aplicaciones de Angular que Angular define el decorador `@Component()`, que extiende el decorador `@Directive()` con características orientadas a plantillas.

Además de los componentes, hay otros dos tipos de directivas: **estructurales y de atributo**. Angular define una serie de directivas de ambos tipos, pero se pueden definir directivas propias utilizando el decorador `@Directive()`.

Las directivas estructurales alteran el diseño agregando, eliminando y reemplazando elementos en el DOM:

```html
<li *ngFor="let hero of heroes"></li> <!-- *ngFor is an iterative -->

<app-hero-detail *ngIf="selectedHero"></app-hero-detail> <!-- *ngIf is a conditional -->
```

Las directivas de atributos alteran la apariencia o el comportamiento de un elemento existente. En las plantillas se ven como atributos HTML normales, de ahí el nombre.

La directiva `ngModel`, que implementa el enlace de datos bidireccional, es un ejemplo de una directiva de atributo. `ngModel` modifica el comportamiento de un elemento existente (generalmente `<input>`) estableciendo su propiedad de valor de visualización y respondiendo a eventos de cambio.

```html
<input [(ngModel)]="hero.name">
```

### Introducción a los Servicios y DI

<https://angular.io/guide/architecture-services>
<https://angular.io/guide/dependency-injection>
<https://academia-binaria.com/servicios-inyectables-en-Angular>

Un servicio es típicamente una clase con un propósito estrecho y bien definido. Debe hacer algo específico y hacerlo bien. Su propósito puede ser contenter lógica de negocio, obtener datos de servidores externos, etc...

Angular distingue los componentes de los servicios para aumentar la modularidad y la reutilización. Al separar la funcionalidad relacionada con la vista de un componente de otros tipos de procesamiento, puede hacer que sus clases de componentes sean livianas y eficientes.

Idealmente, el trabajo de un componente es permitir la experiencia del usuario y nada más. Un componente debe presentar propiedades y métodos para el _'data binding'_, para mediar entre la vista (representada por la plantilla) y la lógica de la aplicación (que a menudo incluye alguna noción de modelo).

Un componente puede delegar ciertas tareas a los servicios, como obtener datos del servidor, validar la entrada del usuario o iniciar sesión directamente en la consola. Al definir tales tareas de procesamiento en una clase de servicio inyectable, pasan a estar a disposición de cualquier componente. Esto también permite más flexibilidad a las aplicaciones ya que podemos inyectar diferentes proveedores del mismo tipo de servicio, según corresponda en diferentes circunstancias.

Los servicios a su vez pueden depender de otros servicios.

```typescript
// Ejemplo de servicio en Angular
export class Logger {
  log(msg: any)   { console.log(msg); }
  error(msg: any) { console.error(msg); }
  warn(msg: any)  { console.warn(msg); }
}
```

La DI o **'Inyección de Dependencias'** está íntimamente conectado en el framework de Angular. Angular crea un _'inyector'_ cuando se crea la aplicación. Este inyector se encarga de crear las dependencias y mantener un contenedor de dependencias que se reutilizarán cuando sea posible. También existe la figura del _'proveedor'_ que es un objeto que le dice al inyector como obtener o crear la dependencia.

Para cualquier dependencia que necesite en su aplicación, debe registrar un proveedor con el inyector de la aplicación, para que el inyector pueda usar el proveedor para crear nuevas instancias. Para un servicio, el **proveedor suele ser la clase de servicio en sí misma**.

Los componentes consumen los servicios, lo que significa que se _inyectan_ dinámicamente en el componente para que pueda ser utilizado. Una dependencia no tiene por qué ser únicamente un servicio. Puede ser una función, un valor, etc...

Para definir una clase como servicio se decora con `@Injectable()` y se provee de los metadatos necesarios para que Angular pueda inyectar el servicio en el componente que lo requiera como dependencia.

Cuando Angular crea una nueva instancia de una clase de componente, determina qué servicios u otras dependencias necesita ese componente al **observar los tipos de parámetros del constructor**:

```typescript
// Angular determina que este componente necesita el servicio 'HeroService'
constructor(private service: HeroService) { }
```

Cuando Angular descubre que un componente depende de un servicio, primero verifica si el inyector tiene alguna instancia existente de ese servicio. Si todavía no existe una instancia de servicio solicitada, el inyector crea una utilizando el proveedor registrado y la agrega al inyector antes de devolver el servicio a Angular de forma que pueda ser reutilizada si otro componente requiere la misma dependencia.

Cuando todos los servicios solicitados se han resuelto y devuelto, Angular puede llamar al constructor del componente con esos servicios como argumentos.

Debe registrar al menos un proveedor de cualquier servicio que vaya a utilizar. El proveedor puede ser parte de los metadatos del servicio, haciendo que ese servicio esté disponible en todas partes, o puede registrar proveedores con módulos o componentes específicos. Es decir, los proveedores se registran en los metadatos de la función decoradora del servicio en `@Injectable ()`, o en los metadatos del módulo `@NgModule()` o del componente `@Component ()`:

Por defecto, cuando creamos un servicio con el comando `ng generate service` de la _'Angular CLI'_ registra un proveedor en el inyector raíz para el servicio creado incluyendo metadatos en la función decoradora `@Injectable()`. Cuando se provee un servicio en el nivel raíz o _'root'_ el servicio es único y compartido por todos aquellos componentes que lo necesiten. También permite a Angular optimizar la aplicación eliminando los servicios que no se estén utilizando:

```typescript
@Injectable({
  providedIn: 'root',
})
```

Cuando se registra un servicio a nivel de módulo, la misma instancia del servicio está disponible para todos los componentes de ese módulo. Esto es, se crea un *singleton* por cada módulo en el que se provea un servicio. Si el mismo servicio se registra en dos módulos, cada módulo recibirá su propia instancia. Para registrar un servicio a nivel de módulo se utiliza la propiedad `providers:[]` de la función decoradora `@NgModule()`:

```typescript
@NgModule({
  providers: [
  BackendService,
  Logger
 ],
 //...
})
```

Cuando se registra un servicio a nivel de componente, se obtiene una nueva instancia del servicio por cada nueva instancia del componente. Para registrar un servicio a nivel de componente se utiliza la propiedad `providers:[]` de la función decoradora `@Component()`:

```typescript
@Component({
  selector:    'app-hero-list',
  templateUrl: './hero-list.component.html',
  providers:  [ CalculatorService ]
})
```

Para crear un servicio de ejemplo abrimos el terminal/consola y escribimos el comando, lo que creará el servicio en el fichero `calculator.service.ts`:

```terminal
`ng generate service <services/calculator>`  // Substituir 'calculator' por el nombre del servicio
```

Esto genera le servicio en Angular que es una clase decorada con `@Injectable()`:

```typescript
import { Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root'
})
export class CalculatorService {
  constructor() { }
}
```

## Routing & Navigation

<https://angular.io/guide/router>
<https://angular.io/guide/router#summary>
<https://academia-binaria.com/paginas-y-rutas-angular-spa/>

El _'Router'_ es el componente en Angular que gestiona la navegación de una vista a otra. Para ello se configura un ['Router'](https://angular.io/api/router/Router) en la aplicación.

### `<base href>`

<https://angular.io/guide/router#base-href>

La mayoría de las aplicaciones de enrutamiento deben agregar un elemento `<base>` al fichero `index.html` como el primer elemento hijo en la etiqueta `<head>` para indicarle al enrutador cómo componer las URL de navegación.

Si la carpeta `app/` es la carpeta raíz de la aplicación, es decir, se ha mantenido la estructura por defecto al crear la aplicación en Angular, esta etiqueta tendrá la siguiente forma:

```html
<html>
  <head>
    <base href="/">
    <!-- ... -->
  </head>
  <!-- ... -->
</html>
```

### Importar el módulo 'RouterModule'

<https://angular.io/guide/router#router-imports>

El _'Router'_ o enrutador en Angular es un servicio opcional, lo que significa que no forma parte del core de Angular. Está en su propio paquete de librería, el `@angular/router`. Tendremos que importar aquellas partes que se necesiten, tal y como se haría con cualquier otro paquete de Angular:

```typescript
// Por ejemplo importamos 'RouterModule' y 'Routes' de la librería
import { RouterModule, Routes } from '@angular/router';
```

### Configuración

<https://angular.io/guide/router#configuration>

Una aplicación enrutada en Angular tiene una instancia única del servicio de [`Router`](https://angular.io/api/router/Router). Cuando la URL del navegador cambia, ese enrutador busca una ruta correspondiente desde la cual puede determinar el componente a mostrar.

Un enrutador no tiene rutas hasta que se configura. El siguiente ejemplo crea cinco definiciones de ruta, configura el enrutador mediante el método `RouterModule.forRoot()` y agrega el resultado al array de `imports:[]` del módulo raíz `AppModule` en el fichero `app.module.ts`:

```typescript
import { Routes, RouterModule } from '@angular/router';
const appRoutes: Routes = [
  { path: 'crisis-center', component: CrisisListComponent },
  { path: 'hero/:id',      component: HeroDetailComponent },
  {
    path: 'heroes',
    component: HeroListComponent,
    data: { title: 'Heroes List' }
  },
  { path: '',
    redirectTo: '/heroes',
    pathMatch: 'full'
  },
  { path: '**', component: PageNotFoundComponent }
];

@NgModule({
  imports: [
    RouterModule.forRoot(
      appRoutes,
      { enableTracing: true } // <-- debugging purposes only. Muestra información de cada evento de enrutado en la consola
    )
    // other imports here
  ],
  ...
})
export class AppModule { }
```

El array de `Routes` llamado `appRoutes` describe las rutas de la aplicación, lo que permitirá navegar por ella. Este array se pasa al método `RouterModule.forRoot()` en las importaciones del módulo para configurar el enrutador.

Cada [`Route`](https://angular.io/api/router/Route) asigna una ruta URL a un componente. No hay barras diagonales en el _path_. El enrutador analiza y crea la URL final, lo que permite utilizar rutas relativas y absolutas al navegar entre las vistas de la aplicación.

El `:id` en la segunda ruta de ejemplo es un token para un parámetro de ruta. En una URL como por ejemplo "/hero/42", el valor '42' es el valor del parámetro 'id'. El componente _'HeroListComponent'_ del ejemplo recibirá ese valor y podrá usarlo para lo que necesite.

La propiedad _'data'_ en la tercera ruta es un lugar para almacenar datos arbitrarios asociados con esta ruta específica. Se puede acceder a la propiedad de datos dentro de cada ruta activada. Se puede utilizar para guardar el título de la página o cualquier otro dato estático y _'read-only'_.

El _path_ vacío de la cuarta ruta de ejemplo representa el **_path_ por defecto** de la aplicación. El lugar al que ir cuando la ruta en la URL está vacía, como sería <http://my-application.com> suele ser la _home_ o página inicial pero puede ser cualquier otra y es aquí donde se define. En el ejemplo la ruta por defecto _'redirecciona'_ a la URL "/heroes", que como se indica en la tercera ruta, será gestionada por el componente `HeroLisComponent`. Para hacer redirecciones se utiliza la propiedad `redirectTo:`.

La ruta `**` en la última ruta es un comodín o _'wildcard'_. El enrutador seleccionará esta ruta si la URL solicitada no coincide con ninguna ruta para las rutas definidas anteriormente en la configuración. Esto es útil para mostrar una página de tipo _"404 - Not found"_ o redirigir a otra ruta.

**El orden de las rutas en la configuración es importante** y esto es por diseño. El enrutador utiliza una estrategia _'first-match wins'_ empezando de arriba hacia abajo. Cuando coincide la ruta con el patrón de la URL carga el componente. Debido a esta estrategia las rutas más específicas deben colocarse al principio y las genéricas o por defecto más abajo. En la configuración anterior de ejemplo, las rutas con una ruta estática se enumeran primero, seguidas de una ruta vacía, que coincide con la ruta predeterminada. La ruta comodín ocupa el último lugar porque coincide con todas las URL y debe seleccionarse solo si no se encuentra una coincidencia primero.

### Router outlet

<https://angular.io/guide/router#router-outlet>

El [`RouterOutlet`](https://angular.io/api/router/RouterOutlet) es una directiva de la biblioteca de enrutadores que se utiliza como un componente. Actúa como un marcador de posición que marca el lugar en la plantilla donde el enrutador debe mostrar los componentes para esa salida.

La idea general de una **SPA es tener una única página que cargue dinámicamente otras vistas**. Normalmente la página contenedora mantiene el menú de navegación, el pie de página y otras áreas comunes. Y deja un espacio para la carga dinámica. Para ello necesitamos saber **qué componente cargar y dónde mostrarlo**. El componente vendrá indicado por el array de `Routes[]`.

Por ejemplo, si tenemos los siguintes ficheros:

```typescript
// app.module.ts
const appRoutes: Routes = [
  { path: 'crisis-center', component: CrisisListComponent },
  { path: 'hero/:id',      component: HeroDetailComponent },
  {
    path: 'heroes',
    component: HeroListComponent,
    data: { title: 'Heroes List' }
  },
  { path: '',
    redirectTo: '/heroes',
    pathMatch: 'full'
  },
  { path: '**', component: PageNotFoundComponent }
];
```

```html
<!-- app.component.html -->
<navbar></navbar>
<main class="container">
  <router-outlet></router-outlet>
  <!-- Dynamic content here! -->
</main>
<footer></footer>
```

De esta forma modificamos el fichero `app.component.html` que es la plantilla del componente raíz con la etiqueta `<router-outlet></router-outlet>` de forma que según la URL, que por ejemplo puede ser "/heroes", Angular cargará el componente indicado `HeroListComponent` y substituirá dinámicamente la etiqueta `<router-outlet></router-outlet>` por la vista de ese componente. De esta forma, tenemos una página dinámica que comporte los menús de navegación y el pie de página y con un contenido dinámico que se carga según la URL.

### Router links

<https://angular.io/guide/router#active-router-links>

Una vez definidas las rutas y los componentes asociados sólo queda ver como navegar por la aplicación, ya sea porque el usuario escribe la dirección directamente en la barra de direcciones del navegador (sólo suele suceder la primera vez) o porque acciones del usuario como clicks en botones o en enlaces dentro de la aplicación.

La directiva [`RouterLink`](https://angular.io/api/router/RouterLink) en las etiquetas `<a>` le dan al enrutador control sobre esos elementos. Las rutas de navegación son fijas, por lo que puede asignar una cadena de texto al routerLink (un enlace "de una sola vez"):

```html
<!-- app.component.html -->
<h1>Angular Router</h1>
<nav>
  <a routerLink="/crisis-center" routerLinkActive="active">Crisis Center</a>
  <a routerLink="/heroes" routerLinkActive="active important">Heroes</a>
</nav>
<router-outlet></router-outlet>
```

La directiva _'RouterLinkActive'_ alterna las clases css para enlaces activos de _'RouterLink'_ basados ​​en el _'RouterState'_ actual. Esta directiva tiene la forma `routerLinkActive="..."` e indica la clase css entre comillas que se aplicará cuando el enlace esté activo y que se eliminará cuando no esté activo. Si se aplican más de una clase se separan con un espacio en blanco.

Los enlaces de ruta activos caen en cascada a través de cada nivel del árbol de ruta, por lo que los enlaces de enrutador padre e hijo pueden estar activos al mismo tiempo.

### RouterState

<https://angular.io/guide/router#router-state>

Después del final de cada ciclo de vida de navegación exitoso, el enrutador crea un árbol de objetos `ActivatedRoute` que conforman el estado actual del enrutador. Puede acceder al [`RouterState`](https://angular.io/api/router/RouterState) actual desde cualquier lugar de la aplicación utilizando el servicio `Router` y la propiedad `routerState`.

Cada `ActivatedRoute` en el `RouterState` proporciona métodos para recorrer hacia arriba y hacia abajo el árbol de ruta para obtener información de las rutas padre, hijo y hermano.

### ActivatedRoute

<https://angular.io/guide/router#activated-route>

La ruta y los parámetros están disponibles a través de un servicio de enrutador inyectado llamado [`ActivatedRoute`](https://angular.io/api/router/ActivatedRoute). Tiene una gran cantidad de información útil que incluye:

* _'URL'_ -> un observable del path o paths de la ruta, representado por un array de strings por cada parte del path.
* _'data'_ -> un observable que contiene el objeto 'data' suministrado a la ruta.
* _'paramMap'_ -> un observable que contiene un 'map' con los parámetros requeridos y opcionales especificados para la ruta.
* _'outlet'_ -> el nombre del 'RouterOutlet' usado para renderizar la ruta.
* _'routeConfig'_ -> la configuración usada para la ruta que contiene el path original
* _'parent'_ -> el 'ActivatedRoute' padre cuando es una ruta hijo.
* _'firstChild'_ -> contiene el primer 'ActivatedRoute' de la lista de rutas hijo.
* _'children'_ -> contiene todas las rutas hijo.

```typescript
ngOnInit() {
  let id = this.route.snapshot.paramMap.get('id');

  this.hero$ = this.service.getHero(id);
}
```

### Router events

<https://angular.io/guide/router#router-events>

Durante la navegación, el _'Router'_ emite eventos a través de la propiedad `Router.events`. Entre el evento inicial hasta el evento final se producen muchos eventos intermedios, como sería cargar la configuración, reconocer la ruta, etc... Estos eventos se registran en la consola cuando la opción `enableTracing` también está habilitada.

[Aquí](https://angular.io/guide/router#router-events) está la lista de todos los eventos que se producen.

## Components & Templates

### Displaying Data

<https://angular.io/guide/displaying-data>

Puede mostrar datos vinculando controles en una plantilla HTML a las propiedades de un componente angular.

La forma más fácil de mostrar una propiedad de un componente es vincular el nombre de la propiedad mediante **interpolación**. Para ello se utiliza el nombre de la propiedad entre doble corchetes ({{}}) en la plantilla HTML:

```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  template: `
    <h1>{{title}}</h1>
    <h2>My favorite hero is: {{myHero}}</h2>
    `
})
export class AppComponent {
  title = 'Tour of Heroes';
  myHero = 'Windstorm';
}
```

Angular extrae automáticamente el valor de las propiedades de `title` y `myHero` del componente e inserta esos valores en el navegador. Angular mantiene actualizados los valores en la vista cuando cambia el valor de estas propiedades.

Nótese que no hemos instanciado de forma explícita el componente `AppComponent`. Angular se encarga de ello. En los metadatos del objeto pasado a la función decoradora `@Component()` le indicamos a Angular la etiqueta `<app-rot>`. Cuando Angular encuentra esa etiqueta en el fichero `index.html` crea una instancia del componente `AppComponent` y lo renderiza dentro de la etiqueta `<app-root>`.

#### Directiva `*ngFor`

Cuando la propiedad es una array de valores, podemos recorrer la lista para visualizar los valores mediante la directiva `*ngFor`:

```typescript
export class AppComponent {
  title = 'Tour of Heroes';
  heroes = ['Windstorm', 'Bombasto', 'Magneta', 'Tornado'];
  myHero = this.heroes[0];
}
```

```html
<h1>{{title}}</h1>
<h2>My favorite hero is: {{myHero}}</h2>
<p>Heroes:</p>
<ul>
  <li *ngFor="let hero of heroes">
    {{ hero }}
  </li>
</ul>
```

Angular duplica la etiqueta `<li>` por cada elemento de la lista y muestra el valor de la variable `hero`.

En este caso la directiva `*ngFor` se emplea para visualizar un array aunque se puede utilizar para repetir items de cualquier objeto [iterable](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols).

#### Visualizar datos de un objeto

Aunque en el ejemplo hemos utilizado un array, en aplicaciones reales se suele iterar sobre objetos que forman parte de la lógica de la aplicación.

Crearemos un clase `Hero` que contendrá las propiedades y utilizaremos la directiva `*ngFor` para recorrer un array de objetos `Hero` y visualizar el nombre:

```bash
# Crear la clase 'Hero'
ng generate class hero
```

```typescript
// 'hero.ts'
export class Hero {
  constructor( public id: number, public name: string) { }
}
```

```typescript
// 'app.component.ts'
heroes = [
  new Hero(1, 'Windstorm'),
  new Hero(13, 'Bombasto'),
  new Hero(15, 'Magneta'),
  new Hero(20, 'Tornado')
];
myHero = this.heroes[0];
```

```html
<!-- app.component.html -->
<h1>{{title}}</h1>
<h2>My favorite hero is: {{myHero.name}}</h2>
<p>Heroes:</p>
<ul>
  <li *ngFor="let hero of heroes">
    {{ hero.name }}
  </li>
</ul>
```

#### Directiva `*ngIf`

A veces, una aplicación necesita mostrar una vista o una parte de una vista solo en circunstancias específicas. Para ello se utiliza la directiva `*ngIf`, similar al `if` condicional de la mayoría de lenguajes:

```typescript
<p *ngIf="heroes.length > 3">There are many heroes!</p>
```

En el ejemplo, si la expresión es `true` Angular añade la etiqueta `<p>` al DOM y se muestra el mensaje.

Con esta directiva Angular no se limita a mostrar u ocultar la etiqueta o su contenido (es decir, no es un simple `display: none;` en CSS). Lo que hace es añadir o eliminar el elemento y todos sus descendientes del DOM, lo que mejora la eficiencia.

## Template syntax

<https://angular.io/guide/template-syntax#template-syntax>

Las aplicaciones en Angular gestionan lo que el usuario ve y puede hacer, logrando esto mediante la interacción de una instancia de la clase `Component` (el componente) y su plantilla orientada al usuario.

Siguiendo los patrones _Model-View-Controller (MVC)_ o _Model-View-ViewModel (MVVM)_, en Angular el componente hace el papel de controlador/viewModel y la plantilla hace el papel de vista.

### HTML en las plantillas

<https://angular.io/guide/template-syntax#html-in-templates>

HTML es el lenguaje utilizado en las plantillas de Angular. Casi toda la sintaxis HTML es una sintaxis de plantilla válida. La etiqueta `<script>` es una notable excepción. Evitando su uso se evita problemas de seguridad y el riesgo de ataques por inyección de comandos.

Otras etiquetas que no tienen sentido en Angular son `<html>`, `<body>` o `<base>`.

### Interpolation and Template Expressions

<https://angular.io/guide/template-syntax#interpolation-and-template-expressions>

La interpolación le permite incorporar cadenas calculadas en el texto entre etiquetas de elementos HTML y dentro de las asignaciones de atributos. Las expresiones de plantilla son lo que se usa para calcular esas cadenas.

#### Interpolation {{...}}

<https://angular.io/guide/template-syntax#interpolation->

La interpolación se refiere a la capacidad de poder incrustar expresiones dentro de etiquetas HTML. Por defecto, la interpolación utiliza como delimitador las llaves dobles, _{{ y }}_.

```html
<h3>Current customer: {{ currentCustomer }}</h3>
```

El texto entre llaves suele ser el nombre de una propiedad del componente. Angular reemplaza ese nombre con el valor de la propiedad del componente correspondiente.

```html
<p>{{title}}</p>
<div><img src="{{itemImageUrl}}"></div>
```

En términos más generales, el texto entre llaves es una expresión de plantilla que Angular primero evalúa y luego convierte en una cadena:

```html
<p>The sum of 1 + 1 is {{1 + 1}}.</p>
```

La expresión puede invocar métodos del componente host como `getVal()`:

```html
<p>The sum of 1 + 1 is not {{1 + 1 + getVal()}}.</p>
```

#### Template Expressions

<https://angular.io/guide/template-syntax#template-expressions>

Una expresión de plantilla produce un valor y aparece dentro de las llaves dobles, _{{}}_. Angular ejecuta la expresión y la asigna a una propiedad de un objetivo vinculante; el objetivo podría ser un elemento HTML, un componente o una directiva.

En una interpolación como `{{1 + 1}}` las llaves rodean una expresión. En un _property binding_, la expresión de plantilla aparece entre comillas y tiene la forma `[property]="expression"`.

En términos de sintaxis, las expresiones de plantilla son muy parecidas a Javascript. Muchas expresiones en Javascript son expresiones de plantilla legales con algunas excepciones:

* Asignaciones (=, +=, -=, ...)
* Operadores como `new`, `typeof`, `instanceof`, ...
* _Chaining expresions_ con ; o ,
* Los operadores de incremento o decremento (++ y --)
* Algunos operadores de ES2015
* No hay soporte para operadores a nivel de bits como | y &.

El contexto de la expresión normalmente es el **componente**, de forma que en la expresión se hace referencia a propiedades del componente:

```html
<h4>{{recommended}}</h4>
<img [src]="itemImageUrl2">
```

El contexto de la expresión también puede ser una variable dentro del template, como por ejemplo hacer referencia a un `input`:

```html
<label>Type something:
  <input #customerInput>{{customerInput.value}}
</label>
```

Por último el contexto de la expresión puede ser una variable dentro de la plantilla como una variable dentro de una directiva `*ngFor`:

```html
<ul>
  <li *ngFor="let customer of customers">{{customer.name}}</li>
</ul>
```

### Template statements

<https://angular.io/guide/template-syntax#template-statements>

Un _template statements_ responde a un evento lanzado por un elemento, componente o directiva y tienen la forma _(event)="statement"_.

Al igual que en las expresiones, normalmente el contexto de una declaración es una instancia del componente:

```html
<button (click)="deleteHero()">Delete hero</button>
```

El nombre _deleteHero_ en `(click)="deleteHero()"` es un método del componente.

El contexto también puede hacer referencia a propiedades del propio contexto de la plantilla, variables que hacen referencia a elementos de la plantilla (`#heroForm`) o variables creadas por una directiva como `*ngFor`:

```html
<button (click)="onSave($event)">Save</button>
<button *ngFor="let hero of heroes" (click)="deleteHero(hero)">{{hero.name}}</button>
<form #heroForm (ngSubmit)="onSubmit(heroForm)"> ... </form>
```

### Data-Binding

_Data-binding_ es un mecanismo para coordinar lo que ven los usuarios, específicamente con los valores de datos de la aplicación. Si bien se pueden extraer e insertar valores dentro del HTML, una aplicación es más fácil de escribir, leer y mantener si un framework específico se encarga de estas tareas.

Angular proporciona varios tipos de _data-binding_ que se pueden agrupar según la dirección del flujo:

|                         |           Markup             |       Nombre          |
| :---------------------- | :--------------------------: | :-------------------: |
|  DOM <------- Component |       {{expression}}         |  _'interpolation'_    |
|  DOM <------- Component |   [target] = "expression"    |  _'property binding'_ |
|  DOM <------- Component |  bind-target = "expression"  |                       |
|  ---------------------- |  --------------------------  |  -------------------- |
|  DOM -------> Component |    (target) = "statement"    |  _'event binding'_    |
|  DOM -------> Component |    on-target = "statement"   |                       |
|  ---------------------- |  --------------------------  |  -------------------- |
|  DOM <------> Component |  [(target)] = "expression"   |  _'two-way binding'_  |
|  DOM <------> Component | bindon-target = "expression" |  _'two-way binding'_  |

El _data-binding_ trabaja con las**propiedades de los elementos del DOM, componentes y directivas** y no con los atributos HTML.

La diferencia entre una propiedad DOM y un atributo HTML es que los atributos están definidos por el HTML y las propiedades son accesibles por el DOM. Una regla para distinguir un atributo de una propiedad es que los atributos inicializar las propiedades del DOM y luego terminan. **Los valores de las propiedades pueden cambiar, el valor del atributo no cambia**.

El atributo HTML y la propiedad DOM no son lo mismo, incluso cuando tienen el mismo nombre.

```html
<input type="text" value="Sarah">
```

Cuando el navegador renderiza esta etiqueta, crea el correspondiente DOM con la propiedad `value` inicializada con "Sarah". Cuando el usuario introduce la palabra "Sally" en el `<input>` la propiedad `value` cambia a "Sally".

Sin embargo, si miramos el atributo HTML `value` con la función `input.getAttribute('value')` vemos que su valor sigue siendo "Sarah".

En definitiva, en Angular el único papel de los atributos es inicializar el elemento y el estado de la directiva. Cuando se crea un _data-binding_ se trata exclusivamente de propiedades y eventos del objeto de destino.

### Binding targets

<https://angular.io/guide/template-syntax#binding-targets>

El objetivo de un enlace de datos es algo en el DOM. Depende del tipo, el objetivo puede ser una propiedad (de un elemento, componente o directiva), un evento (de un elemento, componente o directiva) y de forma excepcional con algunos atributos:

* **Propiedad** (elemento, componente o directiva)

```html
<img [src]="heroImageUrl">
<app-hero-detail [hero]="currentHero"></app-hero-detail>
<div [ngClass]="{'special': isSpecial}"></div>
```

* **Evento** (elemento, componente o directiva)

```html
<button (click)="onSave()">Save</button>
<app-hero-detail (deleteRequest)="deleteHero()"></app-hero-detail>
<div (myClick)="clicked=$event" clickable>click me</div>
```

* **Two-way** (eventos y propiedades)

```html
<input [(ngModel)]="name">
```

* **Atributos** (de forma excepcional)

```html
<button [attr.aria-label]="help">help</button>
```

* **Clases**

```html
<div [class.special]="isSpecial">Special</div>
```

* **Style**

```html
<button [style.color]="isSpecial ? 'red' : 'green'">
```

#### Propiedades

<https://angular.io/guide/template-syntax#property-binding-property>

## Formularios, tablas y modelos de datos en Angular

<https://academia-binaria.com/formularios-tablas-y-modelos-de-datos-en-angular/>

Vamos a ver cómo la librería `@angular/forms` enlaza **las vistas, los controladores y los modelos;** y cómo se hace la presentación de datos en **listas y tablas**.

### Binding

#### Base

Los formularios son el **punto de entrada** de información a nuestros sistemas. Llevan con nosotros desde el inicio de la propia informática y se han comido una buena parte del tiempo de programación. En Angular han prestado una especial atención a ellos facilitando su desarrollo, desde pantallas simples hasta complejos procesos.

Para empezar crearemos un proceso sencillo. algo que permita mantener una lista de contactos empresariales. Con lo aprendido en el tema de Páginas y rutas Angular SPA creamos un par de ficheros:

```terminal
ng g m contacts --routing true
ng g c contacts/contacts
```

Y asignamos sus rutas delegadas en `app-routing` y en `contacts-routing`:

```typescript
// app-routing
{
  path: 'contacts',
  loadChildren: './contacts/contacts.module#ContactsModule'
},
// contacts-routing
{
  path: '',
  component: ContactsComponent
}
```

Y finalizamos con un enlace en el `HeaderComponent`:

```html
<a routerLink="contacts" class="button">
  <span> Contacts</span>
</a>
```

La clave para entender cómo funciona Angular está en el concepto de **enlace entre elementos html de las vistas y propiedades de modelos de datos**, el llamado *binding*.

Para realizar el *binding* usaremos directivas en ambos sentidos.

#### Enlace del modelo hacia la vista

Vamos a crear un pequeño modelo de datos. Para empezar agregamos algunas propiedades. En `'contacts.component.ts'`:

```typescript
public header = 'Contacts';
public description = 'Manage your contact list';
public numContacts = 0;
public counterClass = 'tag secondary';
public formHidden = false;
```

En `'contacts.component.html'` mostramos cabeceras con estilo:

```html
<h2>{{ header }}</h2>
<p>{{ description | uppercase }}</p>
<p>
  You have
  <mark [class]="counterClass">{{ numContacts }}</mark>
  contacts right now.
</p>
```

##### La interpolación entre {{}}

En el fichero `'contacts.component.ts'` tienes en su vista html elementos ajenos al lenguaje. Son las **directivas**. La primera que encuentras es `{{}}`. Esas dobles llaves encierran expresiones que se evaluarán en tiempo de ejecución. La llamamos **directiva de interpolación** y es la manera más cómoda y usual de mostrar contenido dinámico en Angular.

>La expresión interna hace referencia a variables que se obtienen de las propiedades de la clase controladora del componente. En este caso `ContactsComponent` y `header`, con su valor *Contacts* en ejecución. Este enlace mantiene la vista permanentemente actualizada a través de un potente sistema de detección del cambio.

##### Las tuberías |

Si queremos que la presentación del dato sea distinta a su valor real, podemos usar funciones de transformación especiales. Se llaman **tuberías o pipes** y se indican mediante el carácter `|`.

El framework nos provee de casos básicos como `uppercase`, `lowercase`, `date`, `number`.... También dispones de un mecanismo para crear tus propios pipes.

##### Los atributos evaluados []

En html disponemos de atributos para asignar valores a propiedades de los elementos. Esos atributos reciben los valores como constantes. Pero, si se encierran entre corchetes se convierten en un **evaluador de expresiones** y puede recibir una variable o cualquier otra expresión.

Como por ejemplo usando una clase css cuyo valor cambia en tiempo de ejecución. O para deshabilitar un elemento dinámicamente.

#### Enlace de la vista hacia el modelo

En `'contacts.component.html'` también actuamos sobre la vista, para manipular el modelo… y de vuelta a la vista. Por ejemplo con mecanismo simple de ocultación de un elemento.

```html
<input value="Show Form" type="button" (click)="formHidden = false" />
<input value="Hide Form" type="button" (click)="formHidden = true" />
<form [ngClass]="{ 'hidden' : formHidden }">
  <fieldset><legend>Contact Form</legend></fieldset>
</form>
```

##### Las clases CSS como atributos especiales

Para el caso concreto de determinar las clases CSS aplicables a un elemento de manera dinámica, usaremos la directiva `ngClass`. La cual recibe un objeto cuyas propiedades son nombres de clases CSS y sus valores son expresiones booleanas. Si se cumplen se aplica la clase y si no, se quita la clase.

```CSS
[ngClass]="{ 'hidden' : formHidden }"
```

En este caso se oculta el elemento dependiendo del valor de la expresión `formHidden`. Pero ¿Cómo se manipula esa variable?

##### Los eventos ()

Cualquier evento asociado a un elemento puede ejecutar una instrucción. Únicamente hace falta incluirlo entre paréntesis. Idealmente dicha instrucción debe llamar a un método o función de la clase controladora. Aunque si es trivial se puede dejar en el html: `(click)="formHidden = true"`

### Doble Binding

La comunicación del modelo hacia la vista es sólo el principio. En Angular también podrás comunicar la vista hacia el modelo, permitiéndole al usuario modificar los datos a través de formularios. Es lo que se conoce como **double binding**.

#### El doble enlace al modelo [(ngModel)]

La directiva `[(ngModel)]` se compone de un atributo `ngModel` y lo rodea de los símbolos `[()]`. Esta técnica es conocida como *banana in a box* porque su sintaxis requiere un `()` dentro de un `[]` y une las capacidades de las expresiones y los eventos facilitando la comunicación bidireccional.

```typescript
[(ngModel)]="model.property"
```

Usa la comunicación en ambos sentidos:

* `(banana)`: de la vista al modelo
* `[box]`: del modelo a la vista

>Atención: La directiva `ngModel` viene dentro del módulo `FormsModule` que hay que importar explícitamente.

Por ejemplo `[(ngModel)]="contact.name"` enlaza doblemente la propiedad del modelo `contact.name` con el elemento `<input>` de la vista. Cada tecleo del usuario se registra en la variable. Y el valor de la variable se muestra en el `<input>`.

Dada un modelo como este en `'contacts.component.ts'`:

```typescript
public contact = { name: '' };
```

Podemos enlazarlos en la plantilla:

```html
<section>
  <label for="name">Name</label>
  <input name="name" type="text" [(ngModel)]="contact.name" placeholder="Contact name" />
</section>
```

>Es muy útil mantener en desarrollo un espía visual de lo que está pasando con los datos. Algunas extensiones como Augury aportan muchas más prestaciones, pero al empezar el pipe json te ayudará mucho: `<pre>{{ contact | json }}</pre>`

La directiva `ngModel` es mucho más potente de lo visto aquí. Entre otras cosas permite decidir el criterio de actualización (a cada cambio o al salir del control). También se verá más adelante el asunto de la validación, que requiere un trato especial. Cuando empiezas con Angular Forms, un **input y su ngModel** asociado serán tus mejores amigos.

#### Form

Hay más usos de las directivas en los formularios. Por ejemplo, dado el siguiente modelo:

```typescript
public contact = { name: '', isVIP: false, gender: '' };
```

Le vendría muy bien un check box:

```html
<section>
  <label for="isVIP">Is V.I.P.</label>
  <input name="isVIP" type="checkbox" [(ngModel)]="contact.isVIP" />
</section>
```

Y un par de radio buttons:

```html
<section>
  <label for="gender">Gender</label>
  <input name="gender" value="male" type="radio" [(ngModel)]="contact.gender" />
  <i>Male</i>
  <input name="gender" value="female" type="radio" [(ngModel)]="contact.gender" />
  <i>Female</i>
</section>
```

### Estructuras

Los anteriores modificadores actúan a nivel de contenido del HTML. Veremos ahora una par de directivas que afectan directamente a la estructura del árbol DOM. Son las llamadas **directivas estructurales** que comienzan por el signo `*`.

#### Repetitivs *ngFor

Una situación que nos encontramos una y otra vez es la de las repeticiones. Listas de datos, tablas o grupos de opciones son ejemplos claros. Hay una directiva en Angular para esa situación, la `*ngFor="let iterador of array"`. La directiva `*ngFor` forma parte del grupo de directivas estructurales, porque modifica la estructura del DOM, en este caso insertando múltiples nodos hijos a un elemento dado.

>Puedes ver un ejemplo del uso la directiva `*ngFor` en el componente `ContactsComponent`. Se emplea para recorrer un array de tipos de estado laboral. Es el caso de uso más repetido de las repeticiones; mostrar listas de datos.

Dado el siguiente modelo:

```typescript
public workStatuses = [
  { id: 0, description: 'unknow' },
  { id: 1, description: 'student' },
  { id: 2, description: 'unemployed' },
  { id: 3, description: 'employed' }
];
public contact = { name: '', isVIP: false, gender: '', workStatus: 0 };
```

Montamos las opciones de un select html recorriendo el array y usando el iterador `wkSt` para acceder a sus datos:

```html
<section>
  <label for="workStatus">Work Status</label>
  <select name="workStatus" [(ngModel)]="contact.workStatus">
    <option *ngFor="let wkSt of workStatuses" [value]="wkSt.id">
      <span>{{ wkSt.description }}</span>
    </option>
  </select>
</section>
```

#### Condicionales *ngIf

La directiva estructural más utilizada es la `*ngIf`, la cual consigue que un elemento se incluya o se elimine en el DOM en función de los datos del modelo.

>En el ejemplo puedes ver que la uso para mostrar el campo empresa cuando el contacto está trabajando. En otro aparecerá el campo de estudios.

Dado el siguiente modelo:

```typescript
public contact = {
  name: '',
  isVIP: false,
  gender: '',
  workStatus: '0',
  company: '',
  education: ''
};
```

```html
<!-- if condition else template -->
<section *ngIf="contact.workStatus=='3'; else education">
  <label for="company">Company Name</label>
  <input name="company" type="text" [(ngModel)]="contact.company" />
</section>
<ng-template #education>
  <label for="education">Education</label>
  <input name="education" type="text" [(ngModel)]="contact.education" />
</ng-template>
```

##### Identificadores con hashtag

En el código anterior apreciarás que aparece un elemento `<ng-template>` no estándar con el atributo llamado `#education` precedido por un `#`. La directiva `#` genera un identificador único para el elemento al que se le aplica y permite referirse a él en otros lugares del código.

Ese truco permite que `*ngIf` muestre otro elemento cuando la condición principal falle. El otro elemento tiene que ser el componente especial `<ng-template>` que se usa para envolver una rama opcional del DOM. Para localizarlo se usa el identificador `#`.

### Modelo y controlador

Los componentes los hemos definido como bloques de construcción de páginas. Mediante una vista y un controlador resuelven un problema de interacción o presentación de modelos. En los puntos anteriores te presenté la vista. Toca ahora estudiar el modelo y el controlador.

#### Interfaces y modelos

Sin ir muy lejos en las capacidades que tendría un modelo de datos clásico, vamos al menos a beneficiarnos del TypeScript para definir la estructura de datos. Esto facilitará la programación mediante el autocompletado del editor y reducirá los errores de tecleo mediante la comprobación estática de tipos.

Para ello necesito una interfaz sencilla. Esto es puro TypeScript, no es ningún artificio registrable en Angular. Esos sí, en algún sitio tienen que estar. Yo suelo usar una ruta como `contacts/models`, pero es algo completamente arbitrario.

```typescript
export interface Option {
  id: number;
  description: string;
}

export interface Contact {
  name: string;
  isVIP: boolean;
  gender: string;
  workStatus: number | string;
  company: string;
  education: string;
}
```

>Te recomiendo que no uses clases para definir modelos a menos que necesites agregarle funcionalidad imprescindible. Las interfaces, ayudan al control de tipos en tiempo de desarrollo, igual que las clases, pero sin generar nada de código en tiempo de ejecución, al contrario que las clases.

Se usan para tipificar las propiedades que conforman nuestro modelo para la vista:

```typescript
public workStatuses: Option[] = [
    { id: 0, description: 'unknow' },
    { id: 1, description: 'student' },
    { id: 2, description: 'unemployed' },
    { id: 3, description: 'employed' }
  ];
public contact: Contact = {
    name: '',
    isVIP: false,
    gender: '',
    workStatus: 0,
    company: '',
    education: ''
  };
public contacts: Contact[] = [];
```

#### ViewModel en el controlador

La parte de **lógica del componente** va en la clase que se usa para su definición. Como ya has visto podemos usar su constructor para reclamar dependencias y usar los interfaces para responder a eventos de su ciclo de vida. Repasemos el `ContactsComponent` viéndolo como la clase que es: no solo propiedades, también métodos:

```typescript
public saveContact() {
  this.contacts.push({ ...this.contact });
  this.numContacts = this.contacts.length;
}
```

Ahora se trata de invocar el método desde la vista. Es muy buena práctica llevar la lógica al controlador y no escribirla en la vista: `<input value="Save" type="submit" (click)="saveContact()" />`

Podemos decir que las propiedades públicas de la clase actuarán como binding de datos con la vista. Mientras que los métodos públicos serán invocados desde los eventos de la misma vista.

##### OnInit

Los componentes son clases con un **ciclo de vida** al que puedes enganchar tu código en algunos pasos. Por ejemplo al iniciarse el componente.

El CLI hace que las clase del componente implemente la interfaz `OnInit` y eso permite al framework invocar al método `ngOnInit` en cuanto el componente esté listo para su uso. Que no suele ser justo durante la construcción, si no un poco después. Te recomiendo que lleves toda la lógica de inicialización a dicho método.

```typescript
public workStatuses: Option[];
public contact: Contact;
public contacts: Contact[];
constructor() {}
public ngOnInit() {
  this.workStatuses = [
    { id: 0, description: 'unknow' },
    { id: 1, description: 'student' },
    { id: 2, description: 'unemployed' },
    { id: 3, description: 'employed' }
  ];
  this.contact = {
    name: '',
    isVIP: false,
    gender: '',
    workStatus: 0,
    company: '',
    education: ''
  };
  this.contacts = [];
}
```

## Flujo de datos entre componentes

<https://academia-binaria.com/flujo-de-datos-entre-componentes-angular/>

Los desarrollos profesionales son complicados pero con Angular tenemos soluciones de comunicación simples para pantallas complejas. Mediante el desarrollo de componentes atómicos y reutilizables Angular favorece la implementación de buenas prácticas.

Crear y comunicar muchos componentes puede llevarnos a código difícil de seguir. La librería `@angular/forms` ofrece tuberías de comunicación para mantener el flujo de datos bajo control.

### Comunicación entre componentes

Las aplicaciones web en las que destaca Angular suelen ser complejas y con mucha variedad funcional en diversas páginas. A menudo esas páginas están repletas de formularios, informes y botones. La solución viene de mano del viejo principio divide y vencerás: **la componentización.**

#### Necesidad de comunicación

El framework permite y recomienda repartir el trabajo en múltiples componentes de responsabilidad única. También es práctica común el crear páginas específicas para situaciones concretas aunque relacionadas. Por supuesto que estructuras como el menú de navegación o secciones de estado general necesitan conocer datos provenientes de las páginas. Nada está completamente aislado. Esto nos enfrenta al problema de **comunicar componentes**.

#### Escenarios

Las situaciones que te encontrarás caerán en alguna de estas tres categorías para las que hay soluciones específicas:

##### Comunicar componentes acoplados

Solemos empezar creando un componente por página. Pero es normal que esa página se complique y la solución a la complejidad es **la división en componentes** y **reparto de responsabilidades**. Dado que están en una misma página existe cierto acoplamiento entre ellos y eso nos facilitará la comunicación.

##### Comunicar componentes en páginas distintas

Cuando los componentes se carga en rutas distintas ya no hay forma de comunicarlos directamente. Pero lo resolveremos fácilmente usando las **capacidades del router**.

##### Comunicar componentes entre estructuras dinámicas

La situación más compleja se da cuando queremos comunicar componentes o servicios desacoplados pero sin cambio de página. En este caso hará falta un **mediador observable**.

### Contenedores / Presentadores

En arquitectura de software cuando encontramos una solución a un problema recurrente le ponemos un nombre y tratamos de utilizarlo siempre que podemos. Obviamente es una elección del programador y siempre tiene un coste que debe valorar. En este caso la ventaja es clara: **reparto de responsabilidades**.

#### Patrón 'Contenedor/presentador'

En este caso el patrón **contendor/presentadores** estipula que haya un único componente responsable de obtener, mutar y guardar el estado. Será el componente contenedor. Los presentadores serán responsables de presentar la información y los elementos de interacción con el usuario. Las ventajas derivadas son: mayor facilidad para el testeo y mayores posibilidades de reutilización de presentadores.

>A este patrón a veces se le conoce como *parent/children* por la jerarquía html que genera.

Veamos una implementación sencilla. Haremos una interfaz mínima para simular el manejo de un coche. Habrá pedales de aceleración y freno, y un cuadro dónde se refleje la velocidad. Para todo ello vamos a usa el Angular CLI y crear un módulo y sus componentes base:

```terminal
ng g m 4-flow/car
ng g c 4-flow/car/car
ng g c 4-flow/car/car/display
ng g c 4-flow/car/car/pedals
```

Agregamos una ruta en el enrutador con su enlace en el menú:

```typescript
{
  path: 'car',
  loadChildren: './car/car.module#CarModule'
}
```

```html
<a routerLink="car" class="button">
  <span> 4 - Car</span>
</a>
```

#### El contenedor

En el componente contenedor tendremos una vista muy sencilla y un controlador más complejo. La vista será la composición de los componentes presentadores, pero el controlador tendrá que obtener datos, aplicarles lógica de negocio y guardarlos cuando corresponda.

>No es habitual asignarle un sufijo al nombre del componente para indicar que es el contendor. Suele ser suficiente el verlo en la raíz de la jerarquía de carpetas.

```typescript
<app-display [model]="car.name"
             [currentSpeed]="car.currentSpeed"
             [topSpeed]="car.maxSpeed"
             [units]="'Km/h'">
</app-display>
<app-pedals (brake)="onBrake($event)"
            [disableBrake]="disableBrake"
            (throttle)="onThrottle($event)"
            [disableThrottle]="disableThrottle">
</app-pedals>
```

Vemos que usa los componentes presentadores `Display` y `Pedals` enviándoles información y suscribiéndose a sus eventos. Concretaremos esta funcionalidad más adelante.

```typescript
public car: CarModel;
public disableBrake: boolean;
public disableThrottle: boolean;

constructor() {}

public ngOnInit() {
  this.car = { name: 'Roadster', maxSpeed: 120, currentSpeed: 0 };
  this.checkLimits();
}
private checkLimits() {
  this.disableBrake = false;
  this.disableThrottle = false;
  if (this.car.currentSpeed <= 0) {
    this.car.currentSpeed = 0;
    this.disableBrake = true;
  } else if (this.car.currentSpeed >= this.car.maxSpeed) {
    this.car.currentSpeed = this.car.maxSpeed;
    this.disableThrottle = true;
  }
}
public onBrake(drive: number) {
  this.car.currentSpeed -= this.getDelta(drive);
  this.checkLimits();
}
public onThrottle(drive: number) {
  this.car.currentSpeed += this.getDelta(drive);
  this.checkLimits();
}
private getDelta = (drive: number) =>
  drive + (this.car.maxSpeed - this.car.currentSpeed) / 10;
```

Lo dicho, la clase controladora del componente contenedor **retiene el grueso de la funcionalidad**. En este caso inicializar una instancia de un coche y mantener sus velocidad en los límites lógicos respondiendo a las acciones del usuario conductor.

#### Envío hacia el presentador con '@Input()'

Esta comunicación hacia abajo envía la información **desde el contenedor hacia el presentador**. Es similar a como una plantilla recibe la información desde el controlador.

Para que una vista muestre datos tiene que usar directivas como asociada a una propiedad pública de la clase componente. Se supone que dicha clase es la responsable de su valor. Pero también puede recibirlo desde el exterior. La novedad es hacer que lo reciba vía html.

```html
<h2> {{ model }} </h2>
<h3> Top speed: {{ topSpeed | number:'1.0-0' }}</h3>
<div class="card">
  <div class="section">
    {{ currentSpeed | number:'1.2-2' }} {{ units }}
  </div>
  <progress [value]="currentSpeed"
            [ngClass]="getSpeedClass()"
            [max]="topSpeed">
  </progress>
</div>
```

Empieza por decorar con `@Input()` la propiedad que quieres usar desde fuera. Por ejemplo un código como este del archivo `'display.component.ts'`:

```typescript
export class DisplayComponent implements OnInit {
  @Input() public model: string;
  @Input() public currentSpeed: number;
  @Input() public topSpeed: number;
  @Input() public units: string;
  constructor() {}
  ngOnInit() {}
  public getSpeedClass = () =>
    this.currentSpeed < this.getThreshold() ? 'primary' : 'secondary';
  private getThreshold = () => this.topSpeed * 0.8;
}
```

Ahora puedes enviarle datos a este componente desde el html de su consumidor. Por ejemplo desde `'car.component.html'` le puedo enviar una variable o cualquier expresión evaluable. Recordemos como usa `[propiedad]="expresion"` en el elemento presentador:

```html
<app-display [model]="car.name"
             [currentSpeed]="car.currentSpeed"
             [topSpeed]="car.maxSpeed"
             [units]="'Km/h'">
</app-display>
```

En la clase controladora del presentador quedan responsabilidades reducidas a temas específicos como determinar las clases css apropiadas o transformar los datos para su presentación.

Estoy usando al componente de nivel inferior como un presentador; mientras que el contenedor superior actúa como controlador. Este mismo patrón puede y debe repetirse hasta descomponer las vistas en estructuras simples que nos eviten repeticiones absurdas en código.

De esta forma es fácil crear componentes reutilizables; y queda muy limpio el envío de datos hacia abajo. Pero, ¿y hacia arriba?.

#### Respuesta del presentador con '@Output()'

Los componentes de nivel inferior no sólo se dedican a presentar datos, también presentan controles. Con ellos el usuario podrá crear, modificar o eliminar los datos que quiera. Aunque no directamente; para hacerlo **comunican el cambio requerido al contenedor de nivel superior**.

Por ejemplo, el componente `PedalsComponent` permite acelerar y frenar. Bueno, realmente permite que el usuario diga que lo quiere hacer; los cambios se harán más arriba. Veamos lo básico del `'pedals.component.html'` antes de nada:

```html
<h3> Pedals: </h3>
<form>
  <input value="brake"
    class="secondary"
    type="button"
    [disabled]="disableBrake"
    (click)="brake.emit(1)"/>
  <input value="throttle"
    class="tertiary"
    type="button"
    [disabled]="disableThrottle"
    (click)="throttle.emit(1)"/>
</form>
```

Claramente son un par de botones que con el evento `(click)` responden a acciones del usuario. En este caso se manifiesta una intención de acelerar o frenar el coche. Pero el método del controlador no actúa directamente sobre los datos.

En su lugar, lo que hace es **emitir un evento** confiando que alguien lo reciba y actúe en consecuencia. Por ejemplo la emisión de la instrucción de frenado se realiza mediante la propiedad `brake` decorada con `@Output() public brake new EventEmitter<number>();`. Dicha propiedad será una instancia de un emisor de eventos que mediante el método `.next()` que emite la señal hacia arriba.

```typescript
export class PedalsComponent implements OnInit {
  @Input() public disableBrake: boolean;
  @Input() public disableThrottle: boolean;
  @Output() public brake = new EventEmitter<number>();
  @Output() public throttle = new EventEmitter<number>();
  constructor() {}
  ngOnInit() {}
}
```

Mientras tanto, en **el contenedor la vista se subscribe al evento `(brake)`** como si este fuese un evento nativo y llama a los métodos que manipulan los datos de verdad.

```html
<app-pedals (brake)="onBrake($event)"
            [disableBrake]="disableBrake"
            (throttle)="onThrottle($event)"
            [disableThrottle]="disableThrottle">
</app-pedals>
```

Las propiedades *output* también pueden enviar argumentos que serán recibidos mediante el identificador `$event` propio del framework. Se declaran especificando el tipo del argumento en el genérico del constructor de `EventEmitter<any>`.

En el controlador ya podemos operar con los datos. El método `onBrake(drive: number)` accede y modifica el valor de la velocidad y lo notifica automáticamente hacia abajo.

De esta manera se cierra el círculo. Los componentes de bajo nivel pueden **recibir datos para ser presentados o emitir eventos para modificarlos**. El componente de nivel superior es el **único responsable de obtener y actuar sobre los datos**.

### Comunicaciones entre páginas o estructuras

#### Comunicación entre distintas páginas

En las aplicaciones hay **comunicaciones de estado más allá de la página actual**. La comunicación entre páginas es responsabilidad del `@angular/router`. Una vez activada una ruta, el sistema carga un componente en el `<router-outlet>` correspondiente. No hay forma de comunicarse hacia *(arriba)* o *[abajo]* con algo desconocido. De una página a otra tampoco es problema pues la comunicación va mediante los parámetros de la url.

Ya hemos usado esta comunicación anteriormente en el tema sobre SPA el componente `AuthorComponent` es capaz de recibir por parámetros una identificación de un autor. Esa información es el resultado de una acción del usuario en la pantalla `/about/authors` programada en el componente `AuthorsComponent`. Por tanto es una comunicación entre componentes, en la que ambos son *controladores hermanos*.

#### Comunicación entre estructuras desacopladas

Estando en la misma ruta, no siempre se podrán conocer los componentes, y por tanto no se podrán usar sus *`[propiedades] y (eventos)`*

Una situación habitual es **comunicar la vista de negocio activa con elementos generales** de la página. Por ejemplo podrías querer mostrar la velocidad máxima alcanzada en la barra del menú o un un mensaje emergente cada vez que se alcance la velocidad límite. En este caso, el `<router-outlet>` es una barrera que impide usar el patrón contendor-presentador pues no se puede predecir el contenido dinámico que carga el `RouterOutlet`.

Cuando las pantallas se hacen realmente complejas empiezan a surgir árboles de componentes de muchos niveles de profundidad. En estas situaciones mantener un único controlador a nivel raíz es poco práctico. Enviar hacia abajo las `[propiedades]` es tedioso, pero peor aún es hacer burbujear los `(eventos)` por varias capas de presentadores.

La solución en ambos casos pasa por permitir que algunos componentes presentadores tengan su propio control de datos. Este tipo de comunicaciones técnicamente se resuelve mediante *Observables* y merece un capítulo especial que se verá más adelante en esta serie. Incluso en situaciones complejas habrá que optar por patrones avanzados de gestión de estado como pueda ser Redux.

## Comunicaciones HTTP

<https://academia-binaria.com/comunicaciones-http-en-Angular>

En la versión Angular 7 y posteriores consumir un servicio REST puede ser cosa de niños si aprendes a jugar con los observables y los servicios de la librería `@angular/common/http`. Conseguirás realizar *comunicaciones http asíncronas en Angular*.

### El servicio 'HttpClient'

Como demostración vamos a consumir un API pública con datos de cotización de monedas. Crearé un módulo y un componente en el que visualizar las divisas y después las transformaremos para guardarlas en un servicio propio:

```terminal
ng generate module 6-http/rates --routing true
ng generate component 6-http/rates/rates
```

#### Importación y declaración de servicios

La librería `@angular/common/http` trae el módulo `HttpClientModule` con el servicio inyectable `HttpClient`. Lo primero es importar dicho módulo:

```typescript
import { HttpClientModule } from '@angular/common/http';

@NgModule({
  declarations: [RatesComponent],
  imports: [HttpClientModule]
})
export class RatesModule { }
```

En tu componente tienes que reclamar la dependencia al servicio para poder usarla. Atención a la importación pues hay más clases con el nombre HttpClient. Debe quedar algo así:

```typescript
import { HttpClient } from '@angular/common/http';
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-rates',
  templateUrl: './rates.component.html',
  styles: []
})
export class RatesComponent implements OnInit {
  constructor(private httpClient: HttpClient) {}

  ngOnInit() {}
}
```

A partir de este momento sólo queda invocar los métodos REST en la propiedad `this.http`.

#### Obtención de datos

Para cada verbo http tenemos su método en el servicio `HttpClient`. Su primer parámetro será la url a la que invocar. Empecemos por el `get` que automáticamente solicita y devuelve objetos JSON desde un API. Por ejemplo para obtener las últimas cotizaciones de las principales divisas lo haremos así:

```typescript
export class RatesComponent implements OnInit {
  private urlapi
    = 'https://api.exchangeratesapi.io/latest';
  public currentEuroRates: any = null;

  constructor(private httpClient: HttpClient) {}

  ngOnInit() {
    this.getCurrentEuroRates();
  }

  private getCurrentEuroRates() {
    const currencies = 'USD,GBP,CHF,JPY';
    const url = `${this.urlapi}?symbols=${currencies}`;
    this.httpClient
      .get(url)
      .subscribe(apiData => (this.currentEuroRates = apiData));
  }
}
```

>El método *get* retorna un objeto observable. Los observables http han de consumirse mediante el método *subscribe* para que realmente se lancen. Dicho método subscribe admite hasta tres callbacks: `susbcribe(data, err, end)` para que se ejecuten en respuesta a eventos. En este ejemplo solo hemos usado el primero.

La presentación en la vista sólo tiene que acceder a la propiedad dónde se hayan cargado las respuestas tratadas en el callback de la suscripción:

```html
<h2> Currency Rates. </h2>
<h3> From Euro to the world </h3>
<pre>{{ currentEuroRates | json }}</pre>
```

#### Envío de datos

Supongamos que, una vez recibidas las cotizaciones, pretendemos transformarlas y almacenarlas en otro servicio. El envío en este caso será con el método *post* al que se le pasará la ruta del *endpoint* y el objeto `payload` que se enviará al servidor.

Vamos a agregar una propiedad y un par de métodos al `'rates-component.ts'`. La idea es obtener un array de cotizaciones aa partir del objeto previo, y guardarla una por una:

```typescript
export class RatesComponent implements OnInit {
  private myRatesApi
    = 'https://api-base.herokuapp.com/api/pub/rates';

  public postRates() {
    const rates = this.transformData();
    rates.forEach(rate =>
      this.httpClient
        .post(this.myRatesApi, rate)
        .subscribe()
    );
  }

  private transformData() {
    const current = this.currentEuroRates.rates;
    return Object.keys(current).map(key => ({
      date: this.currentEuroRates.date,
      currency: key,
      euros: current[key]
    }));
  }
}
```

>Atención a los métodos `subscribe()`. Aunque vayan vacíos son imprescindibles para que se ejecute la llamada.

En la vista no hay gran cosa que hacer, salvo agregarle un botón para iniciar el proceso:

```html
<input value="Save Rates" type="button" (click)="postRates()" />
```

#### Actualización de datos

Un par de ejemplo más para acabar de entender la mecánica básica de `HttpClient`. Podemos fijar el tipo de datos esperado en cualquier llamada. De hecho es recomendable que tengas un interfaz para cada respuesta esperada.

En este tutorial no se ha hecho y nos quedamos con el `any`, pero al menos distinguimos entre objetos y arrays. Esto es lo que añado al `RatesComponent` para que muestre los datos guardados en mi API:

```typescript
export class RatesComponent implements OnInit {
 private myRatesApi
  = 'https://api-base.herokuapp.com/api/pub/rates';
 public myRates: any[] = null;

 public getMyRates() {
    this.httpClient
      .get<any[]>(this.myRatesApi)
      .subscribe(apiResult => (this.myRates = apiResult));
  }
}
```

Y en la vista, un nuevo botón y una nueva expresión:

```html
<input value="Refresh" type="button" (click)="getMyRates()" />
<pre>{{ myRates | json }}</pre>
```

Por último, en plan repaso, un ejemplo de método para borrar:

```typescript
public deleteMyRates() {
  this.httpClient
    .delete(this.myRatesApi)
    .subscribe();
}
```

Y su botón en en la vista:

```html
<input value="Delete Rates" type="button" (click)="deleteMyRates()" />
```

### Observables

Las comunicaciones entre navegadores y servidores son varios órdenes de magnitud más lentas que las operaciones en memoria. Por tanto deben realizarse de **manera asíncrona** para garantizar una buena experiencia al usuario.

Esta experiencia no siempre fue tan buena para el programador. Sobre todo con las primeras comunicaciones *AJAX* basadas en el paso de funciones *callback*. La aparición de las *promises* mejoró la claridad del código, y ahora con los **Observables** tenemos además una gran potencia para manipular la información asíncrona.

> El patrón Observable fue implementado por Microsoft en la librería *Reactive Extensions* más conocida como **RxJs**. El equipo de Angular decidió utilizarla para el desarrollo de las comunicaciones asíncronas.

Lo primero es importar el código, de forma similar a cualquier otra clase o función. Por ejemplo para empezar basta con `import { Observable } from "rxjs/Observable";`. Tendremos la clase usada por Angular para observar el respuesta http.

Pero esta es una clase genérica donde sus instancias admiten la manipulación interna de tipos más o menos concretos. Por eso ves en el ejemplo que algunas funciones retornan el tipo esperado `: Observable<MyClass>`, o si no saben que tipo esperar se conforman con `: Observable<any>`.

En cualquier caso, toda operación asíncrona retornará una instancia observable a la cual habrá que subscribirse para recibir los datos o los errores, cuando termine. Aunque a veces no se verá el `subscribe()`

#### Async

Para probar otras formas de presentar datos recibidos desde un API, voy a crear un nuevo componente. El `ObseratesComponent` mezcla de observables y rates:

```terminal
ng generate component 6-http/rates/obserates
```

Y en su vista HTML usaré una función propia de Angular llamada `async`. Dicha función actúa como un *pipe* en una expresión. Igual que el `| json` pero a su izquierda espera que le den algo a lo que suscribirse; espera un observable:

```html
<h2> Currency Observable Rates. </h2>
<h3> From Euro to the $ world </h3>
<pre>{{ currentEuroRates$ | async | json }}</pre>}
```

En este caso uso la propiedad `currentEuroRates$` finalizada en `$` por convenio. Esa propiedad se rellena en el controlador con el método `get`, no con los datos futuros, si no con el propio observable:

```typescript
private ratesApi
  = 'https://api.exchangeratesapi.io/latest';
public currentEuroRates$: Observable<any> = null;

constructor(private httpClient: HttpClient) {}

ngOnInit() {
  this.getCurrentEuroRates();
}

private getCurrentEuroRates() {
  const currencies = 'USD,GBP,CHF,JPY';
  const url = `${this.ratesApi}?symbols=${currencies}`;
  this.currentEuroRates$ = this.httpClient.get(url);
}
```

> Al utilizar el *pipe async* ya no es necesaria la suscripción en código. La propia función del framework se ocupa de ello. Por tanto la llamada se realiza igualmente aunque no veamos la suscripción.

Esta es la manera recomendada de consumir datos desde un API. Definir la llamada en el controlador y pasarle el observable a la vista para que lo muestre cuando obtenga los datos.

#### Pipe

Los datos devueltos raramente vienen en el formato preciso para usar en la vista. Con frecuencia hay que transformarlos al vuelo en cuanto se reciben. Recordemos que `HttpClient` no devuelve los datos tal cual sino un stream de estados de dichos datos. La manipulación será sobre el stream no directamente sobre los datos; y, claro, para manipular un torrente hay que encauzarlo en tuberías.

Aquí es donde aparece el método `.pipe(operator1, operator2...)` aplicado a un observable. Suele hacerse en lugar, o antes, del `.susbcribe(okCallback, errCallback)`. Este método canaliza una serie de operadores predefinidos que manipulan el chorro de estados observados.

El operador más utilizado es `map(sourceStream => targetStream)`. Este operador recibe una función callBack que será invocada ante cada dato recibido. Esa función tienen que retornar un valor para sustituir al actual y así transformar el contenido del chorro.

```typescript
public myRates$: Observable<any[]> = null;
private getCurrentEuroRates() {
  const url = `${this.ratesApi}?symbols=USD,GBP,CHF,JPY`;
  this.currentEuroRates$ = this.httpClient.get(url);
  this.myRates$ = this.currentEuroRates$.pipe(map(this.transformData));
}
private transformData(currentRates) {
  const current = currentRates.rates;
  return Object.keys(current).map(key => ({
    date: currentRates.date,
    currency: key,
    euros: current[key]
  }));
}
```

> En este ejemplo partimos de nuevo de un objeto recibido y lo queremos ver como un *array* de objetos. Para ello lo transformamos usado el operador `map`. Este operador ha de importarse de `rxjs/operators` y aplicarse a un observable dentro de su método `.pipe()`. Es el más sencillo y uno de los más utilizados: recibe y emite datos dentro de un stream de eventos observables. Nada que ver, salvo el nombre, con la sencilla función `array.map(callback)`, que recibe y devuelve datos estáticos.

```html
<pre>{{ myRates$ | async | json }}</pre>
```

#### Operators

El código anterior funciona, pero resulta que al haber dos funciones `async` suscritas provoca que la llamada original se realice dos veces. Esto es así porque el segundo observable `myRates$` es una canalización del primer `currentEuroRates$`.

Estos y otros problemas se solucionan usando operadores. Vamos a conocer un par de ellos más y veremos como `pipe(op1, op2, opn)` los ejecuta a todos en orden.

El operador `share()` permite compartir el resultado de una primera llamada con subsiguientes suscriptores. Evitando de ese modo la repetición de costosas peticiones http.

```typescript
private getCurrentEuroRates() {
const url = `${this.ratesApi}?symbols=USD,GBP,CHF,JPY`;
  this.currentEuroRates$ = this.httpClient.get(url)
      .pipe(share());
  this.myRates$ = this.currentEuroRates$
      .pipe(
        tap(d=>console.log(d)),
        map(this.transformData),
        tap(t=>console.log(t))
      );
}
```

> El operador `tap(callback)` es similar en nombre al `map()`. Pero la gran diferencia es que está pensado para no manipular los datos que recibe. Los usa y puede causar otros efectos colaterales, pero nunca modifica el propio stream. Es muy utilizado para inspeccionar o auditar el flujo de otros operadores.

### Interceptores

Los interceptores tienen un nombre intimidante pero un propósito sencillo y muy útil: **interceptar todas las comunicaciones http** y ejecutar código personalizado para cada uno. Por ejemplo un gestor centralizado de errores http o el control de los tokens de seguridad de la aplicación.

Pero antes de eso habrá que aprender unos conceptos básicos. Vamos a ver un ejemplo sencillo que audite todas las llamadas http. Todo empieza con un servicio:

```terminal
ng generate service rates/AuditInterceptor
```

#### La interfaz 'HttpInterceptor'

Al servicio genérico recién creado hay que hacerle cumplir una interfaz `HttpInterceptor` que viene con `HttpClientModule`. Esta interfaz solo necesita un método, el `intercept(req, next)` pero sus tipos e implementación mínima la hacen complicada de entender a la primera:

```typescript
import { HttpEvent, HttpHandler, HttpInterceptor, HttpRequest }
  from '@angular/common/http';
import { Injectable } from '@angular/core';
import { Observable } from 'rxjs';

@Injectable({
  providedIn: 'root'
})
export class AuditInterceptorService implements HttpInterceptor {
  public intercept( req: HttpRequest<any>, next: HttpHandler )
    : Observable<HttpEvent<any>> {
    return next.handle(req);
  }

  constructor() { }
}
```

Todo este código para nada. Porque eso es lo que hace, nada. Eso sí, tampoco rompe ni bloquea nada. Vayamos por partes, primero los parámetros, luego el tipo de la respuesta y por último la implementación:

* `req: HttpRequest<any>` -> puntero a la petición en curso
* `next: HttpHandler` -> puntero a la siguiente función que maneje la petición
* `: Observable<HttpEvent<any>>` -> retornamos un stream de eventos http para cada petición
* `return next.handle(req);` -> que el siguiente procese la petición, sin hacerle nada en absoluto

#### Inversión de control vía token

Tenemos un servicio que cumple una interfaz compleja. Pero dicho servicio debe ser proveído en algún módulo antes de ser reclamado como dependencias por alguien. Pero ¿por quién?

Técnicamente lo necesita el propio `HttpClient` del framework. Pero, obviamente, no pueden reclamar por tipo una clase que acabo de inventarme yo. Adelante con **la inversión del control**.

Realmente `HttpClient` depende de algo que por convenio llaman token de tipo *HTTP_INTERCEPTORS*. Nuestro trabajo consiste en que cuando reclame su dependencia, le demos la nuestra. El típico gato por liebre. Así en nuestro módulo pondremos la siguiente configuración:

```typescript
providers: [
  {
    provide: HTTP_INTERCEPTORS,
    useClass: AuditInterceptorService,
    multi: true
  }
]
```

El parámetro `multi:true` en este caso le indica que puede haber más de un interceptor. Concretamente debe añadirlo a la lista y admitir más. Hecho esto, sobraría el `providedIn: 'root'` autogenerado en el decorador del servicio.

#### Un auditor de llamadas

Pues ya estamos listos para aportar algo de funcionalidad. Nuestro objetivo es escribir en el log un texto para cada llamada terminada y el tiempo que le tomó. La idea es aprovechar que todo es un stream observable y canalizarlo en una tubería con una serie de operadores:

```typescript
export class AuditInterceptorService implements HttpInterceptor {
  constructor() {}

  public intercept(req: HttpRequest<any>, next: HttpHandler){
    const started = Date.now();
    return next.handle(req).pipe(
      filter((event: HttpEvent<any>) => event instanceof HttpResponse),
      tap((resp: HttpResponse<any>) => this.auditEvent(resp, started))
    );
  }

  private auditEvent(resp: HttpResponse<any>, started: number) {
    const elapsedMs = Date.now() - started;
    const eventMessage = resp.statusText + ' on ' + resp.url;
    const message = eventMessage + ' in ' + elapsedMs + 'ms';
    console.log(message);
  }
}
```

El operador `filter(any=>bool)` se usa para descartar eventos que no cumplan unos criterios. En mi caso sólo me interesan los eventos de recepción de la petición, y no necesito los intermedios. Uso de nuevo el `tap(callback)` para hacer cosas con los datos sin modificarlos en absoluto. En este caso los envío al método `auditEvent` para que lo saque por consola. Listo: un auditor para todas las llamadas.

## Vigilancia y seguridad

<https://academia-binaria.com/vigilancia-y-seguridad-en-Angular>

La vigilancia de los datos y la información en tiempo real al usuario son dos pilares del desarrollo con Angular en el lado del navegador. La seguridad de los datos realmente es una responsabilidad compartida entre el servidor y el cliente.

### Observables para monitorizar datos

Hemos visto varias técnicas para comunicar información dentro de una aplicación Angular. Empezamos por conocer el **flujo entre componentes** de una misma rama del DOM. También enviamos datos en los **parámetros de una ruta**. Y obviamente podemos usar un **servicio común** para guardar información compartida. En este caso, usarmos los **Observables** para saber cuando se actualiza la información.

Para ilustrar este tema vamos a crear un sencillo sistema de notificaciones que informe al usuario. Empezaremos creando un módulo para los propósitos de este laboratorio:

```terminal
ng generate module notifications --routing true
ng generate component notifications/sender
ng generate component notifications/receiver
```

Lo apuntamos al enrutador global `'app-routing.module.ts'` y asignamos las rutas locales:

```typescript
{
  path: 'notifications',
  loadChildren: './notifications/notifications.module#NotificationsModule'
},
```

```typescript
const routes: Routes = [
  {
    path: 'sender',
    component: SenderComponent
  },
  {
    path: 'receiver',
    component: ReceiverComponent
  },
  {
    path: '**',
    redirectTo: 'sender'
  }
];
```

Por último un enlace en el menú principal header.component.html y ya estamos listos para enviar y recibir desde dos componente desacoplados:

```html
<a routerLink="notifications" class="button">Notifications</a>
```

#### Productores de observables

La librería RxJS es enorme y Angular hace un uso extenso de ella. El tutorial anterior se ha visto desde el punto de vista del consumidor. Es decir, nos hemos suscrito a fuentes observables. Para avanzar tendremos que poder emitir, o mejor dicho producir, información.

##### 'Of' y 'from'

Los constructores más sencillos de la librería son **funciones que emiten valores estáticos o secuencias a intervalos regulares**. Para familiarizarte con ellos te propongo que juegues con código como este:

```typescript
value$ = of(new Date().getMilliseconds());
value$.subscribe(r => console.log(r));
stream$ = from([1, 'two', '***']);
stream$.subscribe(r => console.log(r));
list$ = of(['N', 'S', 'E', 'W']);
list$.subscribe(r => console.log(r));
```

##### 'Subject' y 'BehaviorSubject'

Los anteriores constructores se basan en datos estáticos. Resuelvan algunas situaciones, pero necesitamos algo que emita **cambios dinámicos**. Y eso se realiza con los *Subjects*, una especie de emisores temáticos a los que suscribirse.

Hay varios tipos pero para empezar nos vamos a fijar en dos: el `Subject()` y el `BehaviorSubject(initialData)`. La diferencia es que el primero sólo emite las cosas según ocurren. Si alguien se suscribe tarde no conocerá el pasado. Esto suele generar problemas de sincronización. El *Behavior* en cambio notifica el último valor conocido a cualquiera que se suscriba. De esa forma no importa si te suscribes antes o después de la obtención de un dato.

Juega con el siguiente ejemplo:

```typescript
const data = {name:'', value:0};

const need_sync$ = new Subject<any>();
// on time
need_sync.subscribe(r => console.log(r));
need_sync.next(data);
// too late
need_sync.subscribe(r => console.log(r));

const no_hurry$ = new BehaviorSubject<any>(this.data);
// its ok
no_hurry.subscribe(r => console.log(r));
no_hurry.next(data);
// its also ok
no_hurry.subscribe(r => console.log(r));
```

#### Un Store de notificaciones

Usaremos el `BehaviorSubject` como notificador principal entre componentes de Angular. Por ejemplo podemos montar un sistema de notificaciones sencillo. Empecemos por crear un servicio:

```terminal
ng generate service notifications/notificationsStore
```

> Para adaptarnos a la nomenclatura usada por patrones de gestión de estado más avanzados como es Redux, usaré el siguiente convenio: *Store* como almacén, `select$()` como publicador de cambios observable y *dispatch* como encargado de procesar una acción de cambio de estado.

```typescript
export class NotificationsStoreService {
  private notifications = [];

  private notifications$ = new BehaviorSubject<any[]>([]);

  constructor() {}

  public select$ = () => this.notifications$.asObservable();

  public dispatch(notification) {
    this.notifications.push(notification);
    this.notifications$.next([...this.notifications]);
  }
}
```

Este servicio es la implementación más sencilla posible de un gestor de estados. Cabe destacar que :

* Mantienen el estado privado para evitar manipulaciones
* Recibe de forma controlada las acciones de cambio
* Emite clones del estado
* Expone observables para que se suscriban los interesados.

#### Desacoplados pero conectados

Una vez que hemos centralizado el control de cambios de una parte de la aplicación, es hora de que lo usen los componentes o servicios involucrados. Solo necesitan recibir la instancia vía dependencia. **No hay más acoplamiento entre emisores y receptores**.

##### Emisión

Veamos un ejemplo, un tanto forzado, consistente en dos componentes que se comunican sin conocerse. Esta es la vista con un formulario para enviar mensajes:

```html
<h2>
  Notes sender
</h2>
<form>
  <fieldset>
    <section>
      <label for="note">Note</label>
      <input name="note" (ngModel)]="note" />
    </section>
  </fieldset>
  <button (click)="send()">Send</button>
</form>
<a [routerLink]="['../receiver']">Go to receiver</a>
```

La parte interesante está en el controlador. Dependencia y uso del servicio del almacén de notificaciones:

```typescript
export class SenderComponent implements OnInit {
  public note = '';

  constructor(private notificationsStore: NotificationsStoreService) {}

  ngOnInit() {}

  public send() {
    this.notificationsStore.dispatch(this.note);
  }
}
```

##### Recepción

La recepción es igual de sencilla. En la vista pondremos un listado de notificaciones que se alimenta de un array emitido por un observable:

```html
<h2>Notes receiver</h2>
<ul>
  <li *ngFor="let note of notes$ | async">{{ note | json }}</li>
</ul>
<a [routerLink]="['../sender']">Go to sender</a>
```

Y en el controlador reclamamos la misma dependencia para el uso del servicio del almacén de notificaciones:

```typescript
export class ReceiverComponent implements OnInit {
  public notes$;

  constructor(private notificationsStore: NotificationsStoreService) {}

  ngOnInit() {
    this.notes$ = this.notificationsStore.select$();
  }
}
```

Es importante recalcar que **no importa el orden de suscripción**. Estos dos componentes podrían vivir en módulos distintos, verse en la misma página o inicializarse en cualquier orden. El receptor se entera siempre de todos los cambios y además recibe el último estado conocido nada más suscribirse.

### Interceptores para gestionar errores

Hemos conocido a los interceptores y vemos su potencial para manipular las respuestas de una API. Quizá uno de los usos más frecuentes se el de **centralizar la gestión de errores**. Veamos como hacerlo usando el conocimiento de los observables.

Para empezar hay que generar un servicio:

```terminal
ng generate service notifications/errorInterceptor
```

Luego hay que hacerle cumplir la interfaz `HttpInterceptor`:

```typescript
export class ErrorInterceptorService implements HttpInterceptor {
  constructor() {}

  public intercept(req: HttpRequest<any>, next: HttpHandler)
    : Observable<HttpEvent<any>> {
    return next.handle(req);
  }
}
```

Para finalizar lo proveemos hacia el `HttpClient` invirtiendo el control:

```typescript
@NgModule({
  declarations: [SenderComponent, ReceiverComponent],
  imports: [
    CommonModule,
    NotificationsRoutingModule,
    HttpClientModule,
    FormsModule
  ],
  providers: [
    {
      provide: HTTP_INTERCEPTORS,
      useClass: ErrorInterceptorService,
      multi: true
    }
  ]
})
export class NotificationsModule {}
```

#### El operador 'catchError'

Volvemos a los observables y los operadores canalizables en `.pipe()`. Durante su ejecución un stream de observables puede emitir valores correctos, una señal de finalización… y cómo no, errores. El método `.subscribe(ok, err, end)` y operadores como `.map(ok, err, end)` admiten hasta tres callbacks que se llamarán según los tipos de sucesos descritos. Pero para tratar el caso concreto de los errores vamos a ver el operador `catchError()`.

Por ejemplo durante la intercepción de respuestas podemos realizar una función específica al recibir un código de error. Dadas estas tres alternativas, escogeremos según la intención o la tecnología que más nos guste:

```typescript
public intercept(req, next) {
   // implementación con .tap()
   return next.handle(req).pipe(tap(null, err=>console.log(err)));
   // implementación con catchError retornando nulo
   return next.handle(req).pipe(catchError(err => of(null)));
   // implementación con catchError re-lanzando el error
   return next.handle(req).pipe(catchError(err => throwError(err)));
}
```

#### Gestión centralizada de errores

Quizás una de las más usadas sea auditar el error y reenviarlo al llamante original por si quiere hacer algo más con el mismo.

```typescript
public intercept(req, next) {
  return next.handle(req).pipe(catchError(this.handleError));
}

private handleError(err) {
  const unauthorized_code = 401;
  let userMessage = 'Fatal error';
  if (err instanceof HttpErrorResponse) {
    if (err.status === unauthorized_code) {
      userMessage = 'Authorization needed';
    } else {
      userMessage = 'Comunications error';
    }
  }
  console.log(userMessage);
  return throwError(err);
}
```

Pero aún mejor que solo escribir en el log, sería avisar al usuario; ¿pero dónde y cómo?

### Un notificador de problemas

La idea es usar el `NotificationsStoreService` desde el interceptor para notificar que ha habido un error.

#### Emisión mediante el Store

```typescript
// dependencia en el constructor
constructor(private notificationsStore: NotificationsStoreService) {}

public intercept(req, next) {
  // Ojo al bind(this), necesario para no perder el contexto
  return next.handle(req).pipe(catchError(this.handleError.bind(this)));
}

private handleError(err) {
  let userMessage = 'Fatal error';
  // emisión de la notificación
  this.notificationsStore.dispatch(userMessage);
}
```

#### Recepción desacoplada del interceptor

Y ahora ya sólo queda suscribirse a los eventos y mostrarlos al usuario. Por ejemplo, desde el `ReceiverComponent`, podemos lanzar llamadas que sabemos que darán problemas y esperar pacientemente el fallo para mostrarlo al usuario:

```html
<button (click)="forceError()">Force http Error</button>
```

```typescript
public forceError() {
  const privateUrl = 'https://api-base.herokuapp.com/api/priv/secrets';
  this.httpClient.get(privateUrl).subscribe();
  const notFoundUrl = 'https://api-base.herokuapp.com/api/pub/items/9';
  this.httpClient.get(notFoundUrl).subscribe();
}
```

Tenemos ahora a nuestro usuario puntualmente informado de todo lo que sucede. Hemos utilizado **patrones de arquitectura de software** como el observable y la inversión del control. El resultado es una serie de componentes y servicios poco acoplados que intercambian información en tiempo real.

## Formularios reactivos

<https://academia-binaria.com/formularios-reactivos-con-Angular/>

El **doble enlace automático** entre elementos html y propiedades de objetos fue el primer gran éxito de Angular. Ese **doble-binding** facilita mucho el desarrollo de formularios. Pero esa magia tienen un coste en escalabilidad; impacta en el tiempo de ejecución y además dificulta la validación y el mantenimiento de formularios complejos.

La solución en Angular 7 pasa por desacoplar el modelo y la vista, introduciendo una capa que gestione ese doble enlace. Los servicios y directivas del módulo `ReactiveFormsModule` que viene en la librería `@angular/forms` permiten programar formularios reactivos conducidos por el código.

### Desacople entre vista y modelo

La directiva `[(ngModel)]="model.property"` con su popular *'banana in a box'* establece el doble enlace entre el elemento de la vista al que se le aplica y una propiedad del modelo. Los cambios en la vista son trasladados automáticamente al modelo, y al revés; cualquier cambio en el modelo se refleja inmediatamente en la vista.

Se pueden establecer validaciones y configurar los eventos que disparan las actualizaciones; pero todo ello usando más y más atributos y directivas en la plantilla. Son los formularios *'template driven'* que degeneran en un html farragoso y difícil de mantener.

Vamos a crear un formulario de registro de usuarios usando los formularios *'model driven'*. Para ello voy a crear el módulo `security` con el componente `register` y los engancharé a la ruta `security/register`:

```terminal
ng generate module security --routing true
ng generate component security/register
```

```typescript
{
  path: 'security',
  loadChildren: './security/security.module#SecurityModule'
},
```

El componente de registro y su ruta asignada:

```typescript
const routes: Routes = [
  {
    path: 'register',
    component: RegisterComponent
  },
  {
    path: '**',
    redirectTo: 'register'
  }
];
```

```html
<a routerLink="security/register" class="button">Register</a>
```

#### 'Form buider'

Entra en acción el `FormBuilder`, un servicio del que han de depender los componentes que quieran desacoplar el modelo de la vista. Se usa para construir un formulario creando un `FormGroup` (un grupo de controles) que realiza un seguimiento del valor y estado de cambio y validez de los datos.

Para poder usarlo tenemos que importar el módulo de Angular en el que viene declarado, el `ReactiveFormModule`:

```typescript
import { ReactiveFormsModule } from '@angular/forms';
@NgModule({
  declarations: [RegisterComponent],
  imports: [
    CommonModule,
    SecurityRoutingModule,
    ReactiveFormsModule
  ]
})
export class SecurityModule { }
```

Veamos un ejemplo mínimo de su declaración en `'register.component.ts'`:

```typescript
export class RegisterComponent implements OnInit {
  public formGroup: FormGroup;

  constructor( private formBuilder: FormBuilder ) { }

  public ngOnInit() {
    this.buildForm();
  }
  private buildForm(){
    this.formGroup = this.formBuilder.group({});
  }
}
```

#### 'Form control'

El formulario se define como un **grupo de controles**.** Cada control tendrá un nombre y una configuración. Esa definición permite establecer un valor inicial al control:

```typescript
private buildForm() {
  const dateLength = 10;
  const today = new Date().toISOString().substring(0, dateLength);
  const name = 'JOHN DOE';
  this.formGroup = this.formBuilder.group({
    registeredOn: today,
    name: name.toLowerCase(),
    email: 'john@angular.io',
    password: ''
  });
}
```

Como ves, es fácil asignar valores por defecto. Incluso es un buen momento para modificar o transformar datos previos para ajustarlos a cómo los verá el usuario; sin necesidad de cambiar los datos de base.

#### 'Form view'

Este trabajo previo y extra que tienes que hacer en el controlador se recompensa con una mayor limpieza en la vista html. Lo único necesario será asignar por nombre el elemento html con el control typescript que lo gestionará.

Para ello usaremos dos directivas que vienen dentro del módulo reactivo como son `[formGroup]="objetoFormulario"` para el formulario en su conjunto y `formControlName="nombreDelControl"` para cada control:

```html
<form [formGroup]="formGroup">
  <label for="registeredOn">Registered On</label>
  <input name="registeredOn" formControlName="registeredOn" type="date" />
  
  <label for="name">Name</label>
  <input name="name" formControlName="name" type="text" />
  
  <label for="email">E-mail</label>
  <input name="email" formControlName="email" type="email" />
  
  <label for="password">Password</label>
  <input name="password" formControlName="password" type="password" />
</form>
```

### Validación y estados

La validación es una pieza clave de la entrada de datos en cualquier aplicación. Es el primer frente de defensa ante errores de usuarios; ya sean involuntarios o deliberados.

Dichas validaciones se solían realizar agregando atributos html tales como el archiconocido `required`. Pero todo eso ahora se traslada a la configuración de cada control, donde podrás establecer una o varias reglas de validación sin mancharte con html.

#### Validadores predefinicos y personalizados

De nuevo tienes distintas sobrecargas que te permiten resolver limpiamente casos sencillos de una sola validación, o usar baterías de reglas que vienen predefinidas como funciones en el objeto `Validators` del framework:

```typescript
private buildForm() {
  const dateLength = 10;
  const today = new Date().toISOString().substring(0, dateLength);
  const name = 'JOHN DOE';
  const minPassLength = 4;
  this.formGroup = this.formBuilder.group({
    registeredOn: today,
    name: [name.toLowerCase(), Validators.required],
    email: ['john@angular.io', [
      Validators.required, Validators.email
    ]],
    password: ['', [
      Validators.required, Validators.minLength(minPassLength)
    ]]
  });
}
```

A estas validaciones integradas se puede añadir otras creadas por el programador. Incluso con ejecución asíncrona para validaciones realizadas en el servidor.

Por ejemplo podemos agregar una validación específica a las contraseñas:

```typescript
password: ['', [
  Validators.required,
  Validators.minLength(minPassLength),
  this.validatePassword
]]
```

Lo único que se necesita es una función que recibe como argumento el control a validar. El resultado debe ser un `null` si todo va bien. Y cualquier otra cosa en caso de fallo. Te muestro una propuesta para que puedas crear tus propios validadores:

```typescript
private validatePassword(control: AbstractControl) {
  const password = control.value;
  let error = null;
  if (!password.includes('$')) {
    error = { ...error, dollar: 'needs a dollar symbol' };
  }
  if (!parseFloat(password[0])) {
    error = { ...error, number: 'must start with a number' };
  }
  return error;
}
```

#### Estados de cambio y validación

Una vez establecidas las reglas, es hora de aplicarlas y avisar al usuario en caso de que se incumplan. Los formularios y controles reactivos están gestionados por máquinas de estados que determinan en todo momento la situación de cada control y del formulario en si mismo.

##### Estados de validación

Al establecer una o más reglas para uno o más controles activamos el sistema de chequeo y control del estado de cada control y del formulario en su conjunto.

La máquina de estados de validación contempla los siguientes estados mutuamente excluyentes:

* **VALID**: el control ha pasado todos los chequeos
* **INVALID**: el control ha fallado al menos en una regla.
* **PENDING**: el control está en medio de un proceso de validación
* **DISABLED**: el control está desactivado y exento de validación

Cuando un control incumple con alguna regla de validación, estas se reflejan en su propiedad `errors` que será un objeto con una propiedad por cada regla insatisfecha y un valor o mensaje de ayuda guardado en dicha propiedad.

##### Estados de modificación

Los controles, y el formulario, se someten a otra máquina de estados que monitoriza el valor del control y sus cambios.

La máquina de estados de cambio contempla entre otros los siguientes:

* **PRINSTINE**: el valor del control no ha sido cambiado por el usuario
* **DIRTY**: el usuario ha modificado el valor del control.
* **TOUCHED**: el usuario ha tocado el control lanzando un evento blur al salir.
* **UNTOUCHED**: el usuario no ha tocado y salido del control lanzando ningún evento blur.

Como en el caso de los estados de validación, el formulario también se somete a estos estados en función de cómo estén sus controles.

Veamos su aplicación primero en el caso general del formulario. Uno de los usos más inmediatos es deshabilitar el botón de envío cuando la validación de algún control falla:

```html
<button (click)="register()" [disabled]="formGroup.invalid">Register me!</button>
```

Por cierto, este sistema de gestión de los controles del formulario oculta la parte más valiosa (el valor que se pretende almacenar) en la propiedad `value` del formulario. Contendrá un objeto con las mismas propiedades usadas durante la definición del formulario, cada una con el valor actual del control asociado.

```typescript
public register() {
  const user = this.formGroup.value;
  console.log(user);
}
```

La validación particular para cada control permite informar al usuario del fallo concreto. Es una buena práctica de usabilidad el esperar a que edite un control antes de mostrarle el fallo. Y también es muy habitual usar la misma estrategia para cada control.

Lo que no queremos es llevar de vuelta la lógica a la vista; así que lo recomendado es crear una función auxiliar para mostrar los errores de validación:

```typescript
public getError(controlName: string): string {
  let error = '';
  const control = this.formGroup.get(controlName);
  if (control.touched && control.errors != null) {
    error = JSON.stringify(control.errors);
  }
  return error;
}
```

En la vista colocaremos adecuadamente los mensajes para facilitarle la corrección al usuario:

```html
<span>{{ getError('name')}}</span>
<span>{{ getError('email')}}</span>
<span>{{ getError('password')}}</span>
```

Ya tenemos formularios reactivos conducidos por los datos que te permitirán construir pantallas complejas manteniendo el control en el modelo y dejando la vista despejada. La ventaja del desacople es que podremos controlar lo que enviamos y recibimos de la vista. Así se pueden aplicar formatos, validaciones y transformaciones entre lo que presentamos y lo que enviamos hacia los servicios.

## License

[![Licencia de Creative Commons](https://i.creativecommons.org/l/by-sa/4.0/80x15.png)](http://creativecommons.org/licenses/by-sa/4.0/)
Esta obra está bajo una [licencia de Creative Commons Reconocimiento-Compartir Igual 4.0 Internacional](http://creativecommons.org/licenses/by-sa/4.0/).
