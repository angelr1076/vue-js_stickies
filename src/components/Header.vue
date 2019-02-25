<template>
  <div class="row">
    <div class="col-sm-12">
      <h3>Stickies Added</h3>
      <div></div>
      <div class="progress">
        <div
          class="progress-bar"
          role="progressbar"
          aria-valuenow="60"
          aria-valuemin="0"
          aria-valuemax="100"
          :style="{width: (reminderCount / maxReminders) * 100 + '%'}"
        >{{ reminderCount }} / {{ maxReminders }}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["reminderCount", "maxReminders"]
};
</script>