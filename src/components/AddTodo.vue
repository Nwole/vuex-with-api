<template>
  <div>
    <h2>AddTodo</h2>
    <div >
      <v-form >
    <v-containe>
      <v-row>
        <v-col cols="6">
          <v-text-field
            v-model="title"
            outlined
            label="add todo..."
            type="text"
          >
          </v-text-field>
        </v-col>
       <v-col  cols="6">
      <v-btn
      color="red"
      dark
      @click="onSubmit"
    >
      submit
    </v-btn>
        </v-col>
      </v-row>
    </v-containe>
  </v-form>
    </div>
  </div>
</template>

<script>
import { mapActions } from 'vuex';
export default {
name: 'AddTodo',
methods:{
    ...mapActions(['addTodo']),

    onSubmit(e){
        e.preventDefault()
        if(this.title.trim() !=='')
        this.addTodo(this.title)
        this.title = ""
    }
},
data(){
    return{
        title: ''
    }
},

}
</script>

<style>


</style>