<script lang="ts">
	import type { LinkType, SiteType } from '../types';
	export let site: SiteType;
	export let links: LinkType[];
	export let footerClass: string = 'p-4 bg-white rounded-lg shadow md:flex md:items-center md:justify-between md:p-6 dark:bg-gray-800';
	export let siteNameClass: string = 'text-sm text-gray-500 sm:text-center dark:text-gray-400';
	export let ulClass: string = 'flex flex-wrap items-center mt-3 sm:mt-0';
	export let aClass: string = 'mr-4 text-sm text-gray-500 hover:underline md:mr-6 dark:text-gray-400';
	export let siteNameLinkClass: string = 'hover:underline';
	export let copyrightYear: string = '© 2022';
	export let allRightsReserved: string = 'All Rights Reserved.';
</script>

<footer class="{footerClass} {$$props.class ? $$props.class : ''}">
	<span class={siteNameClass}
		>{copyrightYear}
		<a href={site.href} class={siteNameLinkClass} target="_blank">{site.name}</a>. {allRightsReserved}
	</span>
	<ul class={ulClass}>
		{#each links as { name, href, rel }}
			<li>
				<a {href} {rel} class={aClass}>{name}</a>
			</li>
		{/each}
	</ul>
</footer>
