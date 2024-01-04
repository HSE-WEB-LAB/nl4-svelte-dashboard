<script>
    import NavButton from "../../atoms/NavButton/NavButton.svelte";
    import {onMount} from "svelte";

    export let navData = [];
    let currentActive = 0;

    const changeCurrent = (i, url) => {
        currentActive = i;
        let a = document.createElement('a');
        a.href = url;
        a.click();
    }

    onMount(() => {
        navData.forEach((nav, index) => {
            if(window.location.href.includes(nav.url)){
                currentActive = index;
            }
        })
    })
</script>

<div class="sideBarButtons">
    {#each navData as nav, index}
        <NavButton
                isActive={currentActive === index}
                click={() => changeCurrent(index, nav.url)}
        >
            { nav.text }
        </NavButton>
    {/each}
</div>

<style>
    .sideBarButtons{
        display: flex;
        flex-direction: column;
        gap: 30px;
    }
</style>