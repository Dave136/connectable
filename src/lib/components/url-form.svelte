<script lang="ts">
  import { createEventDispatcher } from 'svelte';

  const dispatch = createEventDispatcher();
  const connect = () => {
    dispatch('connect');
  };
</script>

<div class="form-control">
  <textarea
    class="textarea textarea-bordered h-24"
    placeholder="postgres://user@localhost/database"
  />
</div>

<div class="form-control mt-6 flex flex-row justify-end">
  <button class="btn normal-case btn-sm" on:click={connect}>Connect</button>
</div>
