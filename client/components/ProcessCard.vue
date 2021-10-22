<template>
  <article class="process-card">
    <div>
      <div class="process-card-title">
        {{ processTitle }} <i class="fas fa-long-arrow-alt-right" />
      </div>
      <div class="process-card-des">
        {{ processDesc }}
      </div>
    </div>
    <div class="process-card-icon">
      <!-- <i class="far fa-gem" /> -->
    </div>
  </article>
</template>

<script>
export default {
  props: {
    processTitle: {
      type: String,
      required: true
    },
    processDesc: {
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
