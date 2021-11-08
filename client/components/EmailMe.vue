<template>
  <div class="email-me">
    <a class="d-block position-relative" href="mailto:nemanja.danev.93@gmail.com">
      <img src="@/assets/images/gmail.jpg" alt>
      <div class="email-me-text">
        Send me an email!
      </div>
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

.email-me a > img {
  transition: all .25s;
}

.email-me a:hover > img {
  transform: scale(.9);
}

.email-me a:hover > .email-me-text  {
  display: flex;
}

.email-me img {
  width: 50px;
  height: 40px;
}
.email-me-text {
  position: absolute;
  background-color: #fff;
  color: #2d1948;
  right: 100%;
  top: 50%;
  width: 150px;
  height: 35px;
  transform: translateY(-50%);
  display: none;
  align-items: center;
  justify-content: center;
  border-radius: 4px;
  transition: all .25s;
  box-shadow: 0px 4px 8px 0px rgb(0 0 0 / 20%);
  font-size: .8rem;
}

.email-me-text:hover {
  color: #C33C2C;
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
