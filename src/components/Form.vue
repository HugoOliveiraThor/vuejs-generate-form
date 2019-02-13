<template>
  <div class="VueForm">
    <template v-for="(field,idx) in schema.fields">
        <component 
          :is="field.type"
          :key="field + idx" 
          :field="field" 
          :data.sync="data[field.name]"></component>
</template>
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
        required:false
      },
      data: {
        required: false
      }
    }
  }
</script>

<style scoped>
  
</style>