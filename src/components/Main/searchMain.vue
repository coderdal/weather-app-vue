<template>
  <section>
    <div class="inputBox">
      <span>
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
          <path
            d="M23.809 21.646l-6.205-6.205c1.167-1.605 1.857-3.579 1.857-5.711 0-5.365-4.365-9.73-9.731-9.73-5.365 0-9.73 4.365-9.73 9.73 0 5.366 4.365 9.73 9.73 9.73 2.034 0 3.923-.627 5.487-1.698l6.238 6.238 2.354-2.354zm-20.955-11.916c0-3.792 3.085-6.877 6.877-6.877s6.877 3.085 6.877 6.877-3.085 6.877-6.877 6.877c-3.793 0-6.877-3.085-6.877-6.877z"
          />
        </svg>
      </span>
      <input
        type="text"
        placeholder="Search by City Name"
        v-model="inputValue"
      />
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      inputValue: "",
    };
  },
};
</script>

<style scoped>
section {
  width: 100%;
  text-align: center;
}

div .inputBox {
  background: #fff;
  padding: 30px 20px;
  border-radius: 12px;
  width: 80%;
  max-width: 600px;
  margin: 0 auto;
  box-shadow: 2px 2px 25px rgba(0, 0, 0, 0.233);
  position: relative;
}

div .inputBox span {
  position: absolute;
  right: 30px;
  top: 50%;
  transform: translateY(-50%);
}

div .inputBox span svg {
  width: 20px;
  height: 20px;
  fill: rgba(128, 128, 128, 0.822);
}

div input {
  width: 100%;
  padding: 10px 22px;
  border: 1px solid rgba(224, 224, 224, 0.822);
  border-radius: 8px;
  font-size: 1em;
  font-weight: 500;
}

div input:focus {
  border: 1px solid rgba(105, 105, 105, 0.722);
  outline: none;
}
</style>
