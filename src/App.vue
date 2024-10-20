<template>
    <div class="container">
      <div v-awesome.red.big="'faruk'"></div>
      <div v-awesome.green.big="'faruk'"></div>
      <hr>
      <div v-user="uservalue"></div>
    </div>
</template>

<script>
export default {
  data(){
    return {
      uservalue: 'franky'
    }
  },
  directives: {
    'user': {
      bind(el, binding) {
        el.innerHTML = binding.value
      }
    }
  }
}
</script>