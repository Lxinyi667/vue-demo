<template>
    <div class="custom-page">
        <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />
      <h1>{{ title }}</h1>
      <input v-model="newItem" @keyup.enter="addItem" placeholder="Add a new item" />
      <img alt="Vue logo" class="logo" src="https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fc-ssl.duitang.com%2Fuploads%2Fblog%2F202109%2F18%2F20210918001105_2066b.thumb.1000_0.jpeg&refer=http%3A%2F%2Fc-ssl.duitang.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1700965490&t=1d7650a39ccf61d9fe2cabdd281d1a55" width="125" height="125" />
      <ul>
        <li v-for="(item, index) in items" :key="index">{{ item }} 
            <button @click="removeItem(index)">Remove</button>
        </li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        title: 'Custom Vue Page',
        newItem: '',
        items: []
      }
    },
    methods: {
      addItem() {
        if (this.newItem) {
          this.items.push(this.newItem);
          this.newItem = '';
        }
      },
      removeItem(index) {
        this.items.splice(index, 1);
      }
    }
  }
  </script>
  
  <style scoped>
  .custom-page {
    text-align: center;
    padding: 20px;
    background-color: #f2f2f2;
  }
  
  h1 {
    color: #42b983;
    font-size: 24px;
    margin-bottom: 10px;
  }
  
  input {
    width: 100%;
    padding: 10px;
    margin-bottom: 10px;
  }
  
  ul {
    list-style: none;
    padding: 0;
  }
  
  li {
    background-color: #fff;
    border: 1px solid #ddd;
    padding: 10px;
    margin: 5px 0;
    display: flex;
    justify-content: space-between;
  }
  
  button {
    background-color: #ff5733;
    color: white;
    border: none;
    padding: 5px 10px;
    cursor: pointer;
  }
  </style>
  