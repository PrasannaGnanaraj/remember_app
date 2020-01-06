<script>
  import Header from "./Header.svelte";
  import Notes from "./Notes.svelte";
  import { onMount } from "svelte";

  const GOOGLE_BUTTON_ID = "google-sign-in-button";
  let Userimage, UserId;
  window.onSignIn = googleUser => {
    const profile = googleUser.getBasicProfile();
    Userimage = profile.getImageUrl();
    UserId = profile.getId();
  };
</script>

<Header {Userimage}>
  <div class="g-signin2" data-onsuccess="onSignIn" />
</Header>
{#if UserId}
  <Notes />
{/if}
