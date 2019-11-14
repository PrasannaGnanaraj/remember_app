<script>
  import Note from "./Note.svelte";
  let serverUrl = "API_URL";
  let notesPromise = getNotes();

  async function getNotes() {
    const res = await fetch(serverUrl);
    const notes = await res.text();
    if (res.ok) {
      return JSON.parse(notes);
    } else {
      throw new Error(text);
    }
  }
</script>

<style>
  div {
    margin: 0.5em 0.5em;
  }
</style>

<div>
  {#await notesPromise}
    <p>...waiting</p>
  {:then notes}
    {#each notes as note}
      <Note {note} />
    {/each}
  {:catch error}
    <p>{error}</p>
  {/await}
</div>
