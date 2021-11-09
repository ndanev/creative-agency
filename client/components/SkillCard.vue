<template>
  <article class="skill-card">
    <div class="skill-card-inner">
      <div class="skill-card-inner-progress">
        <img :src="image" width="150" height="150" alt>
      </div>
    </div>
    <h3 class="skill-card-title mb-3">
      {{ title }}
    </h3>
    <div class="skill-card-content">
      {{ desc }}
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
    desc: {
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
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
      -ms-flex-direction: column;
          flex-direction: column;
  -webkit-box-pack: center;
      -ms-flex-pack: center;
          justify-content: center;
  -webkit-box-align: center;
      -ms-flex-align: center;
          align-items: center;
  margin-bottom: 3rem;
}

.skill-card-title {
  font-size: 1.2rem;
  font-weight: bold;
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
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-align: center;
      -ms-flex-align: center;
          align-items: center;
  -webkit-box-pack: center;
      -ms-flex-pack: center;
          justify-content: center;
  font-size: 3rem;
  color: #fff;
}

.skill-card-inner-progress img {
    width: 150px;
    height: 150px;
    border-radius: 50%;
    -webkit-transition: all .85s;
    -o-transition: all .85s;
    transition: all .85s;
}

.skill-card-inner-progress img:hover {
    -webkit-transform: rotateY(360deg);
            transform: rotateY(360deg);
}

.skill-card-content {
  font-size: .9rem;
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
