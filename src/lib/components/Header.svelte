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
	class="top-0 z-[999] mb-2 flex flex-col items-center justify-between bg-white px-10 pt-9 pb-6 font-semibold text-black shadow-md md:flex-row lg:flex-row"
>
	<div class="w-full md:w-fit lg:w-fit">
		<a class="" href="https://sacda.ca/index.php">
			<Logo class="w-64" />
		</a>

		<button
			class="absolute top-0 right-10 bg-[#F99D2A] px-8 py-10 md:hidden lg:hidden"
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
		<div transition:slide class="flex-col items-end gap-4 md:flex lg:flex">
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
					class="hidden md:flex md:bg-[#414042] md:px-6 md:py-2 md:text-white md:hover:bg-[#F99D2A] lg:flex lg:bg-[#414042] lg:px-6 lg:py-2 lg:text-white lg:hover:bg-[#F99D2A]"
					href="https://sacda.ca/index.php/Search/advanced/objects"
					role="button">ADVANCED SEARCH</a
				>
			</div>

			<ul class="flex flex-col items-center gap-4 md:flex-row lg:flex-row **:border-b-2 **:border-b-transparent **:pb-1 **:transition-all **:duration-200 **:hover:border-b-[#F99D2A]">
				<li class="nav-item">
					<a class="" href="https://sacda.ca/index.php/Browse/objects">BROWSE </a>
				</li>
				<li class="nav-item">
					<a class="" href="https://sacda.ca/index.php/Collections/index">COLLECTIONS</a>
				</li>
				<li class="nav-item">
					<a class="" href="https://sacda.ca/index.php/exhibits/index">EXHIBITS</a>
				</li>
				<li class="nav-item">
					<a class="" href="https://sacda.ca/index.php/About/Index">ABOUT</a>
				</li>
				<li class="nav-item">
					<a class="" href="https://sacda.ca/index.php/Contact/Form">CONTACT</a>
				</li>
				<li class="nav-item">
					<a class="" href="https://sacda.ca/index.php/newsletter">NEWSLETTER</a>
				</li>
				<li class="nav-item md:hidden lg:hidden">
					<a class="" href="https://sacda.ca/index.php/Search/advanced/objects">ADVANCED SEARCH</a>
				</li>
			</ul>
		</div>
	{/if}
</nav>
