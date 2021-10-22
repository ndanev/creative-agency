<template>
  <article class="work-card">
    <img :src="image" alt>
    <div class="work-card-info">
      <div class="work-card-title">
        {{ title }}
      </div>
    </div>
  </article>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true
    },
    image: {
      type: String,
      required: true
    }
  }
}
</script>

<style>
.work-card {
  position: relative;
}

.work-card img {
  width: 100%;
}

.work-card-info {
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  background-color: rgba(0,0,0,.7);
  color: #fff;
  display: none;
  align-items: center;
  justify-content: center;
  transition: all .25s ease-in-out;
}

.work-card:hover > .work-card-info {
  display: flex;
}

@media (max-width: 767px) {
  .work-card {
    margin-bottom: 5px;
  }
}
</style>
