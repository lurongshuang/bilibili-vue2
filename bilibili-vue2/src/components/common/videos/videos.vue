<template>
  <div id="videos" class="clearfix">
    <videoItem v-for="item in videoData" :key="item.ctime" :video-data="item"></videoItem>
  </div>
</template>

<script>
  import videoItem from '../videoItem/videoItem';

  export default {
    name: 'videos',
    props: {
      videosList: {
        type: Array,
        default: {message: []}
      }
    },
    components: {
      videoItem
    },
    computed: {
      videoData() {
        let arr = this.videosList.slice(-11, this.videosList.length);
        return arr;
      }
    },
    updated() {
      // console.log(this.videosList);
    }
  };
</script>

<style lang="stylus" scoped>
  @import '../../../common/stylus/base';

  #videos
    width 100%
    height 100%
</style>
