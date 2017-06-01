<template>
<div class="home">
  <div v-for="task in this.tasks">
    <div class="demo-card-wide mdl-card mdl-shadow--2dp task">
      <div class="mdl-card__title">
        <h2 class="mdl-card__title-text">{{task.name}}</h2>
      </div>
      <div class="mdl-card__menu">
        <button class="mdl-button mdl-button--icon mdl-js-button mdl-js-ripple-effect">
          <i class="material-icons">share</i>
        </button>
      </div>
    </div>
  </div>
  <div class="button-container">
    <button class="button mdl-button mdl-js-button mdl-button--fab mdl-button--colored" @click="addTask">
      <i class="material-icons">add</i>
    </button>
  </div>
</div>
</template>

<script>
export default {
  name: 'home',
  data () {
    return {
      msg: 'Welcome to Your Vue.js PWA',
      tasks: []
    }
  },
  methods: {
    addTask: function () {
      this.tasks.push(
        {
          'name': `task n°${this.tasks.length + 1}`,
          'done': false
        }
      )
    }
  }
}
  </script>
 
<style scoped>

  .home {
    height: 100%;
    width: 100%;
  }

  .task {
    min-height: 0;
    width: initial;
    display: flex;
    flex: 1;
    margin-bottom: 5px;
  }

  .button {
    margin: 10px;
  }

  .button-container {
    position: fixed;
    display: flex;
    flex-direction: row-reverse;
    left: 0;
    bottom: 0;
    width: 100%;
    z-index: 1;
  }
</style>
