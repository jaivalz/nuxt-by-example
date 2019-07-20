<template>
  <div>
    <div class="container mt-5">
      <b-card
        img-src="https://placekitten.com/1000/300"
        img-alt="Card image"
        img-top
      >
        <b-card-text>
          Some quick example text to build on the card and make up the bulk of
          the card's content.
        </b-card-text>
      </b-card>
    </div>
    <br />
    <hr />
    <div class="card col-lg-3 mx-5">
      <div class="container">
        <nuxt-link to="/hola">
          <img
            class="card-img-top"
            src="https://placekitten.com/1000/300"
            alt="Card image cap"
            width="350px"
            height="150px"
          />
        </nuxt-link>
        <div class="bottom-right">
          <a href="//www.google.es">Bottom Right</a>
        </div>
      </div>
      <div class="container">
        <n-link to="/hola">
          <img
            class="card-img-top"
            src="https://placekitten.com/1000/300"
            alt="Card image cap"
            width="285px"
            height="150px"
          />
        </n-link>
        <div class="top-right">Top Right</div>
      </div>
      <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <p class="card-text">
          Some quick example text to build on the card title and make up the
          bulk of the card's content.
        </p>
        <a href="#" class="btn btn-primary">Go somewhere</a>
      </div>
    </div>
    <!-- https://www.w3schools.com/howto/howto_css_image_text.asp -->
    <br />
  </div>
</template>

<script>
export default {}
</script>

<style scoped>
.container {
  position: relative;
  text-align: center;
  color: white;
}

/* Bottom left text */
.bottom-left {
  position: absolute;
  bottom: 8px;
  left: 16px;
}

/* Top left text */
.top-left {
  position: absolute;
  top: 8px;
  left: 16px;
}

/* Top right text */
.top-right {
  position: absolute;
  top: 8px;
  right: 16px;
  cursor: default;
}

/* Bottom right text */
.bottom-right {
  position: absolute;
  bottom: 8px;
  right: 16px;
  cursor: default;
}

a {
  color: inherit;
  text-decoration: none;
}

/* Centered text */
.centered {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
</style>
