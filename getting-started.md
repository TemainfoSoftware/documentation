---
description: >-
  Truly-UI is dedicated to providing a good development experience for
  programmers.
---

# Getting Started

## Prerequisites

We assume that you have already installed the following packages at least and are already running an AngularIO project.

* [NodeJS &gt;= 10.0.0](https://nodejs.org)
* [Angular Cli &gt;= 8.0.0](https://cli.angular.io/)
* [Angular &gt;= 8.0.0](https://angular.io/)

## Installation

1. Having NPM installation run the following command on your terminal to install it:

   ```bash
    $ npm install --save truly-ui @angular/animations @angular/cdk
   ```

2. Because NPM does not install `peerDependencies`, you should manually install the dependencies:

   ```bash
    $ npm install --save string-format ts-md5 object-path reflect-metadata
    $ npm install --save-dev @types/object-path
   ```

3. Configure styles of used font packages \(Icon Packages are already installed when running npm install truly-ui\):

   Inside the `angular.json` file add the following paths to the `styles` key

   ```text
    "styles": [
          "src/styles.css",
          ...
          "node_modules/@angular/cdk/overlay-prebuilt.css",
          "node_modules/truly-ui/css/icons/dx-icons/css/icons.scss",
          "node_modules/truly-ui/css/icons/fa-icons/css/icons.scss",
          "node_modules/truly-ui/css/icons/ion-icons/css/icons.scss",
          "node_modules/truly-ui/css/icons/animations.scss"
    ]
   ```

4. Configure CoreModule on your AppModule:

   ```typescript
   import { BrowserModule } from '@angular/platform-browser';
   import { FormsModule } from '@angular/forms';
   import { NgModule } from '@angular/core';

   import { AppComponent } from './app.component';

   import { CoreModule } from 'truly-ui'; //CoreModule

   @NgModule({
     declarations: [
       AppComponent
     ],
     imports: [
       BrowserModule,
       CoreModule.forRoot({theme: 'default'}) // Configurations
     ],
     providers: [],
     bootstrap: [AppComponent]
   })
   export class AppModule { }
   ```

   **Usage**

   The use of the components is basically the importation of the main module and the use of the directives in its application: Example is the import of the input module and its use

```typescript
import { BrowserModule } from '@angular/platform-browser';
import { FormsModule } from '@angular/forms';
import { NgModule } from '@angular/core';

import { AppComponent } from './app.component';

// Import your library, for example the InputComponent :
import { InputModule, ButtonModule, CoreModule } from 'truly-ui';//Import Modules

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,
    CoreModule.forRoot({theme: 'default'}),

    // Specify your library as an import
    InputModule,
    ButtonModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

Once your library is imported, you can use its components, directives and pipes in your Angular application:

```markup
<!-- You can now use your library component in app.component.html -->

 <tl-input
     [(ngModel)]="Many Properties"
     [iconBefore]="'ion-printer'"
     [placeholder]="'With Placeholder'"
     [textAfter]="'US'"
     [clearButton]="true"
     [autocomplete]="'off'">
 </tl-input>
```

