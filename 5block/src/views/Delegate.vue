<template>
  <div class="Delegate">
    <label>Déléguer son vote</label>
    <input v-model="delegate" class="Delegate-input" />
    <button @click="delegateVote" class="Delegate-button">Déléguer son vote</button>
  </div>
</template>

<script>
"use strict";

export default {
  name: "Delegate",
  data() {
    return {
      delegate: ""
    };
  },
  methods: {
    delegateVote() {
      if (this.delegate === "") return;
      this.$store.dispatch("delegateVote", this.delegate).then(() => {
        this.delegate = "";
      });
    }
  }
};
</script>

<style lang="scss">
.Delegate {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
  margin-top: 1rem;
  &-input {
    width: 400px;
  }
  &-button {
    cursor: pointer;
    border: none;
    background-color: #0277bd;
    color: white;
    padding: 0.5rem;
    margin-top: 0.5rem;
    border-radius: 5px;
  }
}
</style>