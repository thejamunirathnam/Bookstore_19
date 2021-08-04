<template>
  <div class="hello">
    <h1>heelo lifecycle</h1>
    <h2>Counter {{counter}}</h2>
    <h3 v-bind:title="title" v-on:click="handleclick">vbind attribute</h3>
    <input type="text" v-model="message"/>
    <h2>{{message}}</h2>

    <div v-if="conditionalseen">
       <HelloWorld titleprops="helloo propssssssssssssssss" titlenumber=34 :propsobj="todos"/>
    </div>
    <div v-else>
       <h3>Else condition in the conditional directiev</h3>
    </div>
    <div v-for="(item, index) in todos" :key="index">
    {{item.text}}
    </div>
    <p id="hello" class="newhello">
    {{counter}}
    </p>
    <h3>comuted properties {{compuetdmethod}}</h3>
  </div>
</template>



<script>
import HelloWorld from "../HelloWorld.vue"
export default {

	data() {
		return {
      counter:0,
      title: "You have started studying vuejs goodd",
      message : '',
      conditionalseen:true,
        todos: [
        { text: 'Learn JavaScript' },
        { text: 'Learn Vue' },
        { text: 'Build something awesome' }
      ]

		}
	},

  computed : {
       compuetdmethod(){
         return this.todos.length
       }
  },

   components: {
    // 'component-a': HelloWorld,
      HelloWorld
  },

  methods:{
    handleclick(){
      console.log("hande click")
      this.counter = this.counter+10;
    },
    add(){
       this.counter++;
    }
  },

}
</script>