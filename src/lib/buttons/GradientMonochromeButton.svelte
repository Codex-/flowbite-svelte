<script lang="ts">
	import type { Buttonshadows, Textsize, ButtonType } from '../types';
	export let textSize: Textsize = 'text-sm';
	export let color: Buttonshadows = 'blue';
	let btnClass: string = `focus:ring-4 font-medium rounded-lg ${textSize} px-5 py-2.5 text-center mr-2 mb-2 `;
	export let type: ButtonType = 'button';

	if (color === 'green') {
		btnClass += `text-white bg-gradient-to-r from-green-400 via-green-500 to-green-600 hover:bg-gradient-to-br focus:ring-green-300 dark:focus:ring-green-800`;
	} else if (color === 'cyan') {
		btnClass += `text-white bg-gradient-to-r from-cyan-400 via-cyan-500 to-cyan-600 hover:bg-gradient-to-br focus:ring-cyan-300 dark:focus:ring-cyan-800`;
	} else if (color === 'teal') {
		btnClass += `text-white bg-gradient-to-r from-teal-400 via-teal-500 to-teal-600 hover:bg-gradient-to-br focus:ring-teal-300 dark:focus:ring-teal-800`;
	} else if (color === 'lime') {
		btnClass += `text-gray-900 bg-gradient-to-r from-lime-200 via-lime-400 to-lime-500 hover:bg-gradient-to-br focus:ring-lime-300 dark:focus:ring-lime-800`;
	} else if (color === 'red') {
		btnClass += `text-white bg-gradient-to-r from-red-400 via-red-500 to-red-600 hover:bg-gradient-to-br focus:ring-red-300 dark:focus:ring-red-800`;
	} else if (color === 'pink') {
		btnClass += `text-white bg-gradient-to-r from-pink-400 via-pink-500 to-pink-600 hover:bg-gradient-to-br focus:ring-pink-300 dark:focus:ring-pink-800`;
	} else if (color === 'purple') {
		btnClass += `text-white bg-gradient-to-r from-purple-500 via-purple-600 to-purple-700 hover:bg-gradient-to-br focus:ring-purple-300 dark:focus:ring-purple-800`;
	} else {
		btnClass += `text-white bg-gradient-to-r from-blue-500 via-blue-600 to-blue-700 hover:bg-gradient-to-br focus:ring-blue-300 dark:focus:ring-blue-800`;
	}
</script>

<button {type} class={btnClass} {...$$restProps} on:click>
	<slot>Read more</slot>
</button>
