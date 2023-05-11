# Svelte

Svelte menggabungkan script, html, dan css dalam satu file sebagai component, lalu component tersebut digabungkan dengan component lainya untuk membuat web client app. Svelte memiliki syntax sendiri untuk mengintegrasikan data ke html. Svelte juga menyediakan **Store** untuk *State Management*. Svelte bekerja sebagai compiler menjadi vanilla javascript yang dimengerti oleh browser. Keuntunganya adalah performa yang lebih cepat karena svelte tidak membuat virtual dom seperti react setelah fase build.

[svelte.dev](https://svelte.dev/)

# Cheatsheet

Basic:

```svelte
<script lang=ts>
	import { writable } from 'svelte/store'
	import Navbar from 'Navbar.svelte'

	export let props = 'bg-red-100'
	let counter = 0
	$: double = counter * 2
	let bindBool = false
	const iterable = []
	const store = writable(0)
	let formData = {
		nama: '',
		password: ''
	}
	
	let files: FileList
	
	function tambah(){ counter += 1 }
	function setStore(){ store.update(e=>e+1) }
	function formSubmit() {
		// no need to `event.preventDefault()` here
	}
</script>

<div>Counter: {counter}</div>
<button on:click={tambah}>Tambah</button>

<div class="grid {props}">Store: {$store}</div>
<button on:click={setStore}>Store Set</button>

<Navbar item={iterable} />

<form on:submit|preventDefault={formSubmit}>
	<input type=text bind:value={formData.nama}>
	<input type=password bind:value={formData.password}>
	<input type=file bind:files={files}>
	<button>Submit</button>
</form>

<input type=checkbox bind:checked={bindBool}>
{#if bindBool}
<div>kondisi benar</div>
{:else}
<div>kondisi salah</div>
{/if}

{#each iterable as elem,i (id)}
<div>Elemen ke {i} berisi {elem}</div>
{:else}
<p>Iterator kosong</p>
{/each}

{#await fetch('/api')}
<div>Loading....</div>
{:then res}
{@const data = res.text()}
<div>Hasil: {data}</div>
{:catch err}
<div>Ada kesalahan: {err}</div>
{/await}

<style>
	div {
		background-color: red;
	}
</style>
```

Runtime:

```svelte
<script lang=ts>
	onMount(()=>{
		console.log('Component mounted')
	})
	onDestroy()
	beforeUpdate()
	afterUpdate()
	
	await tick()
	
	setContext('key', 2)
	getContext('key')
	hasContext('key')
	getAllContexts()
	
	const dispatch = createEventDispatcher();
</script>
```

## Lainya

beberapa fitur yang tidak dijelaskan di sini:

- svelte/motion
- svelte/transition
	- use:action
	- transition:fn
	- on:introstart
	- in:fn
- svelte/animate
	- animate:name
- a lot of special attributes
- `<slot>`
- list of `<svelte:special>`
- svelte/easing
- svelte/register
- Svelte API

## SvelteKit

Svelte meng-*compile* file menjadi vanilla js untuk bisa dijalankan oleh browser. Kita juga bisa meng-*compile* secara langsung menggunakan **Svelte API** di server/nodejs untuk mengintegrasikan server render atau routing. Salah satu projek yang menggunakan ini adalah SvelteKit, dibuat oleh pembuat svelte sendiri. SvelteKit menyediakan beberapa fitur backend menggunakan svelte sebagai frontend.