# Angular Workspaces

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 14.2.7.

> A workspace is a set of Angular applications and libraries. The angular.json file at the root level of an Angular workspace provides workspace-wide and project-specific (application or library) configuration defaults for build and development tools.

## Creating a workspace

The `--createApplication=false` parameter avoids the creation of an initial application (default value is true).

```js
// create a workspace
ng new angularWorkspace --create-application=false --directory=angularWorkspace --interactive=false
```

![workspace](https://ibb.co/Snn7PC9)

```js
// Creating an application in a workspace
cd angularWorkspace
ng generate application first-app  --style=scss --routing=true
ng generate application second-app  --style=scss --routing=true
```

Now, on the root `angular.json` we will have:

```js
{
  ...
  "projects": {
    "first-app": { ... },
    "second-app": { ... },
  }
  ...
} 
```

## Create a Shared Service

> The syntax is ng generate service `service-name` and the parameter `--project` is mandatory to specify the library where to generate the service.

```js
ng generate service services/test-service --project=first-app
```

## Create a Shared 3rd party service

```js
ng add @angular/material --project=first-app
```

## Finally, run workspace

```js
ng serve --project=first-app
ng serve first-app

ng serve --project=second-app
ng serve second-app
```

## To build your application for production

```js
ng build --prod --project=first-app
```

---

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The application will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via a platform of your choice. To use this command, you need to first add a package that implements end-to-end testing capabilities.

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI Overview and Command Reference](https://angular.io/cli) page.
