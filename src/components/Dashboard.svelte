<script>
    export let notes;

    import Note from "./Note.svelte";
    import NotePlaceholder from "./NotePlaceholder.svelte";
</script>

<div class="dashboard">
    <div class="note-container">
        <NotePlaceholder on:click/>
        {#each notes as { title, text, color }}
            <Note {title} {text} {color} />
        {/each}
    </div>
</div>

<style>
    .dashboard {
        margin: 0;
        padding: 3vh 4vw;
        box-sizing: border-box;
    }

    .note-container {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        gap: 1vw;
    }

    @media (max-width: 1024px) {
        .note-container {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 2vw;
        }
    }

    @media (max-width: 480px) {
        .note-container {
            display: grid;
            grid-template-columns: repeat(1, 1fr);
            gap: 0;
        }
    }
</style>
