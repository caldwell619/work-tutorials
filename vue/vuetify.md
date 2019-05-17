# Incorporating Vuetify

Vuetify is an open source library for pre-styled components. It saves time an effort by utitilizing common UI components, styled with Materialze, Google's open source CSS framework

## Installing

[Vuetify](https://vuetifyjs.com/en/getting-started/quick-start) is a Vue plugin distributed through `yarn` and `npm`

- In an existing project, level with `package.json`, run `npm i -S vuetify`
- In `main.js`, add `import Vuetify from 'vuetify'` and `Vue.use(Vuetify)`
- Add Vuetify's css file to the root component, `Root.vue`, by importing it
  - `import 'vuetify/dist/vuetify.min.css'`

Vuetify is now globally accessible throughout the application

## Usage

At the uppermost root of the project, `App.vue`, every child must be wrapped in a `v-app` tag for this to function properly. This doesn't impact usage, it just allows Vuetify to know where the root of using Vuetify components is.

To use Vuetify components, simply use them in personal components

The [docs](https://vuetifyjs.com/en/components/api-explorer) have several examples and use cases

Scroll through and find the component you want to use, copy and paste it into your template, with the corresponding script

## Testing

In order to test components with Vuetify, you must plugin and **fully mount** your component.

A step by step guide on testing Vue components utilizing the `vue/test-utils` can be found [here](https://google.com)

`vue add @vue/unit-jest`
