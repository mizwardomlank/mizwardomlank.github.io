<template lang='pug'>

  v-container.tab-wrapper.py-5
    v-layout(row wrap)

      v-flex.mb-5(xs12)
        v-layout

          v-flex.hidden-xs-only(sm1 md1 lg1 xl1)
            v-layout(fill-height align-center)
              v-divider.grey

          v-flex.text-sm-center(xs12 sm5 md4 lg3 xl3)
            .display-1(v-once) {{ title }}

          v-flex.hidden-xs-only(sm6 md7 lg8 xl8)
            v-layout(fill-height align-center)
              v-divider.grey


      v-flex(xs12)
        v-layout(row wrap)

          template(v-for='post in posts')
            card-post(v-if='post.type === "post"' :post='post')
            card-photo(v-if='post.type === "photo"' :post='post')
</template>



<script lang='coffee'>

import cardPost from './card--post.vue'
import cardPhoto from './card--photo.vue'

export default
  name: 'tab--featured'

  data: ->
    title: 'Featured posts'

    posts: [
        type: 'post'
        title: 'Buat jadi programmer harus jago matematika?'
        subtitle: 'Article'
        headIcon: 'web'
        href: 'https://develoka.com/article/buat-jadi-programmer-harus-jago-matematika'
        iconSource: 'https://develoka.com/uploads/images/83c882235beeec4becb49cb5de129d17_cover.jpg'
      ,
        type: 'post'
        title: 'Flip Card Game for iOS'
        subtitle: 'iOS App'
        headIcon: 'github-circle'
        href: 'https://github.com/mizwardomlank/ios-flipcard'
        iconSource: 'https://github.com/mizwardomlank/ios-flipcard/raw/master/img/screenshot.png'
    ]

  components:
    'card-post': cardPost
    'card-photo': cardPhoto

</script>



<style lang='sass'>

  .card
    padding: 5%
  
  .v-card
    padding: 10px

</style>
