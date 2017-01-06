<template>
  <div>
    <div class="search-bar2" v-if="type">
      <div class="icon icon-search pull-left bar2" ></div>
      <div class="placeholder pull-left word-pos">请输入歌名/歌手/专辑</div>
    </div>
    <div class="search-bar" v-if="!type">
      <div class="icon icon-search " style="margin-top: -2px;"></div>
      <div class="placeholder ">请输入歌名/歌手/专辑</div>
    </div>
  </div>
  <!--<div class="pos-top">-->
    <!--<div class="placeholder-container " id="placeholder"></div>-->
    <!--<div><i class="icon icon-search search-pos" ></i><input type="text" class="searchbar"  id="searchBar" placeholder="请输入歌名/歌手/专辑"/></div>-->
  <!--</div>-->
</template>

<script>
  export default {
    name: 'list-view',
    props: ['type'],
    created: function () {

    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .search-bar {
    height: 40px;
    line-height: 40px;
    border: none;
    margin: 20px;
    background-color: #605963;
    font-size: 16px;
    border-radius: 20px;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .search-bar2 {
    height: 40px;
    line-height: 40px;
    border: none;
    margin: 20px;
    background-color: #605963;
    font-size: 16px;
    border-radius: 20px;
  }
  .bar2 {
    margin-top: 1px;
    position: relative;
    left: 50%;
    margin-left: -110px;

  }
  .word-pos {
    position: relative;
    left: 50%;
    margin-left: -76px;
  }

  .placeholder {
    color: #d6d6d6;
  }


  /* icon */
  .icon {
    height: 35px;
    width: 35px;
  }

  .icon-search {
    background: url("../assets/search.png") no-repeat;
    background-size: 50% 50%;
    background-position: center;
  }
  .search-pos {
    margin-top: -1px;
    /*margin-left: 5px;*/
  }

</style>
