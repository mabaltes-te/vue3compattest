<template>
  <div class="hello">
    <TeLink disabled title="This is a disabled link title">This is a disabled link label</TeLink>
    <br/>
    <TeLink :on-click="onClickAlert">This is a onclick link label</TeLink>
    <br/>
    <TeLink href="https://www.thousandeyes.com" title="This is a normal link title">This is a normal link label</TeLink>


    <TeButton
        ref="button0"
        :on-click="() => isOpenBasic = true"
        class="mb-3">
      Open Basic Modal
    </TeButton>
    <TeModal
        :is-open="isOpenBasic"
        :on-close="() => isOpenBasic = false"
        title="Some Title">
      <template v-slot:body>
        <div>
           This is a test
        </div>
      </template>
    </TeModal>

    <div class="tooltip-story">
      <div class="mb-3">
        <h4> Hover example </h4>
        <TeTooltip
            offset="10"
            popover-class="tetip"
            container=".tooltip-story"
            trigger="hover"
            placement="right">
          <span>Hover over me</span>
          <template v-slot:popover>
            TeTooltip example
          </template>
        </TeTooltip>
      </div>
      <div class="mb-3">
        <h4> Click example </h4>
        <TeTooltip
            offset="10"
            popover-class="tetip"
            container=".tooltip-story"
            placement="left">
          <span>Click on me</span>
          <template v-slot:popover>
            TeTooltip example
          </template>
        </TeTooltip>
      </div>
    </div>
  </div>
</template>

<script>
import { TeButton, TeLink, TeModal, TeTooltip } from '@te/ui-components';

export default {
  components: {
    TeLink,
    TeModal,
    TeTooltip,
    TeButton
  },
  data: () => ({
    isOpenBasic: false,
  }),
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
