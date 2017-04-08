<template lang='pug'>
#MainSlide.frontpage
  .eg-slideshow
    slide
      .content
        h1
          span.logo
          span Climate
          span.grey Changes
        h2 "Earth provides enought to satisfy every man's needs, <br> but not every man's greet"
        h3 Mahatma Gandhi
</template>

<script>
import slideshows from 'slideshows/slideshows'
import eagle from 'eagle.js'

export default {
  mixins: [ eagle.slideshow ],
  data: function () {
    return {
      slideshows: slideshows.list
    }
  },
  mounted: function () {
    console.log(this.slideshows)
    document.currentSlide = {}
  },
  components: {
    'temperature': require('./slideshows/Temperature')
  },
  methods: {
    click: function (evt) {
      evt.stopPropagation()
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang='scss' scoped>
#MainSlide .content {
  width: 950px;
}

@import "node_modules/eagle.js/src/themes/frontpage/frontpage";
.logo {
  display: inline-block;
  width: 240px;
  height:240px;
  margin-right: 0;
  background-image: url(./logo.svg);
  background-size: contain;
  background-position: center bottom;
  background-repeat: no-repeat;
}
h2 {
  margin-bottom: 0;
}
h3 {
  text-align: center;
}
</style>
