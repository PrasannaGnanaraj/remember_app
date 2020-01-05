<script>
  import Header from "./Header.svelte";
  import Notes from "./Notes.svelte";
  import { onMount } from "svelte";

  const GOOGLE_BUTTON_ID = "google-sign-in-button";

  const onSignIn = googleUser => {
    const profile = googleUser.getBasicProfile();
    console.log("Name: " + profile.getName());
  };
</script>

<Header>
  <div class="g-signin2" data-onsuccess="onSignIn" />
</Header>
<Notes />
