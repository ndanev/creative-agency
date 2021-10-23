<template>
  <article class="skill-card">
    <div class="skill-card-inner">
      <div class="skill-card-inner-progress">
        <img :src="image" alt>
      </div>
    </div>
    {{ title }}
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
.skill-card {
  text-align: center;
  color: #fff;
  font-size: 1.2rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin-bottom: 3rem;
}

.skill-card-inner {
  width: 175px;
  height: 175px;
  border-radius: 50%;
  margin-bottom: 1rem;
  background: #2d1948;
}

.skill-card-inner-progress {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  border: 5px solid #fff;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 3rem;
  color: #fff;
}

.skill-card-inner-progress img {
    width: 150px;
    height: 150px;
    border-radius: 50%;
    transition: all .85s;
}

.skill-card-inner-progress img:hover {
    transform: rotateY(360deg);
}

@media (max-width: 767px) {
    .skill-card-inner {
        width: 100px;
        height: 100px;
    }

    .skill-card {
        margin-bottom: 1.4rem;
    }

    .skill-card-inner-progress {
        border: 0;
    }

    .skill-card-inner-progress img {
        width: 100%;
        height: 100%;
    }
}
</style>
