<template>
  <div>
    <div :class="{ active: !active }" class="loader">
      <div class="loader__inner">
        <div class="case loader__wrap">
          <div class="loader__picture">
           LOADER
          </div>
          <p class="loader__text">
            Подождите, <br />
            идёт загрузка...
          </p>
        </div>
      </div>
    </div>
    <template v-if="images != null">
      <img
          v-for="(img, index) in images"
          :key="`image-${index}`"
          class="loader__hide"
          :src="img"
      />
    </template>
  </div>
</template>

<script type="text/babel">
  // import pointerScroll from '../mixins/pointerScroll'
  // import typeAheadPointer from '../mixins/typeAheadPointer'
  // import ajax from '../mixins/ajax'
  // import childComponents from './childComponents';
  // import appendToBody from '../directives/appendToBody';
  // import sortAndStringify from '../utility/sortAndStringify'
  // import uniqueId from '../utility/uniqueId';

  /**
   * @name VueSelect
   */
  export default {

    data() {
      return {
        active: true,
      };
    },
    props: {
      images: { type: Array, default: null },
    },

    mounted() {
      document.onreadystatechange = () => {
        if (document.readyState == 'complete') {
          this.$nextTick(() => {
            this.active = false;
          }, 1000);
        }
      };
    },
  }
</script>
