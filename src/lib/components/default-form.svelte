<script lang="ts">
  import { createEventDispatcher } from 'svelte';

  const dispatch = createEventDispatcher();

  const testConnection = () => {
    dispatch('test');
  };

  const saveConnection = () => {
    dispatch('save');
  };

  const connect = () => {
    dispatch('connect');
  };
</script>

<div class="form-control flex-row items-center justify-center">
  <label class="label mr-4" for="host">
    <span class="label-text">Host</span>
  </label>
  <input
    type="text"
    placeholder="localhost"
    class="input input-bordered input-sm"
  />
</div>
<div class="form-control flex-row items-center justify-center">
  <label class="label mr-4" for="port">
    <span class="label-text">Port</span>
  </label>
  <input type="text" placeholder="5432" class="input input-bordered input-sm" />
</div>
<div class="form-control flex-row items-center justify-center">
  <label class="label mr-4" for="username">
    <span class="label-text">Username</span>
  </label>
  <input
    type="text"
    placeholder="postgres"
    class="input input-bordered input-sm"
  />
</div>
<div class="form-control flex-row items-center justify-center">
  <label class="label mr-4" for="password">
    <span class="label-text">Password</span>
  </label>
  <input
    type="text"
    placeholder="postgres"
    class="input input-bordered input-sm"
  />
</div>
<div class="form-control flex-row items-center justify-center">
  <label class="label mr-4" for="database">
    <span class="label-text">Database</span>
  </label>
  <input
    type="text"
    placeholder="postgres"
    class="input input-bordered input-sm"
  />
</div>
<div class="form-control flex-row items-center">
  <label class="label cursor-pointer">
    <input type="checkbox" checked class="checkbox mr-4" />
    <span class="label-text">SSL</span>
  </label>
</div>
<div class="form-control mt-6 flex flex-row justify-end">
  <button class="btn normal-case btn-sm mr-4" on:click={testConnection}
    >Test</button
  >
  <button class="btn normal-case btn-sm mr-4" on:click={saveConnection}
    >Save</button
  >
  <button class="btn normal-case btn-sm" on:click={connect}>Connect</button>
</div>
