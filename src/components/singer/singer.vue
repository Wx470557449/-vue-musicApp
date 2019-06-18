<template>
  <div class="singer"></div>
</template>
<script>
// import { getSingerList } from 'api/singer'
// import { ERR_OK } from 'api/config'
import jsonp from 'jsonp'

export default {
  data() {
    return {
      singers: []
    }
  },
  created() {
    this._getSingerList()
  },
  methods: {
    _getSingerList() {
      // getSingerList().then(res => {
      //   if (res.code === ERR_OK) {
      //     this.singers = res.data.list
      //     console.log(this.singers)
      //   }
      // })
      jsonp(
        'https://u.y.qq.com/cgi-bin/musicu.fcg?g_tk=5381&loginUin=0&hostUin=0&format=json&inCharset=utf8&outCharset=utf-8%C2%ACice=0&platform=yqq.json&needNewCode=0&data=%7B%22comm%22:%7B%22ct%22:24,%22cv%22:0%7D,%22singerList%22:%7B%22module%22:%22Music.SingerListServer%22,%22method%22:%22get_singer_list%22,%22param%22:%7B%22area%22:-100,%22sex%22:-100,%22genre%22:-100,%22index%22:-100,%22sin%22:0,%22cur_page%22:1%7D%7D%7D',
        '',
        (err, data) => {
          if (!err) {
            this.singers = data.singerList.data.singerlist
            console.log(this.singers)
          }
        }
      )
    }
  }
}
</script>
<style lang="stylus" scoped>
.singer
  position: fixed
  top: 88px
  bottom: 0
  width: 100%
</style>
