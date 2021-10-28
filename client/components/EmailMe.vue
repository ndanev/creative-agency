<template>
  <div class="email-me">
    <a class="d-block" href="mailto:nemanja.danev.93@gmail.com">
      <img src="@/assets/images/gmail.jpg" alt>
    </a>
  </div>
</template>

<script>
export default {}
</script>

<style>
.email-me {
    position: fixed;
    bottom: 50px;
    right: 50px;
    z-index: 10;
    width: 75px;
    height: 75px;
    background-color: #fff;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    border: 4px solid #fff;
    transition: all .25s ease-in-out;
    box-shadow: 0px 4px 8px 0px rgb(0 0 0 / 20%);
}

.email-me:hover, .email-me:focus, .email-me:active {
  border: 4px solid #C33C2C;
}

.email-me img {
  width: 50px;
  height: 40px;
}

@media (max-width: 767px) {
  .email-me {
    bottom: 30px;
    right: 30px;
    width: 50px;
    height: 50px;
  }

  .email-me img {
    width: 30px;
    height: 20px;
  }
}
</style>
