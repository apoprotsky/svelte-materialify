<script>
  import { Alert, Icon } from 'sveltfy/src';
  import { mdiCheck, mdiThumbUp, mdiAlert } from '@mdi/js';
</script>

<Alert class="success-color" dense>
  <div slot="icon">
    <Icon path={mdiCheck} />
  </div>
  Lorem ipsum dolor sit amet consectetur adipisicing elit. Architecto, aperiam ad iure harum
  iste ea numquam quo accusamus blanditiis in.
</Alert>

<Alert class="primary-color" dense>
  <div slot="icon">
    <Icon path={mdiThumbUp} />
  </div>
  Lorem ipsum dolor sit amet consectetur adipisicing elit. Architecto, aperiam ad iure harum
  iste ea numquam quo accusamus blanditiis in.
</Alert>

<Alert class="error-text" dense outlined>
  <div slot="icon">
    <Icon path={mdiAlert} />
  </div>
  Lorem ipsum dolor sit amet consectetur adipisicing elit. Architecto, aperiam ad iure harum
  iste ea numquam quo accusamus blanditiis in.
</Alert>
