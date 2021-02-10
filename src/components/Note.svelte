<script>
    export let title;
    export let text;
    export let color;

    import {createEventDispatcher} from 'svelte';

    const dispatch = createEventDispatcher();
    const handleChange = () =>{
        dispatch('update', {
            id: id,
            title: title,
            text: text,
            color: color
        })
    }
</script>

<div class="note">
    <div class="note-container" style={"background-color" + color}>
        <header class="header">
            <div class="options">
                <button>
                    <svg
                        xmlns="http://www.w3.org/2000/svg"
                        viewBox="0 0 24 24"
                        fill="black"
                        width="18px"
                        height="18px"
                        ><path d="M0 0h24v24H0V0z" fill="none" /><path
                            d="M12 22C6.49 22 2 17.51 2 12S6.49 2 12 2s10 4.04 10 9c0 3.31-2.69 6-6 6h-1.77c-.28 0-.5.22-.5.5 0 .12.05.23.13.33.41.47.64 1.06.64 1.67 0 1.38-1.12 2.5-2.5 2.5zm0-18c-4.41 0-8 3.59-8 8s3.59 8 8 8c.28 0 .5-.22.5-.5 0-.16-.08-.28-.14-.35-.41-.46-.63-1.05-.63-1.65 0-1.38 1.12-2.5 2.5-2.5H16c2.21 0 4-1.79 4-4 0-3.86-3.59-7-8-7z"
                        /><circle cx="6.5" cy="11.5" r="1.5" /><circle
                            cx="9.5"
                            cy="7.5"
                            r="1.5"
                        /><circle cx="14.5" cy="7.5" r="1.5" /><circle
                            cx="17.5"
                            cy="11.5"
                            r="1.5"
                        /></svg
                    >
                </button>
                <button>
                    <svg
                        xmlns="http://www.w3.org/2000/svg"
                        height="24"
                        viewBox="0 0 24 24"
                        width="24"
                        ><path d="M0 0h24v24H0V0z" fill="none" /><path
                            d="M14.12 10.47L12 12.59l-2.13-2.12-1.41 1.41L10.59 14l-2.12 2.12 1.41 1.41L12 15.41l2.12 2.12 1.41-1.41L13.41 14l2.12-2.12zM15.5 4l-1-1h-5l-1 1H5v2h14V4zM6 19c0 1.1.9 2 2 2h8c1.1 0 2-.9 2-2V7H6v12zM8 9h8v10H8V9z"
                        /></svg
                    >
                </button>
            </div>
        </header>
        <div class="content">
            <div class="title">
                <input
                    type="text"
                    placeholder="Without title..."
                    bind:value={title}
                    on:change={handleChange}
                />
            </div>
            <div class="text">
                <textarea
                    id=""
                    rows="10"
                    placeholder="Write..."
                    bind:value={text}
                    on:change={handleChange}
                />
            </div>
        </div>
    </div>
</div>

<style>
    .note {
        border-radius: 5px;
        border: 2px solid transparent;
        overflow: hidden;
        width: 22vw;
        height: 40vh;
    }

    .note:focus-within {
        border: 2px solid #000;
        box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
    }

    .header {
        padding: 5px;
    }

    .options {
        display: flex;
        justify-content: space-between;
    }

    .content {
        padding: 0 20px;
    }

    .title input {
        font-size: medium;
        font-weight: bold;
        padding: 10px 0;
        outline: none;
        resize: none;
        width: 100%;
    }

    .text textarea {
        width: 100%;
        outline: none;
        resize: none;
        height: 250px;
    }

    button {
        margin: 0;
        border: none;
        background-color: transparent;
        cursor: pointer;
    }

    textarea,
    input {
        border: none;
        background: transparent;
    }

    @media (max-width: 1024px) {
        .note {
            height: 45vh;
            width: 45vw;
        }
    }

    @media (max-width: 480px) {
        .note {
            height: 30vh;
            width: 80vw;
        }
    }
</style>
