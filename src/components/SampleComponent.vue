<template>
  <button @click="count++">{{ count }}</button>
</template>

<script lang="ts">
import { onMounted, ref } from "vue";
import { Options, Vue } from "vue-class-component";

// onMounted(() => {
//   console.log("from out");
// })

// const count = ref(0);

// onMounted(() => {
//   console.log(count.value);
// })

@Options({})
export default class SampleComponent extends Vue {
  count = ref(0);
  // count = 0;

  mounted() {
    console.log("Hello world");
    console.log(this.count);
  }

  // onMounted(){
  //   console.log("Hello world dddd");
  // }
}
</script>
