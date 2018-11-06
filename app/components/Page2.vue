<template>
    <Page @loaded="loadPage">
        <StackLayout>
            <Label class="message" :text="msg" col="0" row="0"/>
            <Button @tap="$modal.close" text="Close"></Button>
        </StackLayout>
    </Page>
</template>

<script>
  export default {
    data() {
      return {
        msg: 'Hello World!'
      }
    },
    methods: {
        loadPage(event) {
            event.object._dialogFragment.getDialog().setCanceledOnTouchOutside(false);
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
