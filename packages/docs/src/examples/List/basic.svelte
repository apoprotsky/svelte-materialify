<script>
  import { ListItem, Icon } from 'sveltfy/src';
  import { mdiHome } from '@mdi/js';
</script>

<div class="d-flex justify-center mt-2 mb-2">
  <div class="elevation-2" style="width:300px">
    <ListItem>List Item</ListItem>
    <ListItem>List Item <span slot="subtitle"> With a subtitle </span></ListItem>
    <ListItem>
      List Item (icon)
      <span slot="append">
        <Icon path={mdiHome} />
      </span>
      <span slot="subtitle">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsa, saepe. Quis nam non
        perferendis doloremque?
      </span>
    </ListItem>
  </div>
</div>
