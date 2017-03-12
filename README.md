# Personal Notes
## Steps to create Angular project (requires node/npm)
1. install angular cli by running `npm i -g @angular/cli`
2. scaffold the app by running `ng new app-name`
    - use `ng g component component-name -m module-name --spec false --prefix false` to generate and register a component
3. use `ng serve` to run the dev server on [http://localhost:4200](http://localhost:4200)
4. Basic bindings:
    - `[childProperty]="parentProperty"` binds `@Input` property `childProperty` on the child component to the class property `parentProperty` on the parent component
    - `(childProperty)="parentFnHandler($event)"` binds `@Output` property `childProperty` on the child component to the `parentFnHandler()` function on the parent
    - `#varName` on the child component gives a reference to that component/class so the parent can call functions `(click)="varName.fnName()"` or read properties
4. if the object may be null when trying to access its property use the safe navigation operator `?` as in `{{couldBeNull?.propertyName}}`
5. Structural directives begin with an astrik `*` and add/remove elements from the dom
    - `*ngFor="let event of events"` loops over collections
    - `*ngIf="event?.location"` if the event object has a location property include the element and its children in the DOM
        - if element visibility changes frequenty it may be better to simple hide the element by binding to the hidden property `[hidden]="event?.location"`
    - `[ngSwitch]="event?.time"` in the parent component will look for `*ngSwitchCase="valueExpression"` or `*ngSwitchDefault` in child components
6. Dynamically apply styles using the `[ngClass]=""` syntax
    - `[ngStyle]={{style1: booleanExp1  ? 'trueValue' : 'falseValue', style2: booleanExp2 ? 'trueValue' : 'falseValue'}}` works the same way


# FirstAngularApp

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 1.0.0-rc.1.

## Development server
Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive/pipe/service/class/module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `-prod` flag for a production build.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).
Before running the tests make sure you are serving the app via `ng serve`.

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).
