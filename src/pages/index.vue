<template>
  <div class="index-container">
    <swipe></swipe>

    <router-link to="test"><search-bar :type="type"></search-bar></router-link>
    <div style="margin-left: 4%;">
      <h4 class="recommend-header">热门专栏</h4>
      <list v-bind:list="list"></list>
    </div>

  </div>
</template>
<script>
  import swipe from '../components/swipe.vue'
  import search from '../components/search-bar.vue'
  import list from '../components/list-view.vue'

  let listCache = localStorage.getItem('bangStorage');

  export default {
    name: 'index',
    data(){
        return {
          list: [
            {
              "id"  :" 17",
              "info" : "酷我最权威、播放量最高新歌尽在此榜～",
              "name":  "酷我新歌榜",
              "pic" :  "http://img1.kwcdn.kuwo.cn/star/upload/9/9/1481783631321_.png"
            },
            {
              "id"  :" 93",
              "info" : "收录一周播放次数涨幅最高的TOP200歌曲！",
              "name":  "酷我飙升榜",
              "pic" :  "http://img4.kwcdn.kuwo.cn/star/upload/9/9/1481783338617_.png"
            },
            {
              "id"  :" 130",
              "info" : "酷音乐流行榜是酷狗、酷我联合推出的权威性榜单，以用户真实搜索数据为基础客观、精准的反应了亿万网友对音乐的收听和喜爱情况。",
              "name":  "酷音乐流行榜",
              "pic" :  "http://img1.kwcdn.kuwo.cn/star/upload/5/5/1481781774229_.png"
            },
            {
              "id"  :" 62",
              "info" : "时下最热华语歌曲，尽在酷我华语榜",
              "name":  "酷我华语榜",
              "pic" :  "http://img2.kwcdn.kuwo.cn/star/upload/0/0/1481783520448_.png"
            },
            {
              "id"  :" 22",
              "info" : "酷我最权威、播放量最高新歌尽在此榜～",
              "name":  "酷我新歌榜",
              "pic" :  "http://img4.kwcdn.kuwo.cn/star/upload/10/10/1481783539562_.png"
            },
            {
              "id"  :" 63",
              "info" : "酷我最权威、播放量最高新歌尽在此榜～",
              "name":  "酷我新歌榜",
              "pic" :  "http://img2.kwcdn.kuwo.cn/star/upload/7/7/1481783803575_.png"
            }
          ]
          ,
          type: true
        }
    },
    components: {
      swipe,
       list,
      'search-bar': search
    },
    created: function () {
//      this.getList();
    },
    methods: {
      getList: function () {
        let self = this;
        if (!self.isLoadData()) {
          console.log(self.getStorage('bangStorage').list);
          self.list = self.getStorage('bangStorage').list;
          return;
        }
        self.$jsonp(apiHttp + '/bd/list', { callbackQuery: 'callback', bdfrom : "omwteam",c : "omwteamsdasdsaas22323" })
          .then(function (json) {
            self.list = [].concat(json.data.classify,json.data.world);

            localStorage.setItem('bangStorage',JSON.stringify({time:new Date().getTime(),list:self.list}));

        }).catch(function (error) {
            console.log(error);
          // Failed.
        })
      },
      /**
       * 获取缓存
       * @param name
       * @returns {undefined}
       */
      getStorage:function (name){
        return localStorage.getItem(name) !== null ? JSON.parse(localStorage.getItem(name)) : undefined;
      },
      /**
       * 是否可以载入数据
       * @returns {boolean}
       */
      isLoadData: function () {
        let bangStorage = this.getStorage('bangStorage');
        let currentTime = new Date().getTime(),
          count = 0,
          flag = true;
        if (bangStorage) {
          count = currentTime - bangStorage.time;
        }
        if (count > 0 && count < 24*60*60*1000 ) {
          flag = false;
        }
        return flag;

      }
    },


  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .index-container {
    color: whitesmoke;
  }
  .recommend-header {
    position: relative;
    width: 100%;
    height: 35px;
    line-height: 35px;
    border-bottom: 1px solid #45424f;
  }
</style>
