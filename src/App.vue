<template>
  <div class="container">
    <app-header :reminderCount="reminders.length" :maxReminders="maxReminders"></app-header>
    <div class="jumbotron">
      <app-new-reminder @reminderAdded="newReminder"></app-new-reminder>
    </div>
    <app-reminder-grid :reminders="reminders" @reminderDeleted="deleteReminder"></app-reminder-grid>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-danger">Hint: Click on a sticky to delete it.</div>
      </div>
    </div>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import ReminderGrid from "./components/ReminderGrid.vue";
import NewReminder from "./components/NewReminder.vue";

export default {
  data: function() {
    return {
      reminders: [],
      maxReminders: 8
    };
  },
  methods: {
    newReminder(reminder) {
      if (this.reminders.length >= this.maxReminders) {
        return alert("Remove some Stickies first!");
      }
      if (reminder.length <= 0) {
        return alert(`No blank Stickies allowed. Let's get creative!`);
      }
      this.reminders.push(reminder);
    },
    deleteReminder(index) {
      this.reminders.splice(index, 1);
    }
  },
  components: {
    appReminderGrid: ReminderGrid,
    appNewReminder: NewReminder,
    appHeader: Header
  }
};
</script>

<style>
body {
  font-family: "Prosto One", cursive;
}
</style>
