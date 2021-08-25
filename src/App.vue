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
    return {};
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
@import "./styles/style.css";
</style>
