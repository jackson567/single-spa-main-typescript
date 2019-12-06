<template>
  <div class="about">
    <h1>This is an about page by APP1</h1>
    <div>jlw:{{jlw}}</div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      jlw: 1
    };
  },
  methods: {
    change_jlw() {
      this.jlw++;
    }
  },
  mounted() {
    
    window.abouttest = this;
  }
};
</script>