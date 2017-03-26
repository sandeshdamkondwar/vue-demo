<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>Essential Links</h2>
    <ul>
      <li><a href="https://vuejs.org" target="_blank">Core Docs</a></li>
      <li><a href="https://forum.vuejs.org" target="_blank">Forum</a></li>
      <li><a href="https://gitter.im/vuejs/vue" target="_blank">Gitter Chat</a></li>
      <li><a href="https://twitter.com/vuejs" target="_blank">Twitter</a></li>
      <br>
      <li><a href="http://vuejs-templates.github.io/webpack/" target="_blank">Docs for This Template</a></li>
    </ul>
    <h2>Ecosystem</h2>
    <ul>
      <li v-for="link in ecosystemLinks">
        <a v-bind:href="link.url">{{link.title}}</a>
      </li>

    </ul>
  </div>
</template>

<script>
export default {
  name: 'hello',
  data () {
    return {
      msg: 'From new Component Hello2',
      ecosystemLinks: [
        {
          url: 'http://router.vuejs.org/',
          title: 'vue-router'
        },
        {
          url: 'http://vuex.vuejs.org/',
          title: 'vuex'
        },
        {
          url: 'http://vue-loader.vuejs.org/',
          title: 'vue-loader'
        },
        {
          url: 'https://github.com/vuejs/awesome-vue',
          title: 'awesome-vue'
        }
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
