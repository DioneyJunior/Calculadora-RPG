<template>
  
  <header>
    <nav class="navbar navbar-expand-lg p-0" id="navbar">
      <div>
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
  </header>
  <br />
            </label>
            
            <input type="radio" v-model="selectedDice" value="d8" id="d8"/>
            <label for="d8">
              d8 <img src="./components/img/d8.png" class="img d-block" id="d8img"
              />
            </label>
            
            <input type="radio" v-model="selectedDice" value="d10" id="d10" />
            <label for="d10">
              d10 <img src="./components/img/d10.png" class="img d-block" id="d10img"
              />
            </label>
            
            <input type="radio" v-model="selectedDice" value="d12" id="d12"/>
            <label for="d12">
              d12<img src="./components/img/d12.png" class="img d-block" id="d12img"
              />
            </label>
            
            <input type="radio" v-model="selectedDice" value="d20"  id="d20"/>
            <label for="d20">
              d20<img src="./components/img/d20.png" class="img d-block" id="d20img"
              />
            </label>
            
            <input type="radio" v-model="selectedDice" value="d100" id="d100" />
            <label for="d100">
              d100<img src="./components/img/d100.png" class="img d-block" id="d100img"
              />
            </label>
          </form>
        </div>
      </div>
    </div>
  </div>
  <br />
  <div class="container justify-content-center d-flex">
    <button class="btn btn-primary" @click.prevent="rollDice">Rolar Dado</button>
  </div>
  <br />
  <div id="result-box" class="container text-center">
    <button
    type="button"
    class="btn btn-secondary btn-lg"
    data-bs-container="body"
    data-bs-toggle="popover"
    data-bs-placement="top"
    data-bs-content="Zero"
    id="output"
    >
    {{ result }}
  </button>
</div>

  <Style>
    nav { position: fixed; bottom: 0; width: 100%; background-color: #484747; border-bottom: 5px
    solid #000000; } @media (max-width: 768px) { .navbar #btn-ficha { display: none; } } 
</template>
<script>
import CharacterInputs from "./components/CharacterInputs.vue";
export default {
  data() {
    return {
      selectedDice: "d10",
      result: null
    };
  },
  name: "App",
  components: {
    CharacterInputs, 
  },
  methods: {
    rollDice() {
      const random = (min, max) => Math.floor(Math.random() * (max - min + 1) + min);
      switch (this.selectedDice) {
        case "d4":
          this.result = random(1, 4);
          break;

        case "d6":
          this.result = random(1, 6);
          break;

        case "d8":
          this.result = random(1, 8);
          break;

        case "d10":
          this.result = random(1, 10);
          break;

        case "d12":
          this.result = random(1, 12);
          break;

        case "d20":
          this.result = random(1, 20);
          break;

        case "d100":
          this.result = random(1, 100);
          break;

        default:
          break;
      }
    }
  }
  }
};
</script>
