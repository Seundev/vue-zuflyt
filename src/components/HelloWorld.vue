<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>{{ count }}</p>
    <button @click="incrementCount">Increment</button>
    <button @click="decrementCount">decrement</button>
    <button @click="reset">reset</button>
    <p v-if="inventory >= 10 && inventory ">we have {{ inventory }} items in stock.</p>
    <p v-else-if="inventory  <= 9">Hurry, we are running low.</p>
    <p v-else="inventory== 0">sold out, check back later. </later></p>
    <p v-for="student in students" :key="student.id"> {{student.name}} {{student.age}}</p>
    <p>What is your name?</p>
    <input v-model="username">
    <p>{{username}}</p>
    <button v-show="username" @click="handleSubmit">submit</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String,
  },

  data() {
    return {
      count: 0,
      inventory: 10,
      students: [
        {id: 1, name: "Seun", age: 29},
        {id: 2, name: "Faith", age:26},
      ],
      username: "Seun",

    };
  },

  methods: {
    incrementCount() {
      this.count++;
    },

    decrementCount() {
      this.count--;
    },

    reset() {
      this.count = 0;
    },

    handleSubmit() {
      console.log("submitted")
    }
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
