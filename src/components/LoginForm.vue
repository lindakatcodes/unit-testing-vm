<template>
  <form @submit.prevent="onSubmit">
    <!-- Best practice in case you've got multiple inputs, since using class or id could change:
    <input data-testid="name-input" type="text" v-model="name"/>
    -->
    <input type="text" v-model="name" />
    <button type="submit">Submit</button>
  </form>
</template>

<script>
  export default {
    data() {
      return {
        name: ''
      };
    },
    methods: {
      onSubmit() {
        this.$emit('formSubmitted', { name: this.name });
      }
    }
  };
</script>
