<template>
  <div class="hello">
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data(){
    return {

    }
  },
  methods:{
    go(){
      this.$router.push('/test1')
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->