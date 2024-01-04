<script>
    import asd from '../../atoms/Svg/dummy logo.svg'
    import NavTitle from "../../molecules/NavTitle/NavTitle.svelte";
    import SideBarButtons from "../../molecules/SideBarButtons/SideBarButtons.svelte";

    const navData = [
        {
            text: 'Dashboard',
            url: '/'
        },
        {
            text: 'Leaderboard',
            url: '/leaderboard'
        },
        {
            text: 'Order',
            url: '/order'
        },
        {
            text: 'Products',
            url: '/products'
        },
        {
            text: 'Sales Report',
            url: '/sales-report'
        },
    ]
</script>

<div class="sidebar">
    <NavTitle
            titleText="Dabang"
            svgIcon={asd}
    />
    <SideBarButtons
            navData={navData}
    />
</div>

<style>
    .sidebar{
        position: absolute;
        top: 0;
        left: 0;

        padding: 50px;

        background-color: white;

        width: 345px;
        height: 100vh;

        display: flex;
        flex-direction: column;
        align-content: center;
    }
</style>