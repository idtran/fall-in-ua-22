<script lang="ts">
	import { state } from '$lib/state';
	import {getContext} from "svelte";

	const updateSidebar = getContext<(x: boolean) => void>('updateSidebar');

</script>

<div class="flex flex-col flex-grow overflow-auto">
	<div class="grid grid-cols-4 gap-6 items-start">
		{#if $state?.mutable.selectedGroup}
			<!-- TODO SHOW GROUP -->
		{:else}
		<div class="col-span-4 px-4 py-2 flex justify-center">
			<button class="btn btn-outline btn-primary" on:click={() => updateSidebar(true)} > Please select a group to continue... </button>
		</div>
		{/if}
	</div>
</div>
