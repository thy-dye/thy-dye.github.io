<script lang="ts">
	import zanka_tired from '$lib/assets/zanka_tired.png';
	import githubIcon from '$lib/assets/logo-github.svg';
	import linkedinIcon from '$lib/assets/logo-linkedin.svg';
	import instagramIcon from '$lib/assets/logo-instagram.svg';
	import youtubeIcon from '$lib/assets/logo-youtube.svg';
	import shadertoyIcon from '$lib/assets/brush-outline.svg';

	import { onMount } from 'svelte';

	onMount(() => {
		const buttons = document.querySelectorAll('.social-button');
		let count = 0;
			
		buttons.forEach((button, index) => {
			setTimeout(() => {
			count++;
			
			// Add animation class
			button.classList.add('animate-in');

			// Remove class after animation completes so hover won't retrigger
			setTimeout(() => {
				button.classList.remove('animate-in');
				// Force final state
				button.style.opacity = '1';
				button.style.pointerEvents = 'auto';
			}, 1500); // Match your animation duration
			
			}, index * 100); // Stagger delay
		});
	});
	
	let { children } = $props();

  const socialLinks = [
    { name: 'GitHub', url: 'https://github.com/thy-dye', icon: githubIcon},
    { name: 'LinkedIn', url: 'https://www.linkedin.com/in/ty-torres-a7722526b/', icon: linkedinIcon},
    { name: 'Instagram', url: 'https://www.instagram.com/cheezit_enjoyer72/', icon: instagramIcon}, 
    { name: 'Youtube', url: 'https://www.youtube.com/@AFoolsFire', icon: youtubeIcon}, 
    { name: 'ShaderToy', url: 'https://www.shadertoy.com/profile/?show=shaders', icon: shadertoyIcon} 
  ];
</script>

<svelte:head>
	<link rel="icon" href={zanka_tired} />
</svelte:head>

<nav>
	<!-- Navigation to other pages -->
	<a class="nav-link" href="/">Ty Torres</a>
	<a class="nav-link" href="/Projects">Projects</a>
	<!-- social links -->
	<section class="connect-section">
		{#each socialLinks as link}
			<a 
				href={link.url} 
				target="_blank" 
				rel="noopener noreferrer"
				class="social-button"
			>
				<span class="button-icon">
					<img src={link.icon} alt={link.name} width="32" height="32"/>
				</span>
			</a>
		{/each}
	</section>
</nav>

<main>
	{@render children()}
</main>

<!-- footer -->
<footer class="page-footer">
  <p>© 2026 Ty Torres. Built with SvelteKit.</p>
  <p class="footer-note">
  	This site is hosted on GitHub Pages.
    <a href="https://github.com/thy-dye/thy-dye.github.io" target="_blank">
        View source code
    </a>
  </p>
</footer>