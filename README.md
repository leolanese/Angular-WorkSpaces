# Angular Workspaces (WS)

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 14.2.7.

> A workspace is a set of Angular applications and libraries. The angular.json file at the root level of an Angular workspace provides workspace-wide and project-specific (application or library) configuration defaults for build and development tools.

#### Further information

> Angular also supports workspaces with multiple projects. This type of development environment is suitable for advanced users who are developing shareable libraries, and for enterprises that use a "monorepo" development style, with a single repository and global configuration for all Angular projects - <https://angular.io/guide/file-structure>

---

## Creating a workspace

The `--createApplication=false` parameter avoids the creation of an initial application (default value is true).

```js
// create a workspace
ng new angularWorkspace --create-application=false --directory=angularWorkspace --interactive=false
```

<a href="https://ibb.co/Snn7PC9"><img src="https://i.ibb.co/Snn7PC9/angular-workspace.jpg" alt="angular-workspace" border="0"></a>

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

## Test the workspaces changes

```js
// simply change inside: `/second-app/app/app.component.html`
// instead of
<h2>Resources</h2>

// do
<h2>Resources Test second workspace (and not first)</h2>
```

<a href="https://ibb.co/HH18spL"><img src="https://i.ibb.co/HH18spL/test-Workspace-Second.jpg" alt="test-Workspace-Second" border="1"></a>

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

---
### :100: <i>Thanks!</i>
#### Now, don't be an stranger. Let's stay in touch!

##### :radio_button: linkedin: <a href="https://www.linkedin.com/in/leolanese/" target="_blank">@LeoLanese</a>
##### :radio_button: Twitter: <a href="https://twitter.com/LeoLanese" target="_blank">@LeoLanese</a>
##### :radio_button: Portfolio: <a href="https://www.leolanese.com" target="_blank">www.leolanese.com</a>
##### :radio_button: DEV.to: <a href="https://www.dev.to/leolanese" target="_blank">dev.to/leolanese</a>
##### :radio_button: Blog: <a href="https://www.leolanese.com/blog" target="_blank">leolanese.com/blog</a>
##### :radio_button: Questions / Suggestion / Recommendation: developer@leolanese.com
