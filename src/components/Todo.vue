<template>
  <div>
    <div class="inputContent">
      <input
        type="text"
        v-model="myTodo"
        @keyup.enter="handleClick"
        class="input"
      >
      <button @click="handleClick" class="button">添加</button>
      <button @click="clearDone" class="button">清空</button>
    </div>

    <hr>

    <div class="content">
      <p>剩余任务：{{remain}}/{{todos.length}}</p>
      <ul>
        <li
          :class="{'done':todo.done}"
          @click="toggle(index)"
          v-for="(todo,index) in todos"
          :key="index"
        >
          {{todo.text}}
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: "My TODO LIST",
      subTitle: "this is a page records all todos in my day life...",
      // 用来双向绑定输入框中的内容
      myTodo: "",
      todos: [
        { text: "给手机充话费", done: false },
        { text: "和朋友一块打球", done: false },
        { text: "晚上看电影", done: true }
      ]
    };
  },
  computed: {
    remain() {
      // 过滤已经完成的
      return this.todos.filter(v => !v.done).length;
    }
  },
  methods: {
    handleClick() {
      if (!this.myTodo) {
        alert("输入内容不能为空！");
        return;
      }
      this.todos.push({
        text: this.myTodo,
        done: false
      });
      this.myTodo = "";
    },
    toggle(index) {
      this.todos[index].done = !this.todos[index].done;
    },
    clearDone() {
      // 过滤已经完成的
      this.todos = this.todos.filter(v => !v.done);
    }
  }
};
</script>

<style scoped>
.inputContent {
  text-align: center;
}

li.done {
  text-decoration: line-through;
  color: red;
}

.content {
  position: fixed;
  left: 35%;
  top: 30%;
}

.button{
  top: 60px;
  width: 200rpx;
  display: inline;
}

.input{
  border: solid 2rpx;
  margin-top: 30rpx;
  margin-bottom: 30rpx;
  position: fixed;
  width: 80%;
  left: 10%;
}
</style>
