<script>
    import Button, { Label } from '@smui/button';
    import {fade} from "svelte/transition";
    import '@material/elevation/mdc-elevation.scss';

    var value = 30.0;
    const increment = 0.5;
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
    <Button on:click|once={onClick} variant="outlined" touch="true" class="mdc-elevation--z2" style="border-color: #595959">
        <Label class="mdc-typography--button">TAP</Label>
    </Button>
</div>

<div class="earth-container">
    <img src="/images/Earth_Eastern_Hemisphere.svg" alt="Earth" class="earth" style="filter:brightness({value}%)">
    {#if show_icon}
        <a href="./amianto-aria" class="air-icon">
            <sub class="mdc-typography--subtitle1 icon-subtitle icon-sub-air" in:fade={{duration: 1000}}>Amianto nell'aria</sub>
            <img src="/images/air_icon.svg" alt="air" class="icon-hover" in:fade={{duration: 1000}}>
        </a>
        <a href="./amianto-terra" class="earth-icon">
            <sub class="mdc-typography--subtitle1 icon-subtitle icon-sub-earth" in:fade={{duration: 1000}}>Amianto nella terra</sub>
            <img src="/images/earth_icon.svg" alt="earth" class="icon-hover" in:fade={{duration: 1000}}>
        </a>
        <a href="./amianto-acqua" class="water-icon">
            <sub class="mdc-typography--subtitle1 icon-subtitle icon-sub-water" in:fade={{duration: 1000}}>Amianto nell'acqua</sub>
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
}

.earth{
    width: 100%;
    max-width: 600px;
    max-height: 70vh;
    object-fit: contain;
}

.icon-subtitle{
    position: absolute;
    color: var(--text-color);
    text-decoration: none;
    white-space: nowrap;
}

.icon-sub-air{
    left: 25%;
    top: -35%;
    transform: translate(-50%,-50%);
}

.icon-sub-earth{
    left: 75%;
    top: -35%;
    transform: translate(-50%,-50%);
}

.icon-sub-water{
    left: 50%;
    top: 135%;
    transform: translate(-50%,-50%);
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

</style>