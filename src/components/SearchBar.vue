<template>
  <div>
    <div class="filter">
      <input
        type="text"
        placeholder="Search by Name"
        v-model="keywordSearch"
        @keyup.enter="$emit('search', keywordSearch.toLowerCase())"
      />
      <button @click="$emit('search', keywordSearch.toLowerCase())">
        Search
      </button>
      <button @click="reset()">Reset</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      keywordSearch: '',
    }
  },
  methods: {
    reset() {
      this.$emit('reset')
      this.keywordSearch = ''
    },
  },
}
</script>
<style lang="scss" scoped>
.filter {
  display: flex;
  padding-top: 20px;

  input {
    width: 80%;
    height: 50px;
    line-height: 50px;
    padding-left: 20px;
  }
  button {
    width: calc(10% - 20px);
    margin-left: 20px;
    background-color: #333;
    color: #fff;
    border-radius: 10px;
  }
}
</style>
