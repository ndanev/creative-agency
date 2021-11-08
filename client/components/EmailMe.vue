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
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-align: center;
        -ms-flex-align: center;
            align-items: center;
    -webkit-box-pack: center;
        -ms-flex-pack: center;
            justify-content: center;
    border: 4px solid #fff;
    -webkit-transition: all .25s ease-in-out;
    -o-transition: all .25s ease-in-out;
    transition: all .25s ease-in-out;
    -webkit-box-shadow: 0px 4px 8px 0px rgb(0 0 0 / 20%);
            box-shadow: 0px 4px 8px 0px rgb(0 0 0 / 20%);
}

.email-me a > img {
  -webkit-transition: all .25s;
  -o-transition: all .25s;
  transition: all .25s;
}

.email-me a:hover > img {
  -webkit-transform: scale(.9);
      -ms-transform: scale(.9);
          transform: scale(.9);
}

.email-me a:hover > .email-me-text  {
  display: -webkit-box;
  display: -ms-flexbox;
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
  -webkit-transform: translateY(-50%);
      -ms-transform: translateY(-50%);
          transform: translateY(-50%);
  display: none;
  -webkit-box-align: center;
      -ms-flex-align: center;
          align-items: center;
  -webkit-box-pack: center;
      -ms-flex-pack: center;
          justify-content: center;
  border-radius: 4px;
  -webkit-transition: all .25s;
  -o-transition: all .25s;
  transition: all .25s;
  -webkit-box-shadow: 0px 4px 8px 0px rgb(0 0 0 / 20%);
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
