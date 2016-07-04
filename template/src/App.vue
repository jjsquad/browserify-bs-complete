<template>
    <div id="app">
        <nav class="nav">
            <div class="nav-left">
                PROJECTNAME
            </div>
            <span class="nav-item">
                <a v-link="{ path: '/' }" class="button is-primary">
                    <span class="icon">
                    <i class="fa fa-home"></i>
                    </span>
                    <span>Main Content</span>
                </a>
                <a v-link="{ path: '/resourceExample' }" class="button is-primary">
                    <span class="icon">
                    <i class="fa fa-link"></i>
                    </span>
                    <span>Resource example</span>
                </a>
                <a v-link="{ path: '/vuexExample' }" class="button is-primary">
                    <span class="icon">
                    <i class="fa fa-bolt"></i>
                    </span>
                    <span>Vuex example</span>
                </a>
            </span>
        </nav>
        <div class="container">
            <router-view></router-view>
        </div>
    </div>
</template>
<script>
import store from './vuex/store'

export default {
  data () {
    return {
      msg: 'Hello Vue!'
    }
  },
  store
}
</script>

<style>
    body {
        font-family: Helvetica, sans-serif;
    }
</style>