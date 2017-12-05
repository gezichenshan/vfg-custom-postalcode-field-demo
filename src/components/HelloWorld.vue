<template>
  <div class="panel-body">
    <vue-form-generator :schema="schema" :model="model" :options="formOptions"></vue-form-generator>
  </div>
</template>

<script>
import Vue from 'vue'
import VueFormGenerator from "vue-form-generator";
import fieldPostcode from "./fieldPostcode.vue";

Vue.use(VueFormGenerator);
Vue.component("fieldPostcode", fieldPostcode);

export default {
  data(){
    return{
      model: {
        id: 1,
        name: "John Doe",
        password: "J0hnD03!x4",
        skills: ["Javascript", "VueJS"],
        email: "john.doe@gmail.com",
        status: true
      },

      schema: {
        fields: [{
          type: "postcode",
          label: "Código postal de la empresa",
          model: "postalCode",
          maxlength: 5,
          required: true,
          validator: function (value, field, model) {
            console.log('tests')
          },
          styleClasses: 'col-12 col-sm-6 col-md-4',
        }]
      },

      formOptions: {
        validateAfterLoad: true,
        validateAfterChanged: true,
        validateDebounceTime: 500
      }
    }
  }
}
</script>
