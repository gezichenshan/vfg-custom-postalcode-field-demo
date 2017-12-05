<template>
  <input
      class="form-control"
      type="tel"
      v-model="value"
      :disabled="disabled"
      :maxlength="schema.maxlength"
      :placeholder="schema.placeholder"
      :readonly="schema.readonly"
      @input="onEnter($event)"
      >
</template>

<script>
  import { abstractField } from "vue-form-generator";
  export default {
    mixins: [ abstractField ],
    methods: {
      onEnter(event){
        this.value = this.value.replace(/[^0-9-]+/,'')
      }
    }
  };
</script>
