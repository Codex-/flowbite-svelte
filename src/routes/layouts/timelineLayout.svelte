<script>
	import Htwo from '../utils/Htwo.svelte';
	import 'prism-themes/themes/prism-holi-theme.css';
	import { Responsive } from 'svelte-sidebar-menu';
</script>

<Responsive />
<div class="max-w-3xl mx-auto mt-16">
	<div class="container flex flex-wrap mx-auto">
		<slot />

		<Htwo label="Related components" />
		<div class="related-components">
			<p>
				<a href="/timelines/default" class="link">Default timeline</a>
			</p>

			<p>
				<a href="/timelines/vertical/" class="link">Vetical timeline</a>
			</p>

			<p>
				<a href="/timelines/horizontal" class="link">Horizontal timeline</a>
			</p>

			<p>
				<a href="/timelines/activity" class="link">Activity log</a>
			</p>

			<p>
				<a href="/timelines/group" class="link">Grouped timeline</a>
			</p>
		</div>
		<Htwo label="References" />
		<div class="references">
			<p>
				<a href="https://flowbite.com/docs/components/timeline/" target="_blank" class="link"
					>Flowbite timeline</a
				>
			</p>
		</div>
	</div>
</div>

<style>
	.link {
		color: #f83c00;
	}
	.link:hover {
		color: #fc7146;
		text-decoration: underline;
	}
</style>
