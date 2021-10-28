<template>
  <article class="work-card">
    <img :src="image" alt class="img-fluid">
    <div class="work-card-info">
      <h3 class="work-card-title mb-3">
        {{ title }}
      </h3>
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
  transition: all .25s;
}

.work-card:hover {
  transform: scale(1.02);
}

.work-card img {
  width: 100%;
  max-width: 100%;
  height: auto;
}

.work-card:hover > .work-card-info {
  display: flex;
  align-items: center;
  justify-content: center;
}

.work-card-info {
  background-color: rgba(27, 12, 48, .8);
  color: #fff;
  padding: 1rem;
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  width: 100%;
  height: 100%;
  display: none;
}
.work-card-title {
  font-weight: bold;
  font-size: 1.4rem;
}

@media (max-width: 767px) {
  .work-card {
    margin-bottom: 1rem;
  }
}
</style>
