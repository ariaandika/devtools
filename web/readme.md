# Web Client

Web Client is an app that run in the client (in the web context, browser). Web client uses HTML for the ui, CSS to style the ui, and Javascript to run the actual logic of the application.

## Javascript

Javascript is a language that can be used to add interactivity to the html through Document Object Model. Javascript can also uses browser feature through Web API.

Typescript is a superset of javascript. Typescript add *type system* on top of javascript. Typescript cannot run anywhere, instead it compile back to javascript where it can be run by js interpreter.

A couple library to make web client application in javascript:

- [React](./react.md)

  React is a **Gold Standard Library** for building web client app. What that means is, react known and use by developers. React use [JSX](./react.md#jsx) to define the ui inside javascript instead of html, make it easier to integrate data to the ui. React uses **Babel** to transpile JSX to vanilla javascript, because browser does not know how to interpret JSX, then it run in react's **Virtual DOM**. React also provide **Hooks** for **State Management** in a component.

 React does not provide complete web development feature, instead rely on open source community:

- React Router, client side routing for react spa
- Mantine
- React-Redux, react's state management

- [Svelte](./svelte.md)

 Svelte combine javascript, html, and css in one `.svelte` file as component, then it combined with other components to make web client app. Svelte has it own html templating syntax to make it easier for integrating data into the ui. Svelte also provide **Svelte Store** for Reactivity. Svelte work as compiler to compile svelte file into vanilla javascript that can run in the browser. The benefits are more performant, because svelte does not create Virtual DOM like react.

## CSS

CSS used for styling html. But, css lack programatic features like condition, loop, etc. So there is libraries that integrate it:

- Talwindcss, provide css properties as html class
- Bootstrap, provide a ready to use component like button, form, table, grid, etc
- Sass, add proramatic feature like condition, loop, array, etc
- Postcss, add css boilerplace like `-moz-` for compatibility
