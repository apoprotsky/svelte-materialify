<script>
  import { NavigationDrawer, List, ListItem, Button, Icon } from 'sveltfy/src';
  import { mdiViewDashboard, mdiAccountBox, mdiGavel } from '@mdi/js';
</script>

<div class="d-flex justify-center">
  <NavigationDrawer style="height:350px" class="primary-color theme--dark">
    <List>
      <ListItem>
        <span slot="prepend">
          <Icon path={mdiViewDashboard} />
        </span>
        Dashboard
      </ListItem>
      <ListItem>
        <span slot="prepend">
          <Icon path={mdiAccountBox} />
        </span>
        Account
      </ListItem>
      <ListItem>
        <span slot="prepend">
          <Icon path={mdiGavel} />
        </span>
        Admin
      </ListItem>
    </List>
    <span slot="append" class="pa-2">
      <Button block>Logout</Button>
    </span>
  </NavigationDrawer>
</div>
