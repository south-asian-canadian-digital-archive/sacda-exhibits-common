<script lang="ts">
	import { slide } from 'svelte/transition';
	import Logo from '$lib/icons/Logo.svelte';

	let search = $state('');
	let mobileNavButtonWidth: number = $state(0);

	let mobileNavOpen = $state(false);
	

	// run(() => {
	// 	mobileNavButtonWidth;
	// });
</script>

<nav
	class="sacda-header top-0 z-[999] mb-2 flex flex-col items-center justify-between bg-white px-10 pt-9 pb-6 font-semibold text-black shadow-md md:flex-row lg:flex-row"
>
	<div class="w-full md:w-fit lg:w-fit">
		<a class="" href="https://sacda.ca/index.php">
			<Logo class="w-64" />
		</a>

		<button
			class="sacda-mobile-nav-toggle absolute top-0 right-10 bg-[#F99D2A] px-8 py-10 md:hidden lg:hidden"
			bind:clientWidth={mobileNavButtonWidth}
			onclick={() => (mobileNavOpen = !mobileNavOpen)}
		>
			{#if mobileNavOpen}
				<span class="fa fa-times scale-150"></span>
			{:else}
				<span class="fa fa-bars scale-150"></span>
			{/if}
		</button>
	</div>

	{#if mobileNavButtonWidth == 0 || mobileNavOpen}
		<div transition:slide class="sacda-nav-content flex-col items-end gap-4 md:flex lg:flex">
			<div class="flex flex-row items-center gap-4 py-8 md:py-0 lg:py-0">
				<div class="flex">
					<input
						class="border border-black px-3 py-2 outline-none"
						placeholder="Search"
						bind:value={search}
					/>
					<a
						href={'https://sacda.ca/index.php/MultiSearch/Index?search=' + search}
						class="flex w-16 items-center justify-center border border-[#414042] bg-[#414042] text-lg text-[#FFEDC2] transition-all duration-200 ease-in-out hover:bg-[#F99D2A]"
						type="button"
					>
						>
					</a>
				</div>
				<a
					class="sacda-advanced-search-btn hidden md:flex md:bg-[#414042] md:px-6 md:py-2 md:text-white md:hover:bg-[#F99D2A] lg:flex lg:bg-[#414042] lg:px-6 lg:py-2 lg:text-white lg:hover:bg-[#F99D2A]"
					href="https://sacda.ca/index.php/Search/advanced/objects"
					role="button">ADVANCED SEARCH</a
				>
			</div>

			<ul class="sacda-nav-list flex flex-col items-center gap-4 md:flex-row lg:flex-row">
				<li class="sacda-nav-item">
					<a class="sacda-nav-link" href="https://sacda.ca/index.php/Browse/objects">BROWSE </a>
				</li>
				<li class="sacda-nav-item">
					<a class="sacda-nav-link" href="https://sacda.ca/index.php/Collections/index">COLLECTIONS</a>
				</li>
				<li class="sacda-nav-item">
					<a class="sacda-nav-link" href="https://sacda.ca/index.php/exhibits/index">EXHIBITS</a>
				</li>
				<li class="sacda-nav-item">
					<a class="sacda-nav-link" href="https://sacda.ca/index.php/About/Index">ABOUT</a>
				</li>
				<li class="sacda-nav-item">
					<a class="sacda-nav-link" href="https://sacda.ca/index.php/Contact/Form">CONTACT</a>
				</li>
				<li class="sacda-nav-item">
					<a class="sacda-nav-link" href="https://sacda.ca/index.php/newsletter">NEWSLETTER</a>
				</li>
				<li class="sacda-nav-item md:hidden lg:hidden">
					<a class="sacda-nav-link" href="https://sacda.ca/index.php/Search/advanced/objects">ADVANCED SEARCH</a>
				</li>
			</ul>
		</div>
	{/if}
</nav>

<style>
	/* SACDA Header Component Styles - High specificity to prevent overrides */
	:global(.sacda-header) {
		--sacda-primary-color: #F99D2A;
		--sacda-secondary-color: #414042;
		--sacda-light-color: #FFEDC2;
	}

	/* Navigation link styles with high specificity */
	:global(.sacda-header .sacda-nav-list .sacda-nav-item .sacda-nav-link) {
		border-bottom: 2px solid transparent !important;
		padding-bottom: 0.25rem !important;
		transition: all 0.2s ease-in-out !important;
		text-decoration: none !important;
		display: inline-block !important;
		color: #000000 !important;
		font-weight: 600 !important;
	}

	:global(.sacda-header .sacda-nav-list .sacda-nav-item .sacda-nav-link:hover) {
		border-bottom-color: var(--sacda-primary-color) !important;
		color: #000000 !important;
	}

	/* Mobile navigation toggle button styles */
	:global(.sacda-header .sacda-mobile-nav-toggle) {
		transition: background-color 0.2s ease-in-out !important;
	}

	:global(.sacda-header .sacda-mobile-nav-toggle:hover) {
		background-color: var(--sacda-secondary-color) !important;
	}

	/* Advanced search button styles */
	:global(.sacda-header .sacda-advanced-search-btn) {
		transition: background-color 0.2s ease-in-out !important;
		color: #ffffff !important;
	}

	:global(.sacda-header .sacda-advanced-search-btn:hover) {
		background-color: var(--sacda-primary-color) !important;
		color: #ffffff !important;
	}

	/* Ensure the component maintains its layout even with external CSS */
	:global(.sacda-header *) {
		box-sizing: border-box !important;
	}

	/* Font Awesome icon protection */
	:global(.sacda-header .fa) {
		font-family: 'Font Awesome 5 Free', 'Font Awesome 5 Pro', FontAwesome !important;
		font-weight: 900 !important;
	}
</style>
