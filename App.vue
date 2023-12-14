<template>
  <div id="app">
    <h1>Vue Counter</h1>
    <p>Count: {{ count }}</p>
    <button id="add" @click="increment"> + 1 </button>
    <button id="sub" @click="decrement"> - 1 </button>
    <p>
      Message: <input v-model="message" disabled />
    </p>
  </div>
</template>

<script>
export default  {
  data() {
    return {
      count: 0,
      message: 'Hello I am a Counter',
    };
  },
  methods: {
    increment() {
      this.count++;
      this.updateMessage();
    },
    decrement() {
      this.count--;
      this.updateMessage();
    },
    updateMessage() {
      if (this.count === 0) {
        this.message = 'I am Zero Right now';
      } else if (this.count > 0) {
        this.message = 'Count is positive!';
      } else {
        this.message = 'Count is negative!';
      }
    },
  },
};
</script>

<style scoped>
#app {
  max-width: 400px;
  margin: 0 auto;
  text-align: center;
  padding: 20px;
}

h1 {
  font-size: 24px;
  margin-bottom: 20px;
}

p {
  font-size: 18px;
  margin-bottom: 10px;
}

button {
  padding: 10px 20px;
  font-size: 16px;
  cursor: pointer;
  color: white;
  border: none;
  border-radius: 5px;
  margin: 5px;
}

#add{
  background-color: green;
}

#sub {
  background-color: red;
}
#add:hover{
  background-color: darkgreen;
}

#sub:hover{
  background-color: darkred;
}

input {
  padding: 10px;
  font-size: 16px;
}

</style>

