<template>
  <main>

    <div class="body">
    <h1>Fast List</h1>
    <p>Catat Kegiatanmu Disini!!</p>
   </div>

    <div class="create-new">
      <input 
        type="text" 
        v-model="newTask" 
        placeholder="" 
        @keypress.enter="addTask" />
      <button class="comic-button" @click="addTask">Tambah</button>
    </div>

   
    
  

    


    <div class="tasks">
      <Task
        v-for="(task, i) in $store.state.tasks"
        :key="i"
        :task="task" />
    </div>

  </main>
</template>

<script>
export default {
  data (){
    return {
      newTask: ''
    }
  },
  methods: {
    addTask () {
      if (this.newTask) {
        this.$store.commit('ADD_TASK', this.newTask);
        this.newTask = '';
      }
    }
  }
}
</script>
