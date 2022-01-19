<template>
  <!--所有的item都展示同一个图片, 同一个文字-->
  <!-- <div class="tab-bar-item" @click="itemClick">
    <div v-if="!isActive"><slot name="item-icon"></slot></div>
    <div v-else><slot name="item-icon-active"></slot></div>
    <div :style="activeStyle"><slot name="item-text"></slot></div>
  </div> -->

 <div class="tab-bar-item" @click="itemClick1" path="/home">
  
    <div v-if="!isActive1"> <img src="~assets/img/tabbar/home.svg" alt=""></div>
    <div v-else> <img  src="~assets/img/tabbar/home_active.svg" alt=""></div>
    <div :style="activeStyle1">  <div>首页</div></div>

  </div>

  <div class="tab-bar-item" @click="itemClick2" path="/category">
 
    <div v-if="!isActive2"> <img src="~assets/img/tabbar/category.svg" alt=""></div>
    <div v-else> <img  src="~assets/img/tabbar/category_active.svg" alt=""></div>
    <div :style="activeStyle2">  <div>分类</div></div>
    
  </div>


  <div class="tab-bar-item" @click="itemClick3" path="/cart">

    <div v-if="!isActive3"> <img src="~assets/img/tabbar/shopcart.svg" alt=""></div>
    <div v-else> <img src="~assets/img/tabbar/shopcart_active.svg" alt=""></div>
    <div :style="activeStyle3">  <div>购物车</div></div>

  </div>


  <div class="tab-bar-item" @click="itemClick4" path="/profile">
   
    <div v-if="!isActive4"> <img src="~assets/img/tabbar/profile.svg" alt=""></div>
    <div v-else> <img  src="~assets/img/tabbar/profile_active.svg" alt=""></div>
    <div :style="activeStyle4"> 我的</div>

  </div>




</template>

<script>

  export default {
    name: "TabBarItem",
    props: {
      path: String,
      activeColor: {
        type: String,
        default: 'red'
      }
    },
    data() {
      return {
        // isActive: true
        tz1:"/home",
        tz2:"/category",
        tz3:"/cart",
        tz4:"/profile",
      }
    },
    computed: {
      isActive1() {
        // /home -> item1(/home) = true
        // /home -> item1(/category) = false
        // /home -> item1(/cart) = true
        // /home -> item1(/profile) = true
        return this.$route.path.indexOf(this.tz1) !== -1
      },
      isActive2() {
        return this.$route.path.indexOf(this.tz2) !== -1
      },
       isActive3() {
        return this.$route.path.indexOf(this.tz3) !== -1
      },
       isActive4() {
        return this.$route.path.indexOf(this.tz4) !== -1
      },
      activeStyle1() {
        return this.isActive1 ? {color: this.activeColor} : {}
      },
       activeStyle2() {
        return this.isActive2 ? {color: this.activeColor} : {}
      },
       activeStyle3() {
        return this.isActive3 ? {color: this.activeColor} : {}
      },
       activeStyle4() {
        return this.isActive4 ? {color: this.activeColor} : {}
      },
    },
    methods: {
      itemClick1() {
        // alert(this.$route.path.indexOf(this.path));
         this.$router.replace(this.tz1)
      },
       itemClick2() {
       
         this.$router.replace(this.tz2)
      },
       itemClick3() {
       
         this.$router.replace(this.tz3)
      },
       itemClick4() {
       
         this.$router.replace(this.tz4)
      },
    }
  }
</script>

<style scoped>
  .tab-bar-item {
    flex: 1;
    text-align: center;
    height: 49px;
    font-size: 14px;
  }

  .tab-bar-item img {
    width: 24px;
    height: 24px;
    margin-top: 3px;
    vertical-align: middle;
    margin-bottom: 2px;
  }
</style>
