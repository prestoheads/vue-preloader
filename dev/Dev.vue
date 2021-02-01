<template>
  <div id="app">
    <v-select />
  </div>
</template>

<script>
import vSelect from "../src/components/Select";
// import countries from "../docs/.vuepress/data/countryCodes";
// import books from "../docs/.vuepress/data/books";

export default {
  components: { vSelect },
  data: () => ({
    selected: null,
    config: {
      // options: countries
    }
  })
};
</script>