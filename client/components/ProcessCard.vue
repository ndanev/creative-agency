<template>
  <article class="process-card">
    <div>
      <h3 class="process-card-title">
        {{ title }} <i class="fas fa-long-arrow-alt-right" />
      </h3>
      <div class="process-card-des">
        {{ desc }}
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
    desc: {
      type: String,
      required: true
    }
  }
}
</script>

<style>
.process-card {
    color: #fff;
    margin-bottom: 1rem;
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
}

.process-card-icon i {
    font-size: 1.6rem;
}

.process-card-title {
    font-weight: bold;
    font-size: 1.4rem;
    color: #f33c7a;
}

.process-card-title .fas {
    margin-left: 1rem;
    color: #fff;
}
</style>
