<script>
  import { ProgressCircular } from 'sveltfy/src';
</script>

<div class="d-flex justify-center">
  <ProgressCircular />
  <div class="pl-2" />
  <ProgressCircular value={10} />
  <div class="pl-2" />
  <ProgressCircular value={25} />
  <div class="pl-2" />
  <ProgressCircular value={60} />
  <div class="pl-2" />
  <ProgressCircular value={100} />
</div>
