<template>
  <Contact username="input"/>
</template>

<script>
import Contact from './Contact.vue';
export default {
  name: NameBlock,
  components: {
    Contact
  },
  data() {
    return {
      input: process.env.NAME_BLOCK_INPUT
    };
  }
}
</script>