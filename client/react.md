# React

React is a **Gold Standard Library** for building web client app. What that means is, react known and use by developers. React use [JSX](#jsx) for making the ui inside javascript instead of html. This way, its easier to integrate data to the ui, since its already inside javascript. React uses **Babel** to transpile JSX to vanilla javascript, because browser does not know how to interpret JSX. Instead, react create a **Virtual DOM** to run the transpiled code. React also provide [Hooks](#hooks) for **State Management** in a component.

[react.dev](https://react.dev/)

## JSX

JSX bring html into javascript with some additions. JSX can integrate data easily instead of html.

```jsx
function App() {
	const data = 'React Dev'
	return <div title="container"><h1>{data}</h1></div>
}

// After transpiled by Babel
function App() {
	const data = 'React Dev'
	return React.createElement(
		'div',
		{title: 'container'},
		React.createElement('h1',{},data)
	)
}
```

## Hooks

Hooks is a function that run every time ui updated. One use case is to hold a state in a component. React provide a number of built-in hooks, or we can create ourself. Example of built-in hook that manage a state, `useState`:

```jsx
function App() {
	const [counter,setCounter] = useState(0)
	return (
		<div>{counter}</div>
		<button onClick={()=>setCounter(counter + 1)}>Add</button>
	)
}
```

## Component

React component is a function that return a JSX. Component can be used multiple time in multiple place. We can add an attribute that can be accessed by the component as function parameter. This is callep **props**.

```jsx
function Comp({ count, title }) {
	return <div title={title}>{count}</div>
}

function App() {
	return <Comp count={9} title={"Restrict"} />
}
```

## Not Listed

- server component

## Project

One of the easy way to setup react project is using vite. Initiate vite project, then choose react as the template:
```bash
npm create vite
```

> Note: people usually tell to use `npx create-react-app`, this cli is not recommended because it have not been updated since a long time (Sep 8, 2022), a lot of security risk by using this cli.

## NextJS

React only run on the client, a.k.a browser, and does not have the ability to run script on the server. NextJS is a backend framewoek that uses react as the frontend. NextJS handle the server side rendering, routing, api, database integration, etc.