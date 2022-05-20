<template>
  <main>
    <h1>TO DO LIST</h1>
    <p>Create a list of tasks :</p>

    <div class="create-new">
      <input type="text" v-model="newTask" placeholder="Add a new task" @keypress.enter="addTask" />
      <button @click="addTask">ADD</button>
    </div>

    <div class="tasks">
      <Task v-for="(task, i) in $store.state.tasks"
      :key="i"
      :task="task" />
    </div>

    <div class="footer">
     <h3>Donate BTC 👇</h3>
     <br />
     <img src="https://i.ibb.co/JkbnDyf/BTC.png" />
     <br />
     <br />
     <p>BTC address: bc1qp4zxxj0k0whkm483qv5dk2rs6sgh2tt70h44rf</p>
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
    addTask (){
      if (this.newTask) {
        this.$store.commit('ADD_TASK', this.newTask);
        this.newTask = '';
      }
    }
  }
}
</script>

