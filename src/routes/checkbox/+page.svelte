<script lang="ts">
  import Checkbox from "@smui/checkbox";
  let status = false;
  $: statusAsString = status ? "checked" : "unchecked";

  const events = ["First event", "Second event", "Third event"];
  let selectedEvents: string[] = [];
  $: selectedEventsStr = selectedEvents.length
    ? selectedEvents.join(", ") + ` (${selectedEvents.length})`
    : "No event selected (0)";
  $: spanColor = status ? "#0F0" : "#F00";
</script>

<div style="display: flex; flex-direction: row; align-items:center;">
  <Checkbox bind:checked={status} />
  <p>
    The checkbox is <span style="color: {spanColor}; font-weight: bold;"
      >{statusAsString}</span
    >
  </p>
</div>
<hr />
{#each events as event}
  <div style="display: flex; flex-direction: row; align-items: center;">
    <Checkbox bind:group={selectedEvents} value={event} />
    <span>{event}</span>
  </div>
{/each}
<p>{selectedEventsStr}</p>
