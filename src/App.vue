<template>
  <div id="app">
    <main>
      <aside>
        <h1>Car<span>Rental</span> - panel główny</h1>
      </aside>
      <section>
        <form>
          <button class="fleet" value="fleet" @click="saveData">
            Dodaj auto do floty
          </button>
          <button class="service" value="service" @click="saveData">
            Serwis i naprawa aut
          </button>
          <button class="issues" value="issues" @click="saveData">
            Zgłaszanie problemów
          </button>
        </form>
      </section>
    </main>
  </div>
</template>

<script>
export default {
  data() {
    return {
      chosenType: "",
    };
  },
  methods: {
    saveData(e) {
      this.coachViewContext.binding.set("value", e.target.value);
      this.coachViewContext.trigger();
      console.log(e.target.value);
    },
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Poppins&display=swap");
*,
*::before,
*::after {
  margin: 0;
  padding: 0;
}
div#app {
  width: 100%;
  height: 100vh;
  background-color: rgb(140, 160, 180);
  display: flex;
  flex-direction: column;
  font-family: "Poppins", sans-serif;
}

aside {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 15vh;
}

aside h1 {
  font-size: 40px;
}

aside h1 span {
  color: rgb(226, 25, 25);
}
section {
  width: 100%;
  height: 85vh;
}
form {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 85vh;
}

.fleet,
.service,
.repair,
.issues {
  height: 30%;
  width: 15%;
  margin: 0 1%;
  border: none;
  font-size: 30px;
  border-radius: 7px;
  background-color: rgb(30, 50, 70);
  color: rgb(240, 240, 240);
}

button:hover {
  background-color: rgb(50, 70, 90);
  cursor: pointer;
}
</style>
