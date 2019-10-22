# NgxImageDisplay

Responsive image container

[![npm version](https://badge.fury.io/js/%40creativeacer%2Fngx-image-display.svg)](https://badge.fury.io/js/%40creativeacer%2Fngx-image-display)

## About
This project can be used to display images on a page.  
The following settings are available  

#### Demo  
[ngx-image-viewer](https://stackblitz.com/edit/ngx-image-viewer)

## Settings
  
Option | Default&#160;value | Description
:---:|:---:|---
columns | Auto-fit | This wil set the amount of columns to display with images. ex: 2 will provide you with 2 images next to each other.
imageminwidth | 300px | This is the minimum resolution for an image, if the containing div is 700px 2 images can be shown, if it's 500px only one image will be show ( next to each other).
zoomonhover | false | This will enable or disable the hover effect when the mouse hovers over an image.
zoomlevel | 'small' | This will set the amount of zoom that will occur if the zoomonhover is set to true. Possible settings: 'small' - 'medium' - 'large'
containerwidth | 100% | Set the width for the image display container.
containerheight | 100% | Set the height for the image display container.

## Available output

The component outputs the follow events that can be triggered on.

Event&#160;name | Description
:---:|---
onImageSelected | This will emit the image that has been selected when a user clicks on an image. ex: (onImageSelected)="function($event)"

## Installation

To install this library, run:

```bash
$ npm install @creativeacer/ngx-image-display --save
```

## Using this library

From your Angular `AppModule`:

```typescript
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';

import { AppComponent } from './app.component';

// Import the library
import { NgxImageDisplayModule } from '@creativeacer/ngx-image-display';

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,
    NgxImageDisplayModule.forRoot() // <-- Add this line
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

Once the library is imported, you can use its component in your Angular application:

```html
<!-- You can now use NgxImageDisplay component in app.component.html -->
<h1>
  {{title}}
</h1>
<ngx-image-display [images]="images" [displayconfig]="displayconfig" (onImageSelected)="logImage($event)"></ngx-image-display>
```  

### Interfaces
```typescript
DisplayConfig {
    columns?: number;
    imageminwidth?: string;  
    zoomonhover?: boolean;  
    zoomlevel?: 'small' | 'medium' | 'large';  
    containerwidth?: string;  
    containerheight?: string;  
    onclick?: Function;
}
``` 
```typescript
Image  {
    type: 'base64' | 'url';  
    imageData: baseImage | urlImage; 
} 
``` 
```typescript
baseImage ( to be implemented )  {
    value: string;  
    extension: 'jpg' | 'jpeg' | 'png' | 'svg';  
}
``` 
```typescript
urlImage  {
    value: string;  
}
``` 

## Default Settings
  
If no Display configuration is provided the default settings will be used.  



## Future development information

Here you can find some general info for contribution

### Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

### Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

### Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `--prod` flag for a production build.

### Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

### Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).

### Creating Library
Run ng g library libname

### Build npm package  
go to project folder  
ng build ngximagedisplay

### publish
npm login   
npm publish --access public

