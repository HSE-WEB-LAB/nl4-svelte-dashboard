<script>
    import {dashboardData} from "../../data/index.js";
    import BarChart from "../../organism/BarChart/BarChart.svelte";
    import SalesWidget from "../../organism/SalesWidget/SalesWidget.svelte";
</script>

<div class="dashboardWidgets">
    <BarChart
            data={dashboardData.barChart.data}
            name={dashboardData.barChart.name}
    />
    <SalesWidget data={dashboardData.todaySalesWidget.data}/>
</div>