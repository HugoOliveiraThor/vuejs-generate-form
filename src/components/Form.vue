<template>
  <div class="VueForm">
    <form @submit.prevent="submit">
      <template v-for="(field,idx) in schema.fields">
          <component 
            :is="field.type"
            :key="field + idx" 
            :field="field" 
            :data.sync="data[field.name]"></component>
</template>
  <button type="submit">Submit</button>
    </form>
  </div>
</template>

<script>
  import HCheckbox from './Checkbox'
  import HInput from './Input'
  export default {
    name: 'H-Form',
    components: {
      HCheckbox,
      HInput
    },
    props: {
      schema: {
        required: false
      },
      data: {
        required: false
      }
    },
    methods: {
      submit() {
      alert(JSON.stringify(this.data, null, ' '))
      }
    }
  }
</script>

<style scoped>
  
</style>