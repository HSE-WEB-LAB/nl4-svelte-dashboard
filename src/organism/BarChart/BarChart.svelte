<script>
    import {onMount} from "svelte";
    import ChartBars from "../../molecules/ChartBars/ChartBars.svelte";
    import BarChartBackground from "../../molecules/BarChartsBackground/BarChartBackground.svelte";

    export let data = [];
    export let name = '';
    let backgroundShards;
    let maxValueBar = 0;

    onMount(() => {
        let maxValue = data[0].value;
        data.forEach(({value}) => {
            if(value > maxValue) maxValue = value;
        })
        if(maxValue < 10){ //опционально
            maxValue = 10;
        }
        else{
            while(maxValue % 10 !== 0){
                maxValue -= 1;
            }
        }
        maxValueBar = maxValue;
        shardsGenerator(maxValue)
    })

    const shardsGenerator = (maxValue) => {
        const temp = [];
        let startValue = maxValue / 4;
        for (let i = 4; i>=0; i--)
            temp.push(startValue * i);
        backgroundShards = temp;
        console.log(backgroundShards)
    };
</script>

<div class="barChart">
    <p class="chartTitle">
        { name }
    </p>
    <div class="graphContainer">
        <BarChartBackground backgroundShards={backgroundShards}/>
        <ChartBars
                data={data}
                maxValue={maxValueBar}
        />
    </div>

</div>

<style>
    .chartTitle{
        font-weight: 500;
        margin-bottom: 20px;
    }
    .barChart{
        height: 350px;
        width: 650px;
        padding: 30px;
        background-color: white;
        border-radius: 20px;
        position: relative;
    }

    .barChart .graphContainer{
        position: relative;
        padding-top: 15px;
    }
</style>