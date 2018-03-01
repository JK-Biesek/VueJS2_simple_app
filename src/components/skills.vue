<template>
  <div class="hello">
  <div class="holder">
  <form @submit.prevent="addSkill">
    <input type="text" placeholder="Enter your skill" v-model="skill"   v-validate="'min:5'" name="skill">
    <transition name="alert-in">
    <p class="alert" v-if="errors.has('skill')">{{errors.first('skill')}}</p>
  </transition>
    </form>
    <ul>
      <transition-group name="list" enter-active-class="animated bounceInUp" leave-active-class="animated bounceOutDown">
      <li v-for="(data,index) in skills" :key='index'> {{data.skill}}
        
      <i class="fa fa-minus-circle" v-on:click="remove(index)"></i>
    </li>
    </transition-group>
    </ul>
  <p>Your skills </p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'skills',
  data(){
  return {
  skill: '',
  skills: [
    {"skill" : "Php"},
    {"skill" : "OOP"},
    {"skill" : "VueJs"},
      ]
    }
  },
  methods: {
    addSkill() {
    this.$validator.validateAll().then((result) =>{
    if(result){
    this.skills.push({skill: this.skill})
    this.skill = '';
    }
    })
    }
  },
  remove(id){
    this.skills.splice(id,1);
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style src="./style.css" scoped>

</style>
