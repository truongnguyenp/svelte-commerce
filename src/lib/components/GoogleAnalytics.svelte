<script lang="ts">
import { page } from '$app/stores'
import { GOOGLE_ANALYTICS_ID } from '$lib/config'

$: {
	if (typeof gtag !== 'undefined') {
		gtag('config', GOOGLE_ANALYTICS_ID, {
			page_title: document.title,
			page_path: $page.url.pathname
		})
	}
}
</script>

<svelte:head>
	<script async src="https://www.googletagmanager.com/gtag/js?id=G-ZMZXZWG90W">
	</script>
	<script>
	window.dataLayer = window.dataLayer || []

	function gtag() {
		dataLayer.push(arguments)
	}

	gtag('js', new Date())
	gtag('config', 'G-ZMZXZWG90W')
	</script>
</svelte:head>
