<template>
  <div class="computed-properties-exercise container">
    <div class="row">
      <div class="col-12">
        <div class="border p-1">
          <div class="reverse-message">
            <p>Original Message: {{state.message}}</p>
            <p>Computed Reversed Message: {{state.reversedMessage}}</p>
          </div>
          <input v-model="state.message">
        </div>
      </div>
    </div>
  </div>
</template>


<script>
import { computed, reactive } from "vue";
export default {
  name: "computed-properties-exercise",
  setup() {
    const state = reactive
    ({
      // After getting this to work, challenge yourself to add an input field and bind message to it, so as you type the messag gets reversed!
      message: "",
      reversedMessage: computed(() => {
        let inMess = state.message
        let messArr = inMess.split("")
        let revMessArr = []
        messArr.forEach(m => revMessArr.splice(0,0,m))
        let revMess = revMessArr.join("")
         return revMess

        // all computed properties must return a value, what do you want this one to return?

      }),
    });
    return {
      state,
    };
  },
};
</script>


<style scoped>
</style>