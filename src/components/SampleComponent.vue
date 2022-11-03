<template>
  <button @click="count++">{{ count }}</button>
</template>

<script lang="ts">
import { defineComponent, onMounted, ref } from "vue";
import { Options, Vue } from "vue-class-component";

// // 1st way
export default defineComponent({
  name: "SampleComponent",
  mounted() {
    console.log("From legacy mounted()");
  },
  props: {
    msg: { type: String, required: false, default: "Sample Message!!!" },
  },
  setup(props) {
    const count = ref(0);
    onMounted(() => {
      console.log(props.msg);
    });

    return { count };
  },
});

// 2nd way
// export default {
//   name: 'Home',
//   mounted(){
//     console.log("From mounted");
//   },
//   props: {
//     msg: { type: String, required: false, default: 'Sample Message!!!' }
//   },
//   setup(props){
//     onMounted(() => {
//       console.log("From onMounted()");
//       console.log(props.msg);
//     })
//   }
// }

// defineComponent

// 3rd way ( use 'setup' attribute in script tag )
// onMounted(() => {
//   console.log("from out");
// })

// const count = ref(0);

// onMounted(() => {
//   console.log(count.value);
// })

// 4th way: class syntax
// @Options({})
// export default class SampleComponent extends Vue {
//   count = ref(0);
//   // count = 0;

//   mounted() {
//     console.log("Hello world");
//     console.log(this.count);
//   }

//   // onMounted(){
//   //   console.log("Hello world dddd");
//   // }
// }
</script>
