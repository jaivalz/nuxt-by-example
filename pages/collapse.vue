<template>
  <div>
    <div class="container my-5">
      <div class="row">
        <div class="col-lg-4">
          <b-card
            title="Tarjeta 1"
            img-src="https://picsum.photos/600/300/?image=25"
            img-alt="Image"
            img-top
            tag="article"
            style="max-width: 20rem;"
            class="mb-2"
          >
            <b-card-text>
              Some quick example text to build on the card title and make up the
              bulk of the card's content.
            </b-card-text>

            <h5 v-b-toggle.collapse-1 class="collapsable">Toggle Collapse</h5>
          </b-card>
        </div>
        <div class="col-lg-4">
          <b-card
            title="Tarjeta 2"
            img-src="https://picsum.photos/600/300/?image=25"
            img-alt="Image"
            img-top
            tag="article"
            style="max-width: 20rem;"
            class="mb-2"
          >
            <b-card-text>
              Some quick example text to build on the card title and make up the
              bulk of the card's content.
            </b-card-text>

            <h5 v-b-toggle.collapse-2 class="collapsable">Toggle Collapse</h5>
          </b-card>
        </div>
        <div class="col-lg-4">
          <b-card
            title="Tarjeta 3"
            img-src="https://picsum.photos/600/300/?image=25"
            img-alt="Image"
            img-top
            tag="article"
            style="max-width: 20rem;"
            class="mb-2"
          >
            <b-card-text>
              Some quick example text to build on the card title and make up the
              bulk of the card's content.
            </b-card-text>

            <h5 v-b-toggle.collapse-3 class="collapsable">Toggle Collapse</h5>
          </b-card>
        </div>
      </div>
      <b-collapse id="collapse-1" class="mt-2">
        <b-card>
          <p class="card-text">Collapse contents Here</p>
          <b-button v-b-toggle.collapse-1-inner size="sm"
            >Toggle Inner Collapse</b-button
          >
          <b-collapse id="collapse-1-inner" class="mt-2">
            <b-card>Hello!</b-card>
          </b-collapse>
        </b-card>
      </b-collapse>

      <b-collapse id="collapse-2" class="mt-2">
        <b-card>
          <p class="card-text">Collapse contents Here</p>
          <b-button v-b-toggle.collapse-1-inner size="sm"
            >Toggle Inner Collapse</b-button
          >
          <b-collapse id="collapse-1-inner" class="mt-2">
            <b-card>Hello!</b-card>
          </b-collapse>
        </b-card>
      </b-collapse>

      <b-collapse id="collapse-3" class="mt-2">
        <b-card>
          <p class="card-text">Collapse contents Here</p>
          <b-button v-b-toggle.collapse-1-inner size="sm"
            >Toggle Inner Collapse</b-button
          >
          <b-collapse id="collapse-1-inner" class="mt-2">
            <b-card>Hello!</b-card>
          </b-collapse>
        </b-card>
      </b-collapse>
    </div>
    <hr />
    <div class="container my-5">
      <div class="row">
        <div class="col-lg-4">
          <b-card
            title="Tarjeta 1"
            img-src="https://picsum.photos/600/300/?image=25"
            img-alt="Image"
            img-top
            tag="article"
            style="max-width: 20rem;"
            class="mb-2"
          >
            <b-card-text>
              Some quick example text to build on the card title and make up the
              bulk of the card's content.
            </b-card-text>

            <h5 v-b-toggle.accordion-1 class="collapsable">Toggle Collapse</h5>
          </b-card>
        </div>
        <div class="col-lg-4">
          <b-card
            title="Tarjeta 1"
            img-src="https://picsum.photos/600/300/?image=25"
            img-alt="Image"
            img-top
            tag="article"
            style="max-width: 20rem;"
            class="mb-2"
          >
            <b-card-text>
              Some quick example text to build on the card title and make up the
              bulk of the card's content.
            </b-card-text>

            <h5 v-b-toggle.accordion-2 class="collapsable">Toggle Collapse</h5>
          </b-card>
        </div>
        <div class="col-lg-4">
          <b-card
            title="Tarjeta 1"
            img-src="https://picsum.photos/600/300/?image=25"
            img-alt="Image"
            img-top
            tag="article"
            style="max-width: 20rem;"
            class="mb-2"
          >
            <b-card-text>
              Some quick example text to build on the card title and make up the
              bulk of the card's content.
            </b-card-text>

            <h5 v-b-toggle.accordion-3 class="collapsable">Toggle Collapse</h5>
          </b-card>
        </div>
      </div>
      <b-collapse id="accordion-1" accordion="my-accordion" role="tabpanel">
        <b-card-body>
          <b-card-text
            >I start opened because <code>visible</code> is
            <code>true</code></b-card-text
          >
          <b-card-text>{{ text.primero }}</b-card-text>
        </b-card-body>
      </b-collapse>
      <b-collapse id="accordion-2" accordion="my-accordion" role="tabpanel">
        <b-card-body>
          <b-card-text
            >I start opened because <code>visible</code> is
            <code>true</code></b-card-text
          >
          <b-card-text>{{ text.segundo }}</b-card-text>
        </b-card-body>
      </b-collapse>
      <b-collapse id="accordion-3" accordion="my-accordion" role="tabpanel">
        <b-card-body>
          <b-card-text
            >I start opened because <code>visible</code> is
            <code>true</code></b-card-text
          >
          <b-card-text>{{ text.tercero }}</b-card-text>
        </b-card-body>
      </b-collapse>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      text: {
        primero: 'Hola',
        segundo: 'He dicho hola',
        tercero: 'dime hola mamonaso'
      }
    }
  }
}
</script>

<style scoped>
.collapsable {
  cursor: pointer;
}
</style>
