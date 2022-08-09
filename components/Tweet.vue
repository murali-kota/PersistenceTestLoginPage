<template>
  <div v-html="oembedHtml">
    <!--
    <blockquote class="twitter-tweet" data-lang="en">
      <p lang="en" dir="ltr">just setting up my twttr</p>&mdash; Jack (@jack) <a href="https://twitter.com/jack/status/20">March 21, 2006</a>
    </blockquote>
     -->
  </div>
</template>

<script>
// https://publish.twitter.com/oembed?url=https://twitter.com/jack/status/20&omit_script=1
//<a class="twitter-timeline" href="https://twitter.com/Tracy_Planning?ref_src=twsrc%5Etfw">Tweets by Tracy_Planning</a> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>


export default {
  head: {
    script: [
      { hid: 'twitter', type: 'text/javascript', src: '//platform.twitter.com/widgets.js', async: true, defer: true }
    ]
  },
  props: ['oembedHtml', 'tweetId'],
  mounted() {
    if (this.tweetId)
        twttr.widgets.createTweet(this.tweetId, this.$el)
    else
        true//twttr.widgets.load(this.$el)
  }
}
</script>