<template>
  <div class="footer">
    <div class="columns container">
      <div class="column">
        <p>Gracias por utilizar nuestra plataforma!</p>
      </div>
    <div class="column has-text-right">
      <p>Ecommerce | Hecho con ❤ para <b> <a href="https://www.linkedin.com/in/johanna-avila7391/"  style="color: #FF33FF">Johanna Avila </a></b></p>
    </div>
      <div class="navbar-item social">
            <a href="#" class="icon" :title="facebookTooltip">
              <i class="fa fa-facebook"></i>
            </a>
            <a href="#" class="icon" :title="twitterTooltip">
              <i class="fa fa-twitter"></i>
            </a>
            <a href="#" class="icon" :title="instagramTooltip">
              <i class="fa fa-instagram"></i>
            </a>
            <a href="#" class="icon" :title="linkedinTooltip">
              <i class="fa fa-linkedin"></i>
            </a>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'VmFooter',
}
</script>

<style lang="scss" scoped>
 .footer {
   background: #b9e2fc;
   color: black;
 }
</style>
