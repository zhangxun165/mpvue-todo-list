<template>
  <div>
    <div class="userinfo">
      <img class="userinfo-avatar" v-if="userInfo.avatarUrl" :src="userInfo.avatarUrl" background-size="cover" />
      <img class="userinfo-avatar" src="/static/images/user.png" background-size="cover" />
    </div>

    <p class="welcome">欢迎来到mpvue-todo-list</p>
  </div>
</template>

<script>
export default {
  data () {
    return {
      userInfo: {
        nickName: 'mpvue-todo-list',
        avatarUrl: 'http://mpvue.com/assets/logo.png'
      }
    }
  }
}
</script>

<style scoped>
.userinfo {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.userinfo-avatar {
  width: 128rpx;
  height: 128rpx;
  margin: 20rpx;
  border-radius: 50%;
}

.welcome{
  text-align: center;
}
</style>
