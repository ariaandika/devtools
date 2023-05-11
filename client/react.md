# React

React merupakan *Gold Standard Library* untuk membuat web client, artinya telah banyak dikenal dan digunakan para developer. React menggunakan [JSX](#JSX) untuk membuat ui dalam javascript ketimbang html. Hal ini memudahkan untuk memasukan data ke ui. React menggunakan **babel** untuk mengubah JSX menjadi vanilla javascript, karena browser tidak mengerti JSX, melainkan membuat Virtual DOM untuk menjalankan javascript yang di-*build* oleh react. React juga menyediakan [Hooks](#Hooks) untuk mengelola state (*State Management*) dalam component.

[react.dev](https://react.dev/)

## JSX

Jsx membawa html ke javascript dengan beberapa tambahan. Jsx dapat mengintegrasikan data dengan mudah dibandingkan dengan html.

```jsx
function App() {
	const data = 'React Dev'
	return <div title="container"><h1>{data}</h1></div>
}

// Setelah di build dengan babel
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

Hooks adalah function yang dijalankan setiap ui diupdate. Hal ini dapat digunakan salah satunya untuk mempertahankan state dalam component. React menyediakan beberapa built-in hook, dan kita dapat membuat hook kita sendiri. Contoh hook untuk mempertahankan state, `useState`:

```jsx
function App() {
	const [counter,setCounter] = useState(0)
	return (
		<div>{counter}</div>
		<button onClick={()=>setCounter(counter + 1)}>Tambah</button>
	)
}
```

## Component

React component adalah sebuah fungsi yang menghasilkan jsx yang bisa digunakan berulang kali. Kita dapat memasukan attribute ke component untuk diakses di dalam component sebagai **props**.

```jsx
function Comp({ count, title }) {
	return <div title={title}>{count}</div>
}

function App() {
	return <Comp count={9} title={"Restrict"} />
}
```

## Lainya

beberapa fitur yang tidak dijelaskan di sini:

- server component

## Project

Salah satu cara mudah untuk membuat react projek adalah menggunakan vite. Jalankan `npm create vite` di terminal, dan pilih React.

> Note: beberapa orang menyarankan `npx create-react-app`, projek ini tidak disarankan karena sudah lama tidak di update (Sep 8, 2022), banyak masalah keamanan yang tidak diperbaiki dibandingkan vite.

## NextJS

React hanya berjalan di client, tidak memiliki akses atau menjalankan script di server. [NextJS](#) adalah backend framework yang menggunakan react sebagai frontend framework. NextJS menangani server side rendering, routing, api, database integration, dsb.