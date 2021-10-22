<template>
  <footer class="footer">
    <div class="container">
      <div class="row">
        <div class="col-md-6 d-flex align-items-center">
          <div class="copyrights mb-3 mb-md-0">
            &copy; {{ new Date().getFullYear() }}, powerd by Nemanja Danev
          </div>
        </div>
        <div class="col-md-6 d-flex justify-content-Center justify-content-md-end">
          <a href="https://github.com/ndanev?tab=repositories" target="_blank"><i class="fab fa-github-square" /></a>
          <a href="https://www.linkedin.com/in/nemanjadanev/" target="_blank"><i class="fab fa-linkedin" /></a>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
export default {}
</script>

<style>
.footer {
  background-color: #1b0c30;
  padding: 1rem 0;
}

.copyrights {
  color: #fff;
}

footer i {
  color: #fff;
  font-size: 2rem;
  margin-left: .5rem;
}
</style>
