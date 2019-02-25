<template>
  <div class="row">
    <form>
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
        <h3>Sticky</h3>
        <textarea class="form-control" rows="3" v-model="reminder"></textarea>
      </div>
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
        <button class="btn btn-primary" @click.prevent="createNew">Add Sticky</button>
      </div>
    </form>
  </div>
</template>

<script>
import Reminder from "./Reminder.vue";

export default {
  data: function() {
    return {
      reminder: ""
    };
  },
  methods: {
    createNew() {
      this.$emit("reminderAdded", this.reminder);
      this.reminder = "";
    }
  }
};
</script>

<style>
</style>