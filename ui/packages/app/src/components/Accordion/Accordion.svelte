<script lang="ts">
	import { Component as Column } from "../Column";
	export let label: string;
	export let elem_id: string;
	export let visible: string;
	export let open: boolean = true;

	let _open = open;

	const toggle = () => {
		_open = !_open;
	};
</script>

<div
	id={elem_id}
	class="p-3 border border-gray-200 dark:border-gray-700 rounded-lg flex flex-col gap-3 hover:border-gray-300 dark:hover:border-gray-600 transition"
	class:hidden={!visible}
>
	<div on:click={toggle} class="w-full flex justify-between cursor-pointer">
		<span>{label}</span>
		<span class:rotate-90={!_open} class="transition">▼</span>
	</div>
	<Column visible={_open}>
		<slot />
	</Column>
</div>
