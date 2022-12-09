<template>
  <div>
    <Video :videoList="videos"/>
  </div>
  </template>
  <script>
  import Video from "@/components/Video.vue"
  export default {
    components: {
      Video
    },
  head: {
      title: "Home"
    },
      data() {
        return {
          videos: []
        }
      },
      async fetch() {
        this.videos = await fetch(
          '/video'
        ).then(res => res.json())
      }
  }
  </script>