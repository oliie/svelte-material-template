<script>
    import Button, { Label, Icon, Group } from '@smui/button';
    import Checkbox from '@smui/checkbox';
    import FormField from '@smui/form-field';
    import Slider from '@smui/slider';

    let clicked = 0;
    let selected = false;
    let value = 0;
</script>

<style lang="scss">
    .grayed {
        opacity: 0.6;
    }
</style>

<div class="container">
    <div>
        <Button variant="outlined" on:click={() => clicked++}>
            <Icon class="material-icons">thumb_up</Icon>
            <Label>Click Me</Label>
        </Button>

        <Group>
            <Button
                color="secondary"
                variant="raised"
                on:click={() => clicked++}>
                One
            </Button>

            <Button variant="raised" on:click={() => clicked++}>Two</Button>

            <Button
                color="secondary"
                variant="raised"
                on:click={() => clicked++}>
                Three
            </Button>
        </Group>

        <Button variant="raised" color="secondary">Click Me</Button>

        <Button ripple={false} variant="raised">Click Me</Button>

        <Button dense={true} variant="unelevated">Click Me</Button>

        <p class="mdc-typography--body1">
            {#if clicked}
                You've clicked the button {clicked} time{clicked === 1 ? '' : 's'}.
            {:else}
                <span class="grayed">You haven't clicked the button.</span>
            {/if}
        </p>
    </div>

    <div>
        <FormField>
            <Checkbox bind:checked={selected} />
            <span slot="label">Check me.</span>
        </FormField>
    </div>

    <div>
        <Slider
            discrete
            displayMarkers
            min={-10}
            max={10}
            step={1}
            bind:value />
    </div>
</div>
