<script lang="ts">
	const tabs = [
		{ name: 'Vault', icon: 'vault' },
		{ name: 'Autofill', icon: 'autofill' },
		{ name: 'Generate', icon: 'generate' },
		{ name: 'Settings', icon: 'settings' }
	];

	const handleTabClick = (tab: { name: string; icon: string }) => {
		return () => {
			console.log(tab);
		};
	};
</script>

<main class="w-[350px] h-[560px] bg-red-400 border border-black p-4">
	<div class="flex flex-col h-full">
		<div class="flex flex-col flex-grow">
			<slot />
		</div>
		<div class="flex flex-row justify-between">
			{#each tabs as tab}
				<button class="flex flex-col items-center" on:click={handleTabClick(tab)}>
					{tab.icon}
					{tab.name}
				</button>
			{/each}
		</div>
	</div>
</main>
