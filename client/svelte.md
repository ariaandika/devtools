# Svelte

Svelte combine javascript, html, and css in one svelte file as component, then it combined with other components to make web client app. Svelte has it own html templating syntax to make it easier for integrating data into the ui. Svelte also provide **Svelte Store** for advanced State Management. Svelte work as compiler to compile svelte file into vanilla javascript that can run by browser. The benefits are more performant, because svelte does not create Virtual DOM like react.

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
		name: '',
		password: ''
	}
	
	let files: FileList
	
	function add(){ counter += 1 }
	function setStore(){ store.update(e=>e+1) }
	function formSubmit() {
		// no need to `event.preventDefault()` here
	}
</script>

<div>Counter: {counter}</div>
<button on:click={add}>Add</button>

<div class="grid {props}">Store: {$store}</div>
<button on:click={setStore}>Store Set</button>

<Navbar item={iterable} />

<form on:submit|preventDefault={formSubmit}>
	<input type=text bind:value={formData.name}>
	<input type=password bind:value={formData.password}>
	<input type=file bind:files={files}>
	<button>Submit</button>
</form>

<input type=checkbox bind:checked={bindBool}>
{#if bindBool}
<div>condition true</div>
{:else}
<div>condition false</div>
{/if}

{#each iterable as elem,i (id)}
<div>Element {i} contain {elem}</div>
{:else}
<p>Iterator empty</p>
{/each}

{#await fetch('/api')}
<div>Loading....</div>
{:then res}
{@const data = res.text()}
<div>Result: {data}</div>
{:catch err}
<div>Something went wrong: {err}</div>
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

## Not Listed

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

Svelte compile svelte files to vanilla js that can be run by browser. We can also compile ourself at runtime using **Svelte API** on the server. SvelteKit uses this to add backend functionality and integrate Svelte as the frontend. SvelteKit provide server side rendering, routing, etc, by following convention so we dont have to work with Svelte API directly.