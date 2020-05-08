<template>
  <div class="home">
    <header class="index-header">
      <a href="mine.html?cpid=0">
        <div class="header-user">
          <div class="user-btn"></div>
        </div>
      </a>
      <div class="header-logo"></div>
      <a href="search.html?cpid=0">
        <div class="header-search"></div>
      </a>
    </header>
  </div>
</template>

<script>
export default {
  name: 'home'
}
</script>
<style scoped lang="scss">
.home {
  display: flex;
  flex-flow: column;
  height: 100%;
  background: chartreuse;
  /* 头部 */
  .index-header {
    display: flex;
    height: 44px;
    justify-content: space-between;
    align-items: center;
    background: burlywood;
    padding: 0 10px;
    /* 头部用户图标 */
    .user-btn {
      width: 25px;
      height: 25px;
      background: url('../../assets/icon/user-btn.png') no-repeat;
      background-size: 100%;
    }
    /* 头部logo图标 */
    .header-logo {
      width: 94px;
      height: 28px;
      background: url('../../assets/logo.png');
      background-size: 100%;
    }

    /* 头部搜索图标 */
    .header-search {
      width: 25px;
      height: 25px;
      background: url('../../assets/icon/search.png');
      background-size: 100%;
    }
  }
}
</style>