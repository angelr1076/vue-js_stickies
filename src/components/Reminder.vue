<template>
  <div class="col-sm-6 col-md-4 col-lg-3">
    <div class="panel panel default">
      <div class="panel-body reminder">
        <slot></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    reminders: Array,
    required: true
  }
};
</script>

<style>
.panel-body {
  font-size: 24px;
  color: #201d1d;
  background-color: #ebe0e0;
  border-radius: 5px;
  box-shadow: 0 1px 3px black;
}

.reminder {
  cursor: pointer;
}

.reminder:hover {
  background-color: #ffe2e2;
}
</style>