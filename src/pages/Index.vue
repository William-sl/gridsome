<template>
  <Layout>

    <!-- Learn how to use images here: https://gridsome.org/docs/images -->
    <!-- <g-image alt="Example image" src="~/favicon.png" width="135" /> -->

   <div>
     <h1 style="text-align:center">Simplicity. Aesthetics. Value.</h1>
     <h2 style="text-align:center; margin:0 50px">Hi there, I'm an independent Digital Designer & Art Director focused on digital design for brands that like to have fun.</h2>
   </div>
   <div style="position:relative">
     <div v-for="post in this.$page.posts.edges" :key="post.node.id">
       <g-image alt="Example image" class="img" :src="`${GRIDSOME_API_URL+post.node.img.url}`" width="135" />
       <h3 style="text-align: center;">{{post.node.title}}</h3>
       <div class="content">{{post.node.content}}</div>
       <!-- <div style="text-align: center;">
          {{item.node.content}}
       </div> -->
     </div>
   </div>
  </Layout>
</template>

<page-query>
query{
  posts:allStrapiPost{
    edges{
      node{
        id,
        title,
        content,
        img {
          url
        }
      }
    }
  }
}
</page-query>

<script>
export default {
  metaInfo: {
    title: 'Hello, world!'
  },
}
</script>

<style>
.home-links a {
  margin-right: 1rem;
}
.img{
      width: 450px;
    margin: auto;
    display: block;
}
.content{
  text-align: center;
    display: block;
    margin-bottom: 10px;
}
</style>
