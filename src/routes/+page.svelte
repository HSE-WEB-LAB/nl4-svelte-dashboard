<script>
import DashboardWidgets from "../templates/DashboardWidgets/DashboardWidgets.svelte";
</script>

<div class="dashboard">
    <DashboardWidgets />
</div>

<style global>
    .dashboard{
        box-sizing: border-box;
        width: 100%;
        height: 100%;
        position: relative;
        padding: 30px;
    }
    *{
        box-sizing: border-box;
        padding: 0;
        margin: 0;
        font-family: 'Poppins', sans-serif;
    }
</style>