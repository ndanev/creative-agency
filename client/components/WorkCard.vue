<template>
  <article class="work-card">
    <img :src="image" alt>
    <div class="work-card-info">
      <div class="work-card-title mb-3">
        {{ title }}
      </div>
      <div class="work-card-link">
        <a :href="link" target="_blank">Github link</a>
        <a v-if="website !== ''" :href="website" target="_blank">Website</a>
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
    },
    link: {
      type: String,
      required: true
    },
    website: {
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
}

.work-card-title {
  font-weight: bold;
}

.work-card:hover > .work-card-info {
  display: flex;
  flex-direction: column;
}

.work-card-link {
  display: flex;
}

.work-card-link a {
  display: block;
  color: #fff;
  background-color: #f33c7a;
  border: 1px solid #fff;
  padding: 10px;
  margin-bottom: 1rem;
}

@media (max-width: 767px) {
  .work-card {
    margin-bottom: 5px;
  }
}
</style>
