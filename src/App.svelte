<script lang="ts">
  import DefaultForm from './lib/components/default-form.svelte';
  import UrlForm from './lib/components/url-form.svelte';
  import './lib/normalize.css';
  import './lib/app.css';

  let tab: 'default' | 'url' = 'default';

  const testConnection = () => {
    console.log('Testing a postgres connection');
  };

  const saveConnection = () => {
    console.log('Saving a postgres connection');
  };

  const connect = () => {
    console.log('Connecting a postgres database');
  };
</script>

<main>
  <div class="hero min-h-screen bg-base-200">
    <div class="hero-content text-center flex flex-col w-9/12">
      <div class="tabs">
        <div
          class="tab tab-bordered"
          class:tab-active={tab === 'default'}
          on:click={() => (tab = 'default')}
        >
          Default
        </div>
        <div
          class="tab tab-bordered"
          class:tab-active={tab === 'url'}
          on:click={() => (tab = 'url')}
        >
          Connect Url
        </div>
      </div>
      <div class="card flex-shrink-0 w-full max-w-sm shadow-2xl bg-base-100">
        <div class="card-body">
          {#if tab === 'default'}
            <DefaultForm
              on:test={testConnection}
              on:save={saveConnection}
              on:connect={connect}
            />
          {/if}
          {#if tab === 'url'}
            <UrlForm on:connect={connect} />
          {/if}
        </div>
      </div>
    </div>
  </div>
</main>
