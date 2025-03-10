<script lang="ts">
	import type { NavbarType } from '../types';
	import { onMount } from 'svelte';
	import NavDropdown from './NavDropdown.svelte';

	export let user: string = '';
	let pathname = '';

	onMount(() => {
		pathname = window.location.pathname;
	});

	let barHidden = true;
	const handleClickbtn = () => {
		barHidden = !barHidden;
	};

	export let sitename: string = 'Svelte Flow';
	export let logo: string = '/images/flowbite-svelte-logo-30.png';
	export let alt: string;
	export let textsize: string = 'text-sm';
	export let menus: NavbarType[];
	export let navClass: string =
		'px-2 bg-white border-gray-200 dark:bg-gray-800 dark:border-gray-700';
	const navDivClass = 'container flex flex-wrap justify-between items-center mx-auto';
	export let spanClass: string =
		'self-center text-lg font-semibold text-gray-900 whitespace-nowrap dark:text-white';
	export let buttonClass: string =
		'inline-flex justify-center items-center ml-3 text-gray-400 rounded-lg md:hidden hover:text-gray-900 focus:outline-none focus:ring-2 focus:ring-blue-300 dark:text-gray-400 dark:hover:text-white dark:focus:ring-gray-500';
	export let dropdownDiv: string =
		'z-10 w-44 text-base list-none bg-white rounded divide-y divide-gray-100 shadow dark:bg-gray-700 dark:divide-gray-600';
	export let dropdownLinkClassWithChild: string = `block py-2 px-4 ${textsize} text-gray-700 hover:bg-gray-100 dark:hover:bg-gray-600 dark:text-gray-400 dark:hover:text-white`;
	export let dropdownLinkClassWithoutChild: string = `block py-2 pr-4 pl-3  text-gray-700 border-b border-gray-100 hover:bg-gray-50 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 md:p-0 dark:text-gray-400 dark:hover:text-white dark:border-gray-700 dark:hover:bg-gray-700 md:dark:hover:bg-transparent ${textsize}`;
	export let liButtonClass: string = `flex justify-between items-center py-2 pr-4 pl-3 w-full ${textsize} font-medium text-gray-700 border-b border-gray-100 hover:bg-gray-50 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 md:p-0 md:w-auto dark:text-gray-400 dark:hover:text-white dark:focus:text-white dark:border-gray-700 dark:hover:bg-gray-700 md:dark:hover:bg-transparent`;
</script>

<nav class={navClass}>
	<div class={navDivClass}>
		<a href="/" class="flex">
			<img src={logo} {alt} />
			<span class={spanClass}>{sitename}</span>
		</a>
		<button
			on:click={handleClickbtn}
			type="button"
			class={buttonClass}
			aria-controls="mobile-menu-2"
			aria-expanded="false"
		>
			<span class="sr-only">Open main menu</span>
			<svg
				class="w-6 h-6"
				fill="currentColor"
				viewBox="0 0 20 20"
				xmlns="http://www.w3.org/2000/svg"
				><path
					fill-rule="evenodd"
					d="M3 5a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 10a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 15a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1z"
					clip-rule="evenodd"
				/></svg
			>
			<svg
				class="hidden w-6 h-6"
				fill="currentColor"
				viewBox="0 0 20 20"
				xmlns="http://www.w3.org/2000/svg"
				><path
					fill-rule="evenodd"
					d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z"
					clip-rule="evenodd"
				/></svg
			>
		</button>
		<div class="w-full md:block md:w-auto" class:hidden={barHidden} id="mobile-menu">
			<ul class="flex flex-col mt-4 md:flex-row md:space-x-8 md:mt-0 md:text-sm md:font-medium">
				{#each menus as { name, href, rel, child }}
					{#if child}
						<NavDropdown
							{liButtonClass}
							{dropdownDiv}
							{name}
							{child}
							{rel}
							{dropdownLinkClassWithChild}
						/>
					{:else}
						<li>
							<a class:active={pathname === href} {href} {rel} class={dropdownLinkClassWithoutChild}
								>{name}</a
							>
						</li>
					{/if}
				{/each}
			</ul>
			{#if user}
				<slot name="user" />
			{/if}
		</div>
	</div>
</nav>

<style>
	#mobile-menu .active {
		color: #fab534;
	}
</style>
