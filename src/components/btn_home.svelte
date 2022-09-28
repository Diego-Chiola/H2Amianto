<script>
    import Button, { Label } from '@smui/button';
    export let home_path;
</script>

<div class="home-btn">
    <Button href="{home_path}" touch="true" style="text-decoration:none">
        <Label class="mdc-typography--button">home</Label>
    </Button>
</div>

<style>
    .home-btn{
        text-decoration: none;
        margin: 5px 0px 0 10px;
    }

    @media screen and (min-width: 1160px) and (hover:hover){
        .home-btn{
            display: none;
        }
    }

    @media screen and (min-width: 1281px){
        .home-btn{
            display: none;
        }
    }
</style>