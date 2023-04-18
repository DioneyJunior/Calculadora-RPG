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
  <div id="content-wrapper" class="row p-0 m-0 align-items-center justify-content-center">
    <div class="col-12 py-3">
      <div class="row p-0 m-0">
        <!-- dados -->
        <div class="col-12 text-center">
          <form>
            <input type="radio" v-model="selectedDice" value="d4" id="d4" />
            <label for="d4">
              d4
              <img v-if="selectedDice !== 'd4'" src="/img/d4.png" class="img d-block" />
              <img v-if="selectedDice === 'd4'" src="/img/d4_check.png" class="img d-block" />
              <img src="/img/d4_check.png" class="img d-none" />
            </label>

            <input type="radio" v-model="selectedDice" value="d6" id="d6" />
            <label for="d6">
              d6
              <img v-if="selectedDice !== 'd6'" src="/img/d6.png" class="img d-block" />
              <img v-if="selectedDice === 'd6'" src="/img/d6_check.png" class="img d-block" />
              <img src="/img/d6_check.png" class="img d-none" /><!-- Preload dice img -->
            </label>

            <input type="radio" v-model="selectedDice" value="d8" id="d8" />
            <label for="d8">
              d8
              <img v-if="selectedDice !== 'd8'" src="/img/d8.png" class="img d-block" />
              <img v-if="selectedDice === 'd8'" src="/img/d8_check.png" class="img d-block" />
              <img src="/img/d8_check.png" class="img d-none" /><!-- Preload dice img -->
            </label>

            <input type="radio" v-model="selectedDice" value="d10" id="d10" />
            <label for="d10">
              d10
              <img v-if="selectedDice !== 'd10'" src="/img/d10.png" class="img d-block" />
              <img v-if="selectedDice === 'd10'" src="/img/d10_check.png" class="img d-block" />
              <img src="/img/d10_check.png" class="img d-none" /><!-- Preload dice img -->
            </label>

            <input type="radio" v-model="selectedDice" value="d12" id="d12" />
            <label for="d12">
              d12
              <img v-if="selectedDice !== 'd12'" src="/img/d12.png" class="img d-block" />
              <img v-if="selectedDice === 'd12'" src="/img/d12_check.png" class="img d-block" />
              <img src="/img/d12_check.png" class="img d-none" /><!-- Preload dice img -->
            </label>

            <input type="radio" v-model="selectedDice" value="d20" id="d20" />
            <label for="d20">
              d20
              <img v-if="selectedDice !== 'd20'" src="/img/d20.png" class="img d-block" />
              <img v-if="selectedDice === 'd20'" src="/img/d20_check.png" class="img d-block" />
              <img src="/img/d20_check.png" class="img d-none" /><!-- Preload dice img -->
            </label>

            <input type="radio" v-model="selectedDice" value="d100" id="d100" />
            <label for="d100">
              d100
              <img v-if="selectedDice !== 'd100'" src="/img/d100.png" class="img d-block" />
              <img v-if="selectedDice === 'd100'" src="/img/d100_check.png" class="img d-block" />
              <img src="/img/d100_check.png" class="img d-none" /><!-- Preload dice img -->
            </label>
          </form>
        </div>
      </div>
    </div>
    <div class="row m-0 justify-content-center mb-3">
      <div class="col-8 col-md-6 col-lg-4 col-xl-3">
        <select class="form-select" v-model="selectedAttribute">
          <option value="padrão">Sem atributo-chave</option>

          <option value="str">Força</option>

          <option value="cons">Constituição</option>

          <option value="dex">Destreza</option>

          <option value="int">Inteligência</option>

          <option value="wis">Sabedoria</option>

          <option value="char">Carisma</option>
        </select>
      </div>
    </div>
    <!-- proficiencia checkbox -->
    <div class="container text-center">
      <form id="prof">
        <input
          v-model="proficiencyCheckbox"
          class="form-check-input"
          type="checkbox"
          id="proftrue"
        />
        <label class="form-check-label" for="proftrue">Adicionar proficiência</label>
      </form>
      <br />
      <!-- Botão rolar dado -->
      <button type="button" class="btn btn-primary" id="btnRoll" @click="btnRollClick()">
        Rolar dado
      </button>
    </div>
    <br />
    <!-- resultado -->
    <div id="result-box" class="container text-center">
      <button
        v-show="showResult"
        @click="isOpen = !isOpen"
        type="button"
        class="btn btn-secondary btn-lg"
        id="btnResult"
      >
        {{ result }}
      </button>
      <div class="align align-content-center">
        <p v-show="isOpen" id="outputText" class="text-white">
          {{ outputText }}
        </p>
      </div>
    </div>
    <br />
    <br />
    <!-- Rodapé -->
    <footer class="mt-auto">
      <div class="container-fluid">
        <div class="row p-0 m-0">
          <div class="col-12 p-0 m-0 py-2">
            <p>Acerto Crítico &copy; 2023</p>
          </div>
        </div>
      </div>
    </footer>
  </div>
  <Style>
    nav { position: fixed; bottom: 0; width: 100%; background-color: #484747; border-bottom: 5px
    solid #000000; } @media (max-width: 768px) { .navbar #btn-ficha { display: none; } } body {
    background-color: #9f9a9a; } .img d-block { margin: 20%; } #content-wrapper { flex: 1 0 auto; }
    #btnRoll { margin-bottom: 2.7%; } /* input */ .img { border: 50%; padding: 2px; } label img {
    cursor: pointer; display: block; } input[type="radio"] { display: none; margin: 10px; }
    input[type="radio"] label { display: flex; align-items: center; justify-content: center; }
    input[type="radio"]:checked+label { color: #ffffff; } @media (max-width: 1080px) { img { height:
    100%; max-height: 100px; } } @media (max-width: 2160px) { img { height: 100%; max-height: 200px;
    } } /* icones */ .icon { display: inline; width: 24px; height: 24px; } /* footer */ footer {
    color: #ccc; text-align: center; bottom: 0; width: 100%; background: #484747; border-top: 5px
    solid #000000; } #outputText { margin-bottom: 2%; margin-top:0.2% } #btnResult { margin-bottom:
    1.75%; }
  </Style>
