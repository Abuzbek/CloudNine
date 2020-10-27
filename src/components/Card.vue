<template>
  <div class="wrapper">
    <p class="title">{{ title }}</p>
    <img class="logo" :src="logo" alt="logo" />
    <p class="body">{{ body }}</p>
    <p class="price">От {{ price }} $</p>
    <button class="btn">
      Заказать
    </button>
  </div>
</template>

<script>
  export default {
    props: {
      title: {
        type: String,
        default: '',
      },
      logo: {
        type: String,
        default: '',
      },
      body: {
        type: String,
        default: '',
      },
      price: {
        type: String,
        default: '',
      },
    },
  };
</script>

<style lang="scss" scoped>
  .wrapper {
    display: flex;
    flex-direction: column;
    background: #ffffff;
    border-radius: 10px;
    padding: 3%;
    box-shadow: rgba(149, 157, 165, 0.2) 0px 8px 24px;
  }
  .title {
    margin: 0 auto;
    margin-bottom: 15%;
    font-weight: 600;
    font-size: 24px;
    line-height: 32px;
  }
  .logo {
    width: 100px;
    height: 100px;
    margin: 0 auto;
    margin-bottom: 15%;
  }
  .body {
    width: 100%;
  }
  .price {
    font-size: 24px;
    line-height: 32px;
  }
  .btn {
    background: #fff;
    cursor: pointer;
    padding: 5%;
    outline: none;
    margin: 0 auto;
    border-radius: 30px;
    color: #2824ea;
    border: 1px solid #2824ea;
    width: 75%;
    font-size: 18px;
    line-height: 24px;
  }
  .btn:hover {
    color: #fff;
    background: #2824ea;
  }
</style>
