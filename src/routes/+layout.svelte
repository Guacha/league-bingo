<script>
	import './styles.css';
	import { AppShell, AppRail, AppRailAnchor, AppRailTile, AppBar } from '@skeletonlabs/skeleton';
	import Icon from '@iconify/svelte';

	let menuActive = false;
	let currentTile = 0;
	let icon = 'mdi:hamburger';

	const handleMenuChange = () => {
		menuActive = !menuActive;
		if (menuActive) {
			icon = 'mdi:close';
		} else {
			icon = 'mdi:hamburger';
		}
	};
</script>

<AppShell>
	<svelte:fragment slot="header">
		<AppBar gridColumns="grid-cols-3" slotDefault="place-self-center" slotTrail="place-content-end">
			<svelte:fragment slot="lead">
				<button on:click={handleMenuChange}>
					<Icon {icon} width="2em" height="2em" class="transition-all ease-in-out" />
				</button>
			</svelte:fragment>
			<p class="text-2xl">LoL Bingo</p>
			<svelte:fragment slot="trail">(actions)</svelte:fragment>
		</AppBar>
	</svelte:fragment>
	<svelte:fragment slot="sidebarLeft">
		<div
			class="fixed z-20 transition-all duration-500 transform -translate-x-full"
			class:lg:block={menuActive}
			class:translate-x-0={menuActive}
			class:shadow-2xl={menuActive}
		>
			<AppRail>
				<!-- --- -->
				<AppRailTile bind:group={currentTile} name="tile-1" value={0} title="tile-1">
					<svelte:fragment slot="lead">
						<div class="flex justify-center">
							<Icon icon="mdi:home-outline" width="1.2em" height="1.2em" />
						</div>
					</svelte:fragment>
					<span>Home</span>
				</AppRailTile>
				<AppRailTile bind:group={currentTile} name="tile-1" value={1} title="tile-1">
					<svelte:fragment slot="lead">
						<div class="flex justify-center">
							<Icon icon="mdi:gamepad-square-outline" width="1.2em" height="1.2em" />
						</div>
					</svelte:fragment>
					<span>Play Bingo</span>
				</AppRailTile>
				<AppRailTile bind:group={currentTile} name="tile-1" value={1} title="tile-1">
					<svelte:fragment slot="lead">
						<div class="flex justify-center">
							<Icon icon="mdi:question-box-outline" width="1.2em" height="1.2em" />
						</div>
					</svelte:fragment>
					<span>About</span>
				</AppRailTile>
				<!-- --- -->
				<svelte:fragment slot="trail">
					<AppRailAnchor href="/" target="_blank" title="Account">(icon)</AppRailAnchor>
				</svelte:fragment>
			</AppRail>
		</div>
	</svelte:fragment>
	<div class="p-4">
		<slot />
	</div>
	<svelte:fragment slot="pageFooter">
		<AppBar gridColumns="grid-cols-3" slotDefault="place-self-center" slotTrail="place-content-end">
			<svelte:fragment slot="lead">
				<p>
					Made with ❤️ by <a href="https://www.github.com/Guacha" target="_blank">Guacha</a>
				</p>
			</svelte:fragment>
			<svelte:fragment slot="trail">
				<a href="https://twitter.com/Guachamalinga" class="btn sm icon variant-filled">
					<Icon icon="bi:twitter-x" width="0.8em" />
				</a>
				<a class="btn sm icon variant-filled-primary" href="https://www.github.com/Guacha">
					<Icon icon="mdi:github" />
				</a>
			</svelte:fragment>
		</AppBar>
	</svelte:fragment>
</AppShell>
