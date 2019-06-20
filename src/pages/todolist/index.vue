<template>
  <div>
    <p class="title">{{title}}</p>
    <p class="subTitle">{{subTitle}}</p>
    <Todo></Todo>
  </div>
</template>

<script>
import Todo from "@/components/Todo";

export default {
      components: {
      Todo
  },
  data() {
    return {
      title: "My TODO LIST",
      subTitle: "this is a page records all todos in my day life..."
    };
  }
};
</script>

<style scoped>
.title {
  text-align: center;
  color: red;
  font-size: 30px;
}

.subTitle {
  text-align: center;
  color: orange;
  font-size: 15px;
}
</style>
