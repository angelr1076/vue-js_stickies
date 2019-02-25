<template>
  <div class="row">
    <app-reminder
      v-for="(reminder, index) in reminders"
      @click.native="deleteReminder(index)"
    >{{ reminder }}</app-reminder>
  </div>
</template>

<script>
import Reminder from "./Reminder.vue";

export default {
  props: {
    reminders: Array,
    required: true
  },
  components: {
    appReminder: Reminder
  },
  methods: {
    deleteReminder(index) {
      this.$emit("reminderDeleted", index);
    }
  }
};
</script>

<style>
</style>