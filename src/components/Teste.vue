<template>
  <div id="vue">
  <form @submit.prevent="submit">
    <div v-for="item, key in schema">
      <label :for="key + _uid">{{item.label}}</label> <!--key + _uid is used to generate unique ids, so you can click on the label-->
      <input v-if="item.type == 'text'" v-model="formData[key]" :id="key + _uid">
      <textarea v-else-if="item.type == 'textarea'" v-model="formData[key]" :id="key + _uid"></textarea>
      <template v-else-if="item.type == 'radio'" v-for="option in item.options">
        <input  type="radio" v-model="formData[key]" :value="option" :id="key + option + _uid">
        <label :for="key + option + _uid">{{option}}</label>
      </template>
    </div>
    <button type="submit">Submit</button>
  </form>
</div>

</template>

<script>
  export default {
    name:'Teste',
    data() {
      return {
        schema: {
        name: {
          type: 'text',
          label: 'What is your name?'
        },
        bio: {
          type: 'textarea',
          label: 'Write something about yourself'
        },
        gender: {
          type: 'radio',
          options: ['male', 'female', 'other'],
          label: 'What is your gender?'
        }
      },
      formData: {}
      }
    },
    methods: {
      submit(){
    	alert(JSON.stringify(this.formData, null, ' '))
    }
    }
  }
</script>

<style scoped>

</style>