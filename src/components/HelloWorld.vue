<template>
  <div class="hello">
    <input type="text" v-model="inputValue" @keyup="addLiat($event)">
    <br>
    <ul>
      <!-- <li v-for="(item,index) in list" :key="index">{{item}}</li> -->
      <todoItem
        v-for="(item,index) in list"
        :key="index"
        :content="item"
        :index="index"
        @delete="deleteItem"
      ></todoItem>
    </ul>
  </div>
</template>

<script>
import todoItem from "./todoItem";
export default {
  name: "HelloWorld",
  components: {
    todoItem
  },
  data() {
    return {
      inputValue: "",
      list: []
    };
  },
  methods: {
    addLiat(e) {
      if (e.keyCode == 13) {
        this.list.push(this.inputValue);
        this.inputValue = "";
      }
    },
    deleteItem(index) {
      console.log(index);
      this.list.splice(index, 1);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
