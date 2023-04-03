<template>
        <!-- Personagem -->
        <div
      style="background-color: #93baca; overflow: auto"
      class="offcanvas offcanvas-start show"
      tabindex="-1"
      id="offcanvas"
      aria-labelledby="offcanvasLabel"
    >
      <div class="offcanvas-header">
        <h5 class="offcanvas-title" id="offcanvasLabel">Ficha de Personagem</h5>
        <button
          type="button"
          class="btn-close"
          data-bs-dismiss="offcanvas"
          aria-label="Close"
        ></button>
      </div>
      <div class="container-fluid" id="personagem">
        <label for="name">Nome</label>
        <input
          placeholder="Insira o nome"
          class="form-control"
          type="text"
          name=""
          id="name"
        />
        <br />

        <label for="strInput" class="mb-2">
          Força*
        </label>
        <input
          placeholder="Modificador de força Ex: 3"
          class="form-control"
          type="number"
          id="strInput"
        />
        <br />

        <label for="constInput" class="mb-2">
          Constituição*
        </label>
        <input
          placeholder="Modificador de Constituição Ex: 3"
          class="form-control"
          type="number"
          id="constInput"
        />
        <br />

        <label for="dexInput" class="mb-2">
          Destreza*
        </label>
        <input
          placeholder="Modificador de Destreza Ex: 3"
          class="form-control"
          type="number"
          id="dexInput"
        />
        <br />

        <label for="intInput" class="mb-2">
          Inteligência*
        </label>
        <input
          placeholder="Modificador de Inteligência Ex: 3"
          class="form-control"
          type="number"
          id="intInput"
        />
        <br />

        <label for="wisInput" class="mb-2">
          Sabedoria*
        </label>
        <input
          placeholder="Modificador de Sabedoria Ex: 3"
          class="form-control"
          type="number"
          id="wisInput"
        />
        <br />

        <label for="charInput" class="mb-2">
          Carisma*
        </label>
        <input
          placeholder="Modificador de Carisma Ex: 3"
          class="form-control"
          type="number"
          id="charInput"
        /><br />

        <label for="profInput" class="mb-2">
          Bonus de proficiência*
        </label>
        <input
          placeholder="Bonus de proficiência Ex: 3"
          class="form-control"
          type="number"
          id="profInput"
        />
        <br />
        <button
          type="button"
          class="btn btn-dark"
          data-bs-dismiss="offcanvas"
        >
          Salvar Personagem
        </button>
      </div>
    </div>
</template>