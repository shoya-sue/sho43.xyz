<template>
    <div>
      <component :is="isMobile ? 'HeaderSp' : 'HeaderPc'" />
      <slot />
      <component :is="isMobile ? 'FooterSp' : 'FooterPc'" />
    </div>
  </template>
  
  <script>
  import HeaderPc from './header-pc.vue';
  import HeaderSp from './header-sp.vue';
  import FooterPc from './footer-pc.vue';
  import FooterSp from './footer-sp.vue';
  
  export default {
    components: {
      HeaderPc,
      HeaderSp,
      FooterPc,
      FooterSp,
    },
    computed: {
      isMobile() {
        return window.innerWidth <= 768;
      }
    },
  };
  </script>
  