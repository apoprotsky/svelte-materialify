<script>
  import Playground from '@/components/doc/Playground.svelte';
  import { Button, Icon } from 'sveltfy/src';
  import { mdiHome } from '@mdi/js';

  const variants = ['depressed', 'outlined', 'rounded', 'text', 'fab', 'icon', 'tile'];

  const controls = {
    block: { type: 'switch' },
    disabled: { type: 'switch' },
    active: { type: 'switch' },
    size: {
      type: 'select',
      items: ['x-small', 'small', 'default', 'large', 'x-large'],
      mandatory: true,
    },
  };

  const formatVariant = (v) => Object.fromEntries(v.map((i) => [i, true]));

  let values = {
    variants: [],
    block: false,
    disabled: false,
    active: false,
    size: 'default',
  };
</script>

<Playground {controls} {variants} bind:values>
  <Button
    block={values.block}
    disabled={values.disabled}
    active={values.active}
    size={values.size}
    {...formatVariant(values.variants)}>
    {#if values.variants.includes('icon') || values.variants.includes('fab')}
      <Icon path={mdiHome} />
    {:else}Click Me{/if}
  </Button>
</Playground>
