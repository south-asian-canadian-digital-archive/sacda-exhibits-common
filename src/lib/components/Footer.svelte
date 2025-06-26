<script lang="ts">
	import type { SponsorData, SocialData } from '../types.js';

	const sponsors: SponsorData[] = [
		{
			name: 'SACDA',
			link: 'http://sacda.ca',
			image: 'https://sacda.ca//themes/sacda/assets/pawtucket/graphics/footer/sacda.svg'
		},
		{
			name: 'South Asian Studies Institute',
			link: 'http://www.ufv.ca/sasi',
			image: 'https://sacda.ca//themes/sacda/assets/pawtucket/graphics/footer/sasi.svg'
		},
		{
			name: 'University of the Fraser Valley',
			link: 'http://www.ufv.ca/',
			image: 'https://sacda.ca//themes/sacda/assets/pawtucket/graphics/footer/ufv.svg'
		},
		{
			name: 'South Asian Canadian Legacy Project',
			link: 'https://saclp.southasiancanadianheritage.ca/',
			image: 'https://sacda.ca//themes/sacda/assets/pawtucket/graphics/footer/bc.svg'
		},
		{
			name: 'Canada',
			link: 'https://www.canada.ca/en.html',
			image: 'https://sacda.ca//themes/sacda/assets/pawtucket/graphics/footer/canada_logo.svg'
		},
		{
			name: 'UBC Irving K. Barber Learning Centre',
			link: 'https://ikblc.ubc.ca/',
			image: 'https://sacda.ca//themes/sacda/assets/pawtucket/graphics/footer/BCHDP_logo_white.png'
		}
	];

	const socials: SocialData[] = [
		{
			name: 'Facebook',
			link: 'https://www.facebook.com/profile.php?id=100092345694324',
			element: "<i class='fa fa-facebook-square'></i>"
		},
		{
			name: 'Instagram',
			link: 'https://www.instagram.com/sacda.sasi/',
			element: "<i class='fa fa-instagram'></i>"
		},
		{
			name: 'Twitter',
			link: 'https://twitter.com/ufvsasi',
			element: "<i class='fa fa-twitter'></i>"
		},
		{
			name: 'Youtube',
			link: 'https://www.youtube.com/channel/UCN5tvG-Q8ly9z0YOyWsoaNA',
			element: "<i class='fa fa-youtube'></i>"
		},
		{
			name: 'Flicker',
			link: 'https://www.flickr.com/photos/ufvcics/albums',
			element: "<i class='fa fa-flickr'></i>"
		}
	];
</script>

<footer
	class="relative flex flex-col-reverse items-end justify-between gap-4 bg-[#414042] px-6 pt-10 pb-24 md:flex-row md:py-24 lg:flex-row lg:py-24"
>
	<div class="flex flex-row items-center gap-5 pb-3">
		{#each sponsors as sponsor}
			<div class="w-auto">
				<a href={sponsor.link} target="_blank" rel="noopener noreferrer">
					<img src={sponsor.image} alt={sponsor.name} class="h-10" />
				</a>
			</div>
		{/each}
	</div>

	<div class="flex w-full flex-col items-center gap-4 md:w-fit lg:w-fit">
		<p
			class="w-fit border-b border-b-[#ffce34] pb-1 text-lg font-bold text-white uppercase md:self-end lg:self-end"
		>
			GET IN TOUCH
		</p>

		<div class="flex flex-row gap-3">
			{#each socials as social}
				<a
					href={social.link}
					target="_blank"
					rel="noopener noreferrer"
					class="flex h-12 w-12 items-center justify-center rounded-full border border-[#ffce34] text-lg text-white"
				>
					{@html social.element}
				</a>
			{/each}
		</div>
	</div>

	<div
		class="absolute bottom-6 w-full self-center text-center text-sm text-white md:w-fit md:self-start lg:w-fit lg:self-start"
	>
		<div class="flex w-full items-center justify-center md:hidden lg:hidden">
			<p class="w-fit border-t border-t-[#ffce34] pb-1 text-lg font-bold text-transparent">
				GET IN TOUCH
			</p>
		</div>

		<a href="https://sacda.ca/policy/takedown">Statement of Use and Takedown Policy </a> |
		<a href="https://sacda.ca/index.php/About/media" class=""> Media </a> | © 2024 South Asian Canadian
		Digital Archive
	</div>
</footer>
