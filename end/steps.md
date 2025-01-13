## Setup Project

```bash
npm i -g @angular/cli@19
ng new my-app --style scss --skip-tests --defaults
cd my-app
```

## Add Angular Material

```bash
ng add @angular/material@19
```

Answer the questions as below:

```bash
? Choose a prebuilt theme name, or "custom" for a custom theme: Custom
? Set up global Angular Material typography styles? Yes
? Include the Angular animations module? Include and enable animations
```

## Generate demo components

```bash
ng generate @angular/material:navigation navigation
ng generate @angular/material:dashboard dashboard
ng generate @angular/material:address-form address-form
ng generate @angular/material:table table
```

## Add ng-content in navigation component

## Add slide toggle in toolbar

```html
<p class="theme-toggle">
    <mat-icon>light_mode</mat-icon>
    <mat-slide-toggle (change)="onThemeChange($event)"></mat-slide-toggle>
    <mat-icon>dark_mode</mat-icon>
</p>
```

```scss
.theme-toggle {
  margin-left: auto;
  display: flex;
  align-items: center;
  justify-content: center;
}
```

## Add dark class in body when toggle changes

```ts
onThemeChange(event: MatSlideToggleChange) {
    this.document.body.classList.toggle('dark');
}
```

## Import everything in App component

```html
<app-navigation>
  <app-dashboard></app-dashboard>
  <app-address-form></app-address-form>
  <app-table></app-table>
</app-navigation>
```