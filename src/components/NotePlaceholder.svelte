<script>
</script>

<div class="noteplaceholder">
    <button on:click>New note</button>
</div>

<style>
    button {
        cursor: pointer;
        border-radius: 10px;
        color: #aaaaaa;
        border: 5px dotted #aaaaaa;
        background-color: transparent;
        font-weight: bold;
        width: 22vw;
        height: 40vh;
    }

    button:hover {
        color: #a4ebf3;
        border: 5px dotted #a4ebf3;
    }

    @media (max-width: 1024px) {
        button {
            height: 45vh;
            width: 45vw;
        }
    }

    @media (max-width: 480px) {
        button {
            width: 80vw;
            height: 30vh;
        }
    }
</style>
