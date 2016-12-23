<template>
    <div class="test">
      <input type="text" v-model="title"><br />
      <h1>{{title}}</h1>
      <p v-if="showName">{{user.firstName}}</p>
      <p v-else>Nobody</p>
      <ul>
        <li v-for="item in items">{{item.title}}</li>
      </ul>
      <button v-on:click="greet('Helo World')">Say Greeting</button>
      <br />
      <input type="text" v-on:keyup="pressKey" v-on:keyup.enter="enterHit">
      <hr />
      <label>First Name: </label><input type="text" v-model="user.firstName">
      <br />
      <label>Last Name: </label><input type="text" v-model="user.lastName">
      <h3>{{fullName}}</h3>
    </div>
</template>

<script>
  export default {
    name: 'test',
    data() {
      return {
        title: 'Hello World',
        user: {
          firstName: 'John',
          lastName: 'Doe'
        },
        showName: true,
        items: [
          {title: 'Item one'},
          {title: 'Item two'},
          {title: 'Item three'}
        ]
      }
    },
    methods: {
      greet: function(greeting){
        alert(greeting);
      },
      pressKey: function(event){
        console.log(event.target.value);
      },
      enterHit: function(){
        console.log('You pressed "Enter"');
      }
    },
    computed: {
      fullName: function(){
        return this.user.firstName + ' ' + this.user.lastName;
      }
    }
  }
</script>

<style scoped>

</style>
