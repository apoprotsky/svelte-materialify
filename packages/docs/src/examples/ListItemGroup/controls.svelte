<script>
  import { ListItemGroup, ListItem, Checkbox } from 'sveltfy/src';

  let value = ['foo'];
</script>

<div class="ml-auto mr-auto elevation-2" style="width:500px">
  <ListItemGroup multiple bind:value>
    <ListItem value="foo">
      Foo
      <span slot="append">
        <Checkbox value="foo" bind:group={value} />
      </span>
    </ListItem>
    <ListItem value="bar">
      Bar
      <span slot="append">
        <Checkbox value="bar" bind:group={value} />
      </span>
    </ListItem>
    <ListItem value="fizz">
      Fizz
      <span slot="append">
        <Checkbox value="fizz" bind:group={value} />
      </span>
    </ListItem>
    <ListItem value="buzz">
      Buzz
      <span slot="append">
        <Checkbox value="buzz" bind:group={value} />
      </span>
    </ListItem>
  </ListItemGroup>
</div>
