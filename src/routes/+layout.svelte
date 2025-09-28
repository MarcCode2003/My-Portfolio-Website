<script lang="ts">
	import '../app.css';
	import favicon from '$lib/assets/favicon.svg';
	import { onMount } from 'svelte';

	let { children } = $props();
	let content: HTMLDivElement;
	let thumb: HTMLDivElement;

	// Update scrollbar thumb position
	function updateThumb() {
		if (!content || !thumb) return;

		const { scrollTop, scrollHeight, clientHeight } = content;
		const thumbHeight = Math.max((clientHeight / scrollHeight) * clientHeight, 40); // min size
		const scrollRatio = scrollTop / (scrollHeight - clientHeight);
		const top = scrollRatio * (clientHeight - thumbHeight);

		thumb.style.height = `${thumbHeight}px`;
		thumb.style.transform = `translateY(${top}px)`;
	}

	onMount(() => {
		content.addEventListener('scroll', updateThumb);
		updateThumb(); // initial position
	});
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<!-- Wrapper -->
<div class="scroll-wrapper">
	<main bind:this={content} class="scroll-content">
		{@render children?.()}
	</main>

	<!-- Custom scrollbar -->
	<div class="custom-scrollbar">
		<div bind:this={thumb} class="thumb"></div>
	</div>
</div>
