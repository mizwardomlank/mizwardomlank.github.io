<template lang='pug'>

#mega-header.grey.darken-4
  .cover-background
    v-img(src='public/header-cover.jpg' lazy-src='public/header-cover.jpg' width='100%' height='100%')
      v-layout(slot='placeholder' fill-height align-end justify-end)
        v-progress-circular.ma-4(indeterminate size='50' color='grey lighten-5')

  v-container.header-content(fill-height)
    v-layout(row wrap justify-center align-space-between)

      v-flex(xs12)
        v-layout(justify-center)

          v-flex(xs11 sm6 md5 lg4 xl3)
            v-layout(justify-space-between align-center)

              v-icon.hidden-xs-only.mt-3(color='grey lighten-2') mdi-minus

              template(v-for='button in buttons' v-once)
                v-btn.button.mx-0.mt-3(dark icon outline target='_blank' color='grey' :href='button.href' v-bind="{[`${button.size}`]: true}")
                  v-icon(color='#294a77' :small="button.size === 'small'") mdi-{{ button.icon }}

              v-icon.hidden-xs-only.mt-3(color='grey lighten-2') mdi-minus


      v-flex(xs12)
        v-layout(fill-height justify-center align-center)
          <center>
          <h1 style="color:#294a77; font-size:36px;"> Hi! <strong>I'm Miftah</strong></h1>
          </center>

      v-flex(xs12)
        v-layout(fill-height justify-center align-end)

          v-btn#btn(dark icon large @click='scrollDown').mb-3
            v-icon(large color='#294a77') mdi-chevron-down
</template>



<script lang='coffee'>

export default
  name: 'page-header'

  data: ->
    buttons: [
        size: 'small'
        icon: 'web'
        href: 'https://develoka.com/user/mizwardomlank'
      ,
        size: 'medium'
        icon: 'instagram'
        href: 'https://instagram.com/mvthm'
      ,
        size: 'large'
        icon: 'github-circle'
        href: 'https://github.com/mizwardomlank'
      ,
        size: 'medium'
        icon: 'twitter-circle'
        href: 'https://twitter.com/mvthm'
      ,
        size: 'small'
        icon: 'at'
        href: 'mailto:miftahmizwar@gmail.com'
    ]

  methods:
    scrollDown: ->
      @$vuetify.goTo '#toolbar',
        duration: 1000

</script>



<style lang='sass'>

#mega-header
  width: 100%
  height: 100vh

  .header-content
    position: relative
    top: -100vh

  .cover-background
    width: 100%
    height: 100vh

</style>
