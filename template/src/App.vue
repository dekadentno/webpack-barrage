<template>
  <div id="app">
    <img src="./assets/logo.png">
    {{#router}}
    <router-view/>
    {{else}}
    <HelloWorld/>
    {{/router}}
  </div>
</template>

<script>
  {{#unless router}}
  import HelloWorld from './components/HelloWorld'{{#if_eq lintConfig "barrage"}};{{/if_eq}}

    {{/unless}}
  export default {
    name: 'App'{{#router}}{{#if_eq lintConfig "barrage"}}{{/if_eq}}{{else}},
        components: {
          HelloWorld{{#if_eq lintConfig "barrage"}},{{/if_eq}}
        }{{#if_eq lintConfig "barrage"}},{{/if_eq}}{{/router}}
  }{{#if_eq lintConfig "barrage"}};{{/if_eq}}
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
