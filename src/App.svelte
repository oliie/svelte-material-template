<script>
    import Button, { Label, Icon } from '@smui/button';

    let clicked = 0;
</script>

<style lang="scss">
    .grayed {
        opacity: 0.6;
    }
</style>

<div class="container">
    <Button variant="outlined" on:click={() => clicked++}>
        <Icon class="material-icons">thumb_up</Icon>
        <Label>Click Me</Label>
    </Button>

    <Button variant="raised" color="secondary">Click Me</Button>

    <Button ripple="false" variant="raised">Click Me</Button>

    <Button dense={true} variant="unelevated">Click Me</Button>

    <p class="mdc-typography--body1">
        {#if clicked}
            You've clicked the button {clicked} time{clicked === 1 ? '' : 's'}.
        {:else}
            <span class="grayed">You haven't clicked the button.</span>
        {/if}
    </p>
</div>
