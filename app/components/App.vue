<template>
    <Page @loaded="loadPage">
        <ActionBar title="Welcome to NativeScript-Vue!"/>
        <GridLayout columns="*" rows="*">
            <Label class="message" :text="msg" col="0" row="0"/>
        </GridLayout>
    </Page>
</template>

<script>
import Page2 from './Page2';

  export default {
    data() {
      return {
        msg: 'Hello World!'
      }
    },
    methods: {
        loadPage() {
            this.$showModal(Page2, {cancelable: false})
        }
    }
  }
</script>

<style scoped>
    ActionBar {
        background-color: #53ba82;
        color: #ffffff;
    }

    .message {
        vertical-align: center;
        text-align: center;
        font-size: 20;
        color: #333333;
    }
</style>
