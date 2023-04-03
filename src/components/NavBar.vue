<template>
<nav class="navbar navbar-expand-lg bg-body-tertiary w-100">
      <div class="container-fluid">
        <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="offcanvas"
          data-bs-target="#offcanvas"
          aria-controls="offcanvas"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
          <div class="navbar-nav">
            <button
              class="btn btn-primary"
              type="button"
              data-bs-toggle="offcanvas"
              data-bs-target="#offcanvas"
              aria-controls="offcanvas"
              id="btn-ficha"
            >
              <i class="bi bi-person-fill"></i>
              Ficha de Personagem
            </button>
          </div>
        </div>
      </div>
    </nav>
    <CharacterInputs />
</template>
<style scoped>
nav{
    background-color:#1f74be
}
</style>
<script>
import CharacterInputs from './CharacterInputs.vue';
export default {
    name: 'NavBar',
    components: { CharacterInputs },
      }
</script>
