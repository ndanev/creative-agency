<template>
  <div class="header-top">
    <div class="container-fluid">
      <div class="d-flex align-items-center justify-content-between">
        <h1>
          Web Design & <span>Development</span>
        </h1>
        <div>
          <i class="fas fa-phone-alt" />
          <a href="tel:4373283418">
            (437) 328-3418
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style>
.header-top {
    padding: 0 1rem;
    background-color: rgba(27, 12, 48, 1);
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 30px;
    z-index: 3;
    display: flex;
    align-items: center;
    justify-content: space-between;
}

.header-top h1 span {
    color: #f33c7a;
}

.header-top h1 {
    font-size: 1rem;
    margin-bottom: 0;
    font-weight: bold;
    color: #fff;
}

.header-top i {
    color: #fff;
}

.header-top a {
    color: #fff;
    font-weight: bold;
}

@media (max-width: 450px) {
  .header-top a {
    font-size: .7rem;
  }

  .header-top i {
    font-size: .7rem;
  }

  .header-top h1 {
    font-size: .7rem;
  }
}
</style>
