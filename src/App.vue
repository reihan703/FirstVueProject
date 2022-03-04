<template>
  <h1>{{title}}</h1>
  <input type="text" ref="name">
  <button @click="handleClick">click here</button>
  <Modal />
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  data(){
    return{
      title:'MyApp'
    }
  },
  methods:{
    handleClick(){
      console.log(this.$refs.name)
      this.$refs.name.classList.add('active')
    }
  },
  components:{
    Modal
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1{
  border-bottom: 1px solid gray;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
