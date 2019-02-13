<template>
  <div id="app">
    <h-form :schema="formSchema" :data="formData">
    </h-form>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import HForm from './components/Form.vue'
import Teste from "./components/Teste.vue";
export default {
  name: 'app',
  components: {
    HForm,
    Teste
  },
  data() {
    return {
      formSchema: {
          fields: [{
              type: 'h',
              name: 'first_name',
              label: 'First name',
              placeholder: 'Enter first name'
            },
            {
              type: 'h-input',
              name: 'last_name',
              label: 'Last name',
              placeholder: 'Enter last name'
            },
            {
              type: 'h-checkbox',
              name: 'is_admin',
              label: 'Administrator',
              placeholder: 'Sure, why not'
            }
          ]
        },
        formData: {
          first_name: {
            value: 'John'
          },
          last_name: {
            value: 'Doe'
          },
          is_admin: {
            value: true
          }
        }
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
