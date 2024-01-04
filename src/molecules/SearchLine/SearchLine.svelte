<script>
    import SvgView from "../../atoms/SvgView/SvgView.svelte";
    import magnifying from '../../atoms/Svg/magnifying-glass-solid.svg'

    export let modelValue = '';
    let inputPadding = true;
    export let updateModelValue = () => {};
</script>

<div class="searchLineContainer">
    {#if inputPadding}
    <SvgView
        svgUrl={magnifying}
        className="magnifying magnifyingContainer"
    />
    {/if}
    <input
            type="text"
            on:input={(e) => updateModelValue(e.target.value)}
            bind:value={modelValue}
            on:focus={() => inputPadding = false}
            on:blur={(e) => {
              if(e.target.value){
                inputPadding = false;
                return;
              }
              inputPadding = true;
            }}
            placeholder="Search here..."
            style={`paddingLeft: ${inputPadding ? 55 : 10}px`}
    />
</div>

<style>
    .searchLineContainer{
        margin-left: 200px;
        width: 500px;
        height: 60px;
        position: relative;
    }

    .searchLineContainer input{
        width: 100%;
        height: 100%;
        border-radius: 16px;
        background-color: #F9FAFB;
        border: none;
        outline: none;
        font-size: 18px;
        padding: 0 10px 0 55px;
    }
</style>