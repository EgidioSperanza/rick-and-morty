<template>
  <div class="card-box">
    <img :src="personage.image" :alt="personage.name" />
    <h1>{{ personage.name }}</h1>
    <h3>
      Species: <span>{{ personage.species }}</span>
    </h3>
    <h3>
      Gender: <span>{{ personage.gender }}</span>
    </h3>
    <h3>
      Origin: <span>{{ personage.origin }}</span>
    </h3>
    <p
      class="status"
      :class="personage.status === 'Alive' ? 'status-alive' : 'status-dead'"
    >
      {{
        personage.status === "Alive"
          ? `${personage.name} is Alive`
          : `${personage.name} is Dead`
      }}
    </p>
  </div>
</template>

<script>
export default {
  props: {
    personage: Object,
  },
};
</script>

<style scoped lang="scss">
.card-box {
  padding: 20px;
  width: 300px;
  border: 1px solid #000;
  border-radius: 20px;
  min-height: 500px;
  margin-bottom: 20px;
  position: relative;
  background-color: #333;
  color: #fff;

  img {
    border-radius: 100%;
    width: 250px;
    border: 3px solid goldenrod;
  }
  h1 {
    text-align: center;
    margin-bottom: 10px;
  }
  h3 {
    span {
      font-weight: 400;
    }
  }
  .status {
    width: 200px;
    margin-top: 20px;
    padding: 10px;
    border: 1px solid black;
    text-align: center;
    position: absolute;
    bottom: 5px;
    left: 50%;
    transform: translate(-50%, 0);
  }
  .status-alive {
    background-color: green;
  }
  .status-dead {
    background-color: black;
  }
}
</style>
