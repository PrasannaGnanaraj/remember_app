<script>
  export let Userimage;
</script>

<div class="bg-black p-4">
  <h1 class="text-white">Remember</h1>
  <slot />
  <img src={Userimage} class="float-right" alt="User Image" />
</div>
