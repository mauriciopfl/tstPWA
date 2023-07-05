<template>
  <div></div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
export default defineComponent({
  setup() {},
  components: {},
  props: {},
  created() {
    window.addEventListener("beforeinstallprompt", (e) => {
      e.preventDefault();
      // Stash the event so it can be triggered later.
      this.deferredPrompt = e;
    });
  },
  mounted() {},
  data() {
    return {
      deferredPrompt: null,
    };
  },
  watch: {},
  computed: {},
  methods: {
    async install() {
      this.deferredPrompt.prompt();
    },
  },
});
</script>

<style lang="scss" scoped></style>
