<script>
  import { Icon } from 'sveltfy/src';
  import { mdiAccount, mdiHome } from '@mdi/js';
  import { faAward, faCamera } from '@fortawesome/free-solid-svg-icons';
</script>

<div class="d-flex justify-space-between">
  <Icon class="primary-text" path={mdiHome} />
  <Icon class="blue-text" path={mdiAccount} />
  <Icon
    class="indigo-text"
    path={faAward.icon[4]}
    viewWidth={faAward.icon[0]}
    viewHeight={faAward.icon[1]} />
  <Icon
    class="orange-text"
    path={faCamera.icon[4]}
    viewWidth={faCamera.icon[0]}
    viewHeight={faCamera.icon[1]} />
</div>
