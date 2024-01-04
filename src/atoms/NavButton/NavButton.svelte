<script>
    export let imgSrc;
    export let isActive;

    export let click = () => {};
</script>

<button
        class={'navButton' + (isActive ? ' active' : '') + ' sideBarButton'}
        on:click={click}
>
    <div class="wrapper">
        {#if imgSrc}
        <div>
            <img src={imgSrc} alt="icon">
        </div>
        {/if}

        <p class="buttonText">
            <slot/>
        </p>

    </div>
</button>

<style>
    .sideBarButton{
        width: 100%;
        height: 54px;
        border-radius: 16px;
        border: none;
        background-color: transparent;
        position: relative;
        cursor: pointer;
    }

    .sideBarButton .wrapper{
        position: relative;
        width: 100%;
        height: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .sideBarButton .buttonText{
        color: #737791;
        font-size: 18px;
    }

    .sideBarButton:hover .buttonText{
        color: black;
    }

    .active{
        background-color: #5D5FEF;
    }

    .active .buttonText{
        color: white;
        font-weight: 500;
    }

    .active:hover .buttonText{
        color: lightgray;
    }
</style>