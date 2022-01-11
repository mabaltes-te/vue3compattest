<template>
  <div class="hello">
    <TeLink disabled title="This is a disabled link title">This is a disabled link label</TeLink>
    <br/>
    <TeLink :on-click="onClickAlert">This is a onclick link label</TeLink>
    <br/>
    <TeLink href="https://www.thousandeyes.com" title="This is a normal link title">This is a normal link label</TeLink>
  </div>
</template>

<script>
import { TeLink } from '@te/ui-components';

console.log(TeLink);

export default {
  components: {
    TeLink
  },
  methods: {
    onClickAlert: () => alert('onClick link clicked')
  },
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
