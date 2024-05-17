<template>
  <Contact :username="input"/>
</template>

<script>
import Contact from './Contact.vue';
export default {
  components: {
    Contact
  },
  data() {
    return {
      input: process.env.NAME_BLOCK_INPUT || "Default Value"
    };
  }
}
</script>