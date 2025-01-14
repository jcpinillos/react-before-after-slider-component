# React node before after slider component
Simple slider component for comparing images. Before and after.  This is a fork of https://github.com/smeleshkin/react-before-after-slider-component

[![screencast demo](./screencast.gif)](./screencast.gif)

## Demo
https://smeleshkin.github.io/react-before-after-slider-component/
## Build
npm run build:npm
## Basic usage
```
npm install react-node-before-after-slider-component --save
```

Then use it in your app:
```js
import React from 'react';
import ReactBeforeSliderComponent from 'react-before-after-slider-component';
import 'react-before-after-slider-component/dist/build.css';

const FIRST_IMAGE = {
  imageUrl: 'https://example.com/.../some-image.jpg'
};
const SECOND_IMAGE = {
  imageUrl: 'https://example.com/.../some-image-2.jpg'
};
/* ... */
<ReactBeforeSliderComponent
    firstImage={FIRST_IMAGE}
    secondImage={SECOND_IMAGE}
/>
/* ... */
/* or you can use a component*/

const FIRST_COMPONENT = <GatsbyImage image={firstImage.gatsbyImage} alt={firstImage.alt} />;
const SECOND_COMPONENT = <GatsbyImage image={secondImage.gatsbyImage} alt={secondImage.alt} />;

<ReactBeforeSliderComponent
    firstComponent={FIRST_COMPONENT}
    secondComponent={SECOND_COMPONENT}
/>
/* ... */
```
## Props

| Attribute                  | Required  | Type                | Default | Description                                                           
|----------------------------|---------------------------------|---------|---------|-------------------------------
| `firstImage`               | true      | Image               |         | Image object with source url. 
| `secondImage`              | true      | Image               |         | Image object with source url.
| `delimiterColor`           | false     | string              | #fff    | Custom delimiter background color. 
| `currentPercentPosition`   | false     | number              | 50      | Start delimiter position. Or also the current position, if it will change in parent.
| `className`                | false     | string              |         | Custom classname.
| `withResizeFeel`           | false     | boolean             | true    | Feeling to window resizing.
| `onReady`                  | false     | function            |         | On slider ready callback.
| `onVisible`                | false     | function            |         | On slider visible in viewport callback.
| `onChangePercentPosition`  | false     | function            |         | On delimiter position update callback. Has new position parameter.
| `feelsOnlyTheDelimiter`    | false     | function            | false   | Only the separator feels clicks. Not any zone of the component.
| `delimiterIconStyles`      | false     | React.CSSProperties |         | Custom styles of delimiter icon. E.g. for a logo. See "Custom logo example"
| `firstComponent`           | false     | ReactNode           |         | A component like GatsbyImage to use a component instead of imageUrl
| `secondComponent`          | false     | ReactNode           |         | A component like GatsbyImage to use a component instead of imageUrl

## Specific Types

```ts
interface Image {
    imageUrl: string,
    alt?: string,
}
```

## Custom logo example
```ts
// Pass this as a delimiterIconStyles property
const delimiterIconStyles = {
   width: '50px',
   height: '50px',
   backgroundSize: 'cover',
   borderRadius: 'none',
   backgroundImage: 'url(<some-path-here>)'
}

```
