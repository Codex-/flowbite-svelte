<script>
	export let size = '24';
	export let color = 'currentColor';
</script>

<svg xmlns="http://www.w3.org/2000/svg" width={size} height={size} viewBox="0 0 24 24" fill="none" stroke={color} stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class={$$props.class ? $$props.class : ''}>
	<circle cx="12" cy="5" r="3" />
	<line x1="12" y1="22" x2="12" y2="8" />
	<path d="M5 12H2a10 10 0 0 0 20 0h-3" />
</svg>
