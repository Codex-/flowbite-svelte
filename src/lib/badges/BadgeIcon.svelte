<script lang="ts">
	import type { Colors, Textsize } from '../types';
	export let textSize: Textsize = 'text-xs';
	export let name: string = '';
	export let color: Colors = 'blue';

	let badgeClass: string = 'font-medium inline-flex items-center px-2.5 py-0.5 rounded mr-2 ';
	if (color === 'gray') {
		badgeClass += `bg-gray-100 text-gray-800 ${textSize} dark:bg-gray-700 dark:text-gray-300`;
	} else if (color === 'red') {
		badgeClass += `bg-red-100 text-red-800 ${textSize} dark:bg-red-700 dark:text-red-300`;
	} else if (color === 'green') {
		badgeClass += `bg-green-100 text-green-800 ${textSize} dark:bg-green-700 dark:text-green-300`;
	} else if (color === 'yellow') {
		badgeClass += `bg-yellow-100 text-yellow-800 ${textSize} dark:bg-yellow-700 dark:text-yellow-300`;
	} else if (color === 'indigo') {
		badgeClass += `bg-indigo-100 text-indigo-800 ${textSize} dark:bg-indigo-700 dark:text-indigo-300`;
	} else if (color === 'purple') {
		badgeClass += `bg-purple-100 text-purple-800 ${textSize} dark:bg-purple-700 dark:text-purple-300`;
	} else if (color === 'pink') {
		badgeClass += `bg-pink-100 text-pink-800 ${textSize} dark:bg-pink-700 dark:text-pink-300`;
	} else {
		badgeClass += `bg-blue-100 text-blue-800 ${textSize} dark:bg-blue-700 dark:text-blue-300`;
	}
</script>

<span class="{badgeClass} {$$props.class || ''}" {...$$restProps}>
	<slot />
	{name}
</span>
