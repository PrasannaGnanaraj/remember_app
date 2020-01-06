<script>
  export let Userimage;
</script>

<div class="bg-black p-4 flex">
  <h1 class="text-white flex-1 w-full my-auto">Remember</h1>
  {#if Userimage}
    <img src={Userimage} alt="User Image" />
  {:else}
    <slot />
  {/if}
</div>
