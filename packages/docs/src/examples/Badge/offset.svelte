<script>
  import { Button, Badge, Avatar, Icon } from 'sveltfy/src';
  import { mdiLock } from '@mdi/js';
</script>

<div class="d-flex pt-4 pb-4 justify-space-around">
  <Badge class="error-color" bordered offsetX={10} offsetY={10}>
    <Button class="error-color">Button</Button>
    <span slot="badge">
      <Icon path={mdiLock} />
    </span>
  </Badge>
  <Badge class="primary-color" dot bottom offsetX={10} offsetY={10}>
    <Avatar><img src="//picsum.photos/50" alt="profile" /></Avatar>
  </Badge>
  <Badge class="primary-color" bordered value={2} offsetX={16} offsetY={16}>
    <Avatar><img src="//picsum.photos/50" alt="profile" /></Avatar>
  </Badge>
</div>
