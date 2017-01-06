<template>
  <div class="om-list-box">

      <div class="om-list om-list-img" v-for="item in list" @click="toPath(item.id)">
          <img :src="item.pic" class="om-list-src">
          <div class="om-list-title om-ellipsis">{{item.name}}</div>
          <div class="om-list-text om-ellipsis">{{item.info}}</div>
      </div>

  </div>
</template>

<script>
  export default {
    name: 'list-view',
    props: ['list'],
    created: function () {

    },
    methods: {
    	toPath: function (id) {
        window.location.href = '#/list?id='+id;
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .om-ellipsis {
    overflow:hidden;
    white-space:nowrap;
    text-overflow:ellipsis;
  }
  .om-list {
    position:relative;
    padding:10px 20px 10px 10px;
    border-bottom:1px solid #45424f;
    text-align:left;
  }
  .om-list .om-list-title {
    height:30px;
    line-height:30px;
    font-size:16px;
  }
  .om-list .om-list-text {
    height:20px;
    line-height:20px;
    font-size:14px;
  }
  .om-list:after {
    position:absolute;
    right:20px;
    top:50%;
    content:'';
    width:10px;
    height:10px;
    margin-top:-5px;
    border-top:1px solid #ddd;
    border-right:1px solid #ddd;
    -webkit-transform:rotate(45deg);
    transform:rotate(45deg);
  }
  .om-list.om-list-img {
    padding:10px 20px 10px 70px;
  }
  .om-list.om-list-img .om-list-src {
    position:absolute;
    left:0;
    top:10px;
    width:50px;
    height:50px;
  }

</style>
