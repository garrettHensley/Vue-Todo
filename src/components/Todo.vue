<template>
  <div>
    <span v-if="!editting">{{ text }}</span>
    <input v-if="editting" type="text" :value="text" />
<div class="flexme">
    <button @click="edit()">{{ Edit }}</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      editting: false,
      Edit: "Edit",
    };
  },
  props: {
    text: String,
  },
  methods: {
    edit() {
      if (this.editting) {
        this.editting = false;
        this.Edit = "Edit";
      } else {
        this.editting = true;
        this.Edit = "Done";
      }
    },
  },
  computed: {},
};
</script>

<style scoped>
span {
  margin-right: 2em;
}
.flexme {
  display: inline-flex;
  justify-content: flex-end;
}
</style>
