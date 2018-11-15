<template>
  <div>{{ data }} <checkbox v-model="data.checkbox" /></div>
</template>

<script>
export default {
  data() {
    return {
      checkbox: false
    };
  }
};
</script>
