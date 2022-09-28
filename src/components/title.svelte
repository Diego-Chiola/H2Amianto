<script>
    export let home_path;
</script>

<a href="{home_path}">
    <h1 class="mdc-typography--headline2" id="title">H<sub>2</sub>Amianto</h1>
</a>

<style>

    a{
        display: block;
        max-width: 320px;
        margin-left: auto;
        margin-right: auto;
        pointer-events: none;
    }

    h1{
        font-weight: 900;
        text-align: center;
        line-height: 66.8px;
        color: var(--primary-color);
        margin-top: 20px;
        margin-bottom: 20px;
    }

    sub{
        font-size: 2rem;
    }

    @media screen and (min-width: 1024px){
        a{
            pointer-events: visible;
        }
    }

</style>