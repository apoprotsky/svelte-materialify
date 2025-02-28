<svelte:options immutable={true} />

<script context="module">
  export async function preload({ params }) {
    const res = await this.fetch(`api/${params.slug}.json`);
    const doc = await res.json();
    if (res.status === 200) {
      return { doc, name: params.slug };
    }
    this.error(res.status, doc.message);
    return { doc: '', name: '' };
  }
</script>

<script>
  import { Table, Icon } from 'sveltfy/src';
  import Layout from '@/components/doc/Layout.svelte';
  import { mdiPound } from '@mdi/js';

  function getKeyword(obj, keyword, _default) {
    if (obj.keywords.length !== 0) {
      const output = obj.keywords.find((x) => x.name === keyword);
      if (output) return output.description;
    }
    return _default;
  }

  export let doc;
  export let name;
</script>

<style global>
  section {
    margin-bottom: 48px;
  }
</style>

<Layout title={`${name} API`}>
  <h1 class="text-h3 mb-6">{name} API</h1>

  <section>
    <h3 class="heading text-h5 mb-2" id="props">
      <a href="#props" tabindex="-1" aria-hidden="true">
        <Icon path={mdiPound} size="18px" style="color: currentColor" class="mr-1" />
      </a>
      Props
    </h3>
    <Table style="border: thin solid var(--theme-dividers)">
      <thead>
        <tr>
          <th>Prop</th>
          <th>Default</th>
          <th>Description</th>
        </tr>
      </thead>
      <tbody>
        {#each doc.data as prop}
          {#if prop.visibility === 'public'}
            <tr>
              <td>
                <span class="font-weight-bold text-mono">{prop.name}</span>
                <span class="d-block text-caption text--secondary">
                  {prop.type.text}
                </span>
              </td>
              <td><code>{prop.defaultValue}</code></td>
              <td>{prop.description || 'Missing Description'}</td>
            </tr>
          {/if}
        {/each}
      </tbody>
    </Table>
  </section>

  {#if doc.events.length !== 0}
    <section>
      <h3 class="heading text-h5 mb-2" id="events">
        <a href="#events" tabindex="-1" aria-hidden="true">
          <Icon path={mdiPound} size="18px" style="color: currentColor" class="mr-1" />
        </a>
        Events
      </h3>
      <Table style="border: thin solid var(--theme-dividers)">
        <thead>
          <tr>
            <th>Event</th>
            <th>Returns</th>
            <th>Description</th>
          </tr>
        </thead>
        <tbody>
          {#each doc.events as event}
            <tr>
              <td class="font-weight-bold text-mono">{event.name}</td>
              <td>{getKeyword(event, 'returns', 'DOMEvent')}</td>
              <td>{event.description || 'DOM Event'}</td>
            </tr>
          {/each}
        </tbody>
      </Table>
    </section>
  {/if}

  {#if doc.slots.length !== 0}
    <section>
      <h3 class="heading text-h5 mb-2" id="slots">
        <a href="#slots" tabindex="-1" aria-hidden="true">
          <Icon path={mdiPound} size="18px" style="color: currentColor" class="mr-1" />
        </a>
        Slots
      </h3>
      <Table style="border: thin solid var(--theme-dividers)">
        <thead>
          <tr>
            <th>Slot</th>
            <th>Slot Props</th>
            <th>Description</th>
          </tr>
        </thead>
        <tbody>
          {#each doc.slots as slot}
            <tr>
              <td class="font-weight-bold text-mono">{slot.name}</td>
              <td>
                {#each slot.parameters as slotParam, i}
                  <code>{slotParam.name}</code>
                  {#if i < slot.parameters.length - 1}<span>, </span>{/if}
                {:else}None{/each}
              </td>
              <td>{slot.description || 'No Description'}</td>
            </tr>
          {/each}
        </tbody>
      </Table>
    </section>
  {/if}
</Layout>
