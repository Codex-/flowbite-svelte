<script lang="ts">
	import type { LinkType, ImgType, Colors } from '../types';
	let isOpen: boolean = true;
	const toggleDropdown = () => {
		isOpen = !isOpen;
	};

	export let dropdownLinks: LinkType[];
	export let img: ImgType;
	export let header: string = 'Lorem ipsum';
	export let content: string = 'Proin efficitur purus felis.';
	export let buttonColor: Colors = 'blue';
	export let link1: LinkType;
	export let link2: LinkType;
	export let headerClass: string = 'mb-1 text-xl font-medium text-gray-900 dark:text-white';
	export let divClass: string = 'max-w-sm bg-white rounded-lg border border-gray-200 shadow-md dark:bg-gray-800 dark:border-gray-700';
	let linkClass: string = 'inline-flex items-center py-2 px-4 text-sm font-medium text-center text-white focus:ring-4 ';
	
	if (buttonColor === 'gray') {
		linkClass += 'bg-gray-700 rounded-lg hover:bg-gray-800 focus:ring-gray-300 dark:bg-gray-600 dark:hover:bg-gray-700 dark:focus:ring-gray-800';
	} else if (buttonColor === 'red') {
		linkClass += 'bg-red-700 rounded-lg hover:bg-red-800 focus:ring-red-300 dark:bg-red-600 dark:hover:bg-red-700 dark:focus:ring-red-800';
	} else if (buttonColor === 'yellow') {
		linkClass += 'bg-yellow-700 rounded-lg hover:bg-yellow-800 focus:ring-yellow-300 dark:bg-yellow-600 dark:hover:bg-yellow-700 dark:focus:ring-yellow-800';
	} else if (buttonColor === 'green') {
		linkClass += 'bg-green-700 rounded-lg hover:bg-green-800 focus:ring-green-300 dark:bg-green-600 dark:hover:bg-green-700 dark:focus:ring-green-800';
	} else if (buttonColor === 'indigo') {
		linkClass += 'bg-indigo-700 rounded-lg hover:bg-indigo-800 focus:ring-indigo-300 dark:bg-indigo-600 dark:hover:bg-indigo-700 dark:focus:ring-indigo-800';
	} else if (buttonColor === 'purple') {
		linkClass += 'bg-purple-700 rounded-lg hover:bg-purple-800 focus:ring-purple-300 dark:bg-purple-600 dark:hover:bg-purple-700 dark:focus:ring-purple-800';
	} else if (buttonColor === 'pink') {
		linkClass += 'bg-pink-700 rounded-lg hover:bg-pink-800 focus:ring-pink-300 dark:bg-pink-600 dark:hover:bg-pink-700 dark:focus:ring-pink-800';
	} else {
		linkClass += 'bg-blue-700 rounded-lg hover:bg-blue-800 focus:ring-blue-300 dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800';
	}
</script>

<div class={divClass}>
	<div class="flex justify-end px-4 pt-4 relative">
		<button id="dropdownButton" on:click={toggleDropdown} class="hidden sm:inline-block text-gray-500 dark:text-gray-400 hover:bg-gray-100 dark:hover:bg-gray-700 focus:outline-none focus:ring-4 focus:outline-none focus:ring-gray-200 dark:focus:ring-gray-700 rounded-lg text-sm p-1.5" type="button">
			<svg class="w-6 h-6" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path d="M10 6a2 2 0 110-4 2 2 0 010 4zM10 12a2 2 0 110-4 2 2 0 010 4zM10 18a2 2 0 110-4 2 2 0 010 4z" /></svg>
		</button>

		<div id="dropdown" class:hidden={isOpen} class:block={!isOpen} class="hidden z-10 w-44 text-base list-none bg-white rounded divide-y divide-gray-100 shadow dark:bg-gray-700 absolute top-16 -right-16">
			<ul class="py-1" aria-labelledby="dropdownButton">
				{#each dropdownLinks as { href, name, rel }}
					<li>
						<a {href} {rel} class="block py-2 px-4 text-sm text-gray-700 hover:bg-gray-100 dark:hover:bg-gray-600 dark:text-gray-200 dark:hover:text-white">{name}</a>
					</li>
				{/each}
			</ul>
		</div>
	</div>

	<div class="flex flex-col items-center pb-10">
		<img class="mb-3 w-24 h-24 rounded-full shadow-lg" src={img.src} alt={img.alt} />
		<h3 class={headerClass}>
			{header}
		</h3>
		<span class="text-sm text-gray-500 dark:text-gray-400">{content}</span>
		<div class="flex mt-4 space-x-3 lg:mt-6">
			{#if link1.href}
				<a href={link1.href} rel={link1.rel} class={linkClass}>{link1.name}</a>
			{/if}
			{#if link2.href}
				<a href={link2.href} rel={link2.rel} class="inline-flex items-center py-2 px-4 text-sm font-medium text-center text-gray-900 bg-white rounded-lg border border-gray-300 hover:bg-gray-100 focus:ring-4 focus:ring-blue-300 dark:bg-gray-800 dark:text-white dark:border-gray-600 dark:hover:bg-gray-700 dark:hover:border-gray-700 dark:focus:ring-gray-800">{link2.name}</a>
			{/if}
		</div>
	</div>
</div>
