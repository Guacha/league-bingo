<script>
	import { SlideToggle } from '@skeletonlabs/skeleton';

	let settings = [
		{
			id: 1,
			name: 'Free Center',
			value: true
		},
		{
			name: 'Allow Troll builds (e.g. Full AP on Lee Sin)',
			value: false
		},
		{
			name: 'Setting 3',
			value: false
		}
	];
</script>

<div class="flex bg-indigo-100 h-full">
	<div class="md:w-2/3 bg-red-100">
		<p class="text-4xl text-center">New Game</p>
		<p class="mt-1 text-center text-xl">
			Start a New Game, after which, you can send the board link to your friends
		</p>
		<div class="flex justify-center mt-1">
			<div class="w-1/2 bg-gray-700 h-3 rounded-xl mt-1"></div>
		</div>
		<p class="mt-1 text-2xl text-center">Game Settings</p>
		<div id="settings" class="pt-2 grid grid-cols-2 gap-y-2">
			{#each settings as setting}
				<p class="text-xl text-center">
					{setting.name}
				</p>
				<div class="text-center">
					<SlideToggle bind:value={setting.value} />
				</div>
			{/each}
		</div>
	</div>
	<div class="md:w-1/3 bg-green-100">Hola2</div>
</div>
