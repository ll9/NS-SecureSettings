<template>
    <Page @loaded="loadPage">
        <ActionBar title="Welcome to NativeScript-Vue!"/>
        <StackLayout>
            <Label class="message" :text="msg"/>
            <Button @tap="setSecure" text="setSecure"/>
            <Button @tap="getSecure" text="getSecure"/>
        </StackLayout>
    </Page>
</template>

<script>
// require the plugin
const SecureStorage = require("nativescript-secure-storage").SecureStorage;

// instantiate the plugin
const secureStorage = new SecureStorage();

import Page2 from "./Page2";

export default {
  data() {
    return {
      msg: "Hello World!"
    };
  },
  methods: {
    loadPage() {
      this.$showModal(Page2, { cancelable: false });
    },
    setSecure() {
      secureStorage.setSync({
        key: "foo",
        value: "I was set at " + new Date()
      });
    },
    getSecure() {
      const success = secureStorage.getSync({
        key: "foo",
      });
      alert(success);
    }
  }
};
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
