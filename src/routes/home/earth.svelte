<script>
    import Button, { Label } from '@smui/button';
    import {fade} from "svelte/transition";
    import '@material/elevation/mdc-elevation.scss';

    var value = 30.0;
    var increment = 0.5;
    let tap_class = "";
    let show_icon = false;

    function onClick() {
        tap_class = "tap-box-hidden";
        show_icon = true;
        var interval = setInterval(() => {
        value += increment;
        if (value >= 80) {
            clearInterval(interval);
        }
    }, 8);
}
</script>

<div class="tap-box {tap_class}" transition:fade>
    <Button on:click|once={onClick} variant="outlined" touch="true" class="mdc-elevation--z5" style="border-color: #595959">
        <Label class="mdc-typography--button">TAP</Label>
    </Button>
</div>

<div class="earth-container">
    <img src="/images/Earth_Eastern_Hemisphere.svg" alt="Earth" class="earth" style="filter:brightness({value}%)">
    {#if show_icon}
        <a href="/" class="air-icon">
            <img src="/images/air_icon.svg" alt="air" class="icon-hover" in:fade={{duration: 1000}}>
        </a>
        <a href="/" class="earth-icon">
            <img src="/images/earth_icon.svg" alt="earth" class="icon-hover" in:fade={{duration: 1000}}>
        </a>
        <a href="/" class="water-icon">
            <img src="/images/water_icon.svg" alt="water" class="icon-hover" in:fade={{duration: 1000}}>
        </a>
    {/if}
</div>

<style>

.tap-box{
    visibility: visible;
    opacity: 1;
    text-align: center;
}

.tap-box-hidden{
    visibility: hidden;
    opacity: 0;
    transition: visibility 0s 0.5s, opacity 0.5s linear;
    cursor: none;
}

.earth-container{
    position: relative;
    width: 100%;
    max-width: 600px;
    margin-left: auto;
    margin-right: auto;
    max-height: 70vh;
    /*transform: scale(100%);
    émargin-bottom: 1em;*/
}

.earth{
    width: 100%;
    max-width: 600px;
    max-height: 70vh;
    /*position: absolute;
    left: 50%;
    transform: translate(-50%, 0);*/
    object-fit: contain;
}

.air-icon{
    position: absolute;
    left: 25%;
    top: 25%;
    transform: translate(-50%,-50%);
}

.earth-icon{
    position: absolute;
    left: 75%;
    top: 25%;
    transform: translate(-50%,-50%);
}

.water-icon{
    position: absolute;
    left: 50%;
    top: 90%;
    transform: translate(-50%,-50%);
}

.icon-hover{
    transition: .4s ease-in-out;    
}

.icon-hover:hover{
    transform: scale(120%);
    filter: brightness(120%);
}

@media screen and (min-width: 460px){
   
}

</style>