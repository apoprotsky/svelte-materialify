<script>
  import Playground from '@/components/doc/Playground.svelte';
  import { Avatar, Icon } from 'sveltfy/src';
  import { mdiHome } from '@mdi/js';

  const controls = {
    size: { type: 'slider' },
    tile: { type: 'switch' },
    icon: { type: 'switch' },
    color: {
      type: 'select',
      items: ['primary', 'secondary', 'success', 'error', 'info'],
    },
  };

  let values = {
    variants: [],
    size: 48,
    tile: false,
    icon: false,
    color: 'primary',
  };
</script>

<Playground {controls} bind:values>
  <Avatar tile={values.tile} size="{values.size}px" class="{values.color}-color">
    {#if values.icon}
      <Icon path={mdiHome} />
    {:else}MS{/if}
  </Avatar>
</Playground>