</template>

<script>
import CharacterInputs from "./components/CharacterInputs.vue";
export default {
  data() {
    return {
      selectedDice: "d10",
      result: null,
      outputText: "",
      selectedAttribute: null,
      proficiencyCheckbox: null,
      isOpen: false,
      showResult: false
    };
  },
  name: "App",
  components: {
    CharacterInputs
  },
  methods: {
    btnRollClick() {
      var character = JSON.parse(localStorage.getItem("character"));
      const diceValue = this.rollDice(this.selectedDice);
      const bonusValue = this.getAttributeBonus(this.selectedAttribute);
      const bonusText = this.getAttributeLabel(this.selectedAttribute);

      let total = diceValue;
      let rollText = `Dado(${diceValue})`;
      if (bonusValue !== undefined) {
        total += bonusValue;
        rollText += `, ${bonusText}`;
      }
      if (this.proficiencyCheckbox) {
        total += character.prof;
        rollText += `, Proficiência(${character.prof})`;
      }
      this.result = total;
      this.outputText = rollText;
      this.showResult = true;
    },

    rollDice(diceName) {
      const random = (min, max) => Math.floor(Math.random() * (max - min + 1) + min);

      let result;
      switch (diceName) {
        case "d4":
          result = random(1, 4);
          break;

        case "d6":
          result = random(1, 6);
          break;

        case "d8":
          result = random(1, 8);
          break;

        case "d10":
          result = random(1, 10);
          break;

        case "d12":
          result = random(1, 12);
          break;

        case "d20":
          result = random(1, 20);
          break;

        case "d100":
          result = random(1, 100);
          break;
      }

      return result;
    },

    getAttributeBonus(attributeName) {
      var character = JSON.parse(localStorage.getItem("character"));
      var bonusValue;

      switch (attributeName) {
        case "str":
          bonusValue = character.str;
          break;

        case "cons":
          bonusValue = character.cons;
          break;

        case "dex":
          bonusValue = character.dex;
          break;

        case "int":
          bonusValue = character.int;
          break;

        case "wis":
          bonusValue = character.wis;
          break;

        case "char":
          bonusValue = character.char;
          break;

        default:
          bonusValue = undefined;
          break;
      }

      return bonusValue;
    },

    getAttributeLabel(attributeName) {
      var character = JSON.parse(localStorage.getItem("character"));
      var attributeLabel = "";

      switch (attributeName) {
        case "str":
          attributeLabel = `Força (${character.str})`;
          break;

        case "cons":
          attributeLabel = `Constituição (${character.cons})`;
          break;

        case "dex":
          attributeLabel = `Destreza (${character.dex})`;
          break;

        case "int":
          attributeLabel = `Inteligência (${character.int})`;
          break;

        case "wis":
          attributeLabel = `Sabedoria (${character.wis})`;
          break;

        case "char":
          attributeLabel = `Carisma (${character.char})`;
          break;
      }

      return attributeLabel;
    }
  }
};
</script>
