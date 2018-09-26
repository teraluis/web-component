# Vue Web-Components demo

*By Dennis Burger, Poort80 Amsterdam, september 2018*

This is a little demo that uses VueJS's `vue-cli` v3.x to **build** a **W3C Web-Component** from a Vue component. This custom Web-component, with a custom made up HTML-tag, can then be dropped into a (non-Vue) web page. Or any other web page that uses any framework.

## Prerequisites

* [NodeJS](https://nodejs.org/en/)
* You'll also need the `vue-cli`. After installing above NodeJS open a **Terminal** (command-line) and run:

```bash
npm i -g @vue/cli
```

This will install the [VueJS vue-cli](https://cli.vuejs.org/guide/installation.html) command-line-interface (CLI).

## Project setup

Run the usual NPM install from within this project directory to install it's dependencies.

```bash
npm install
```

## Run local VueJS development web server

For this demo we'll focus on the `src/views/Home.vue` -page. And it into a custom **W3C HTML-tag** with a JavaScript file. Run the following to start the local (hot-reloading) development web server.

```bash
npm run serve
```

Open the `src/views/Home.vue` -page (component) into a text-editor (or IDE). This VueJS component (page) will be turned into a W3C Web-component.

## Build the custom web-component

When done developing; quit the running development server by hitting `ctrl + c` on the terminal. Now run the command below to have `vue-cli` v3.x **build** this component into a W3C web-component inside the `dist/` directory.

```bash
npm run build
```

The result is a very short static `dist/demo.html` -page. With a few HTML `<script>` -tags.

```html
<script src="https://unpkg.com/vue"></script>
<script src="./my-hello-world.js"></script>

<my-hello-world></my-hello-world>
```

* The first `<script>` -line is the VueJS library loaded from a CDN.
* The second `<script>` -line is the `Home.vue` application all wrapped up into one JavaScript file.
* The third is that custom HTML-tag name you'll use for your VueJS Web-component.

## View the static HTML demo

To quickly view (or 'serve') this `dist/` directory run the command below. This will start a simple HTTP web server serving the `dist/` directory.

```bash
npm run demo
```

Open the URL mentioned in the terminal in a web browser.

## Using the Web-component

Now you can use this custom HTML-tag `<my-hello-world></my-hello-world>` along with those two `<script>` -tags inside other web pages.

This setup uses the **Shadow DOM** for self-contained components.

## More info

* [Create & Publish Web Components With Vue CLI 3](https://vuejsdevelopers.com/2018/05/21/vue-js-web-component/)
* [Shadow DOM v1: Self-Contained Web Components](https://developers.google.com/web/fundamentals/web-components/shadowdom)
