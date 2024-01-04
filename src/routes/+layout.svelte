<script>
    import TopBar from "../templates/TopBar/TopBar.svelte";
    import SideBar from "../templates/SideBar/SideBar.svelte";
    import '../style.css'
</script>


<div class="layout">
    <TopBar />
    <SideBar/>
    <div class="layoutWrapper">
        <slot />
    </div>
</div>

<style global>
    *{
        box-sizing: border-box;
        padding: 0;
        margin: 0;
        font-family: 'Poppins', sans-serif;
    }

    .layout{
        position: relative;
        padding-top: 120px;
        padding-left: 345px;
        background: #FAFBFC;

        display: block;
        width: 100vw;
        height: 100vh;
    }

    .layoutWrapper{
        box-sizing: border-box;
        width: 100%;
        height: 100%;
        max-width: 100%;
        max-height: 100%;
        overflow: auto;
    }
</style>