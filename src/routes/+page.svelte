<script lang="ts">
    import { fade } from "svelte/transition";

    let visible = $state(true);

    let page = $state(0);
</script>
<main>
    <div id="content">
        <div id="inner">
            <div id="text">
                {#if page == 0}
                    Liebe Sabsi,<br />
                    Would you be my valentine? 🥰<br />
                {:else if page == 1}
                    🥳❤️❤️❤️<br />
                {/if}
            </div>
            {#if page == 0}
                <img src="/images/hedgehog.gif" alt="hedgehog"/>
            {:else if page == 1}
                <img src="/images/party.gif" alt="party"/>
            {/if}
            <div id="buttons">
                {#if page == 0}
                    <button class="yes" onclick={() => page = 1}>Ja 😍</button>
                    {#if visible}
                        <button class="no" onclick={() => visible = false} transition:fade>Nein 🥺</button>
                    {/if}
                {/if}
            </div>
            {#if page == 1}
                Kino? Zoomania 2? Dann wenn du Zeit hast?
                <img src="/images/zoomania.gif" alt="zoomania"/><br />
            {/if}
        </div>
    </div>
</main>

<style>
    main {
        background-color: rgb(235, 221, 225);
        width: 100dvw;
        height: 100dvh;
        display: flex;
        flex-flow: column nowrap;
        padding: 20px;
        box-sizing: border-box;
        flex-grow: 4;
        align-items: center;
        justify-content: center;

        & #content {
            background-color: rgb(255, 39, 97);
            padding: 40px;
            border-radius: 40px;

            & #inner {
                background-color: rgb(255, 166, 190);
                padding: 25px;
                border-radius: 25px;
                display: flex;
                flex-flow: column nowrap;
                row-gap: 20px;

                & #text {
                    font-family: Verdana, Geneva, Tahoma, sans-serif;
                    font-size: 3rem;
                }

                & #buttons {
                    display: flex;
                    flex-flow: row nowrap;
                    justify-content: center;
                    column-gap: 20px;

                    & .yes {
                        background-color: green;
                        color: white;
                    }

                    & .no {
                        background-color: red;
                        color: white;
                    }

                    & button {
                        padding: 15px;
                        font-size: 2rem;
                        border-radius: 10px;
                        border: none;
                        outline: none;
                    }
                }
            }
        }
    }
</style>
