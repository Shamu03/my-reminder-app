<script>
	import Header from "./components/Header.svelte";
	import Dashboard from "./components/Dashboard.svelte";

	import { v4 } from "uuid";

	let notes = [
		{
			id: 0,
			title: "Vacaciones",
			color: "yellow",
			text: "Hola!",
		},
		{
			id: 1,
			title: "Guayabas",
			color: "green",
			text: "Hello!",
		},
	];
	let copyNotes = [...notes];
	$: count = notes.length;

	const handleNew = () => {
		const color = generateColor();
		const id = v4();
		const note = {
			id: id,
			title: "",
			text: "",
			color: color,
		};
		notes = [note, ...notes];
		copyNotes = [...notes];
	};
	function generateColor() {
		const colors = ["#f4f9f9", "#ccf2f4", "#a4ebf3"];
		const index = Math.floor(Math.random() * colors.length);
		return colors[index];
	}

	function handleUpdate(e){
		const note = e.detail;
		const index = notes.findIndex(n => n.id === note.id);
		note[index] = note;
		copuNotes = [...notes];

	}
</script>

<main>
	<Header />
	<div class="counter">{count} notes</div>
	<Dashboard {notes} on:click={handleNew} on:update={handleUpdate}/>
</main>

<style>
	.counter {
		padding: 0 5vmax;
	}
	
</style>
