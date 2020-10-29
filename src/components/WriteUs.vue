<template>
  <div class="wrapper">
    <div class="text-center titleText">Напишите нам</div>
    <v-text-field
      label="Имя"
      :rules="rules"
      hide-details="auto"
      v-model="clientName"
      :value="clientName"
      class="formField"
    ></v-text-field>
    <v-text-field
      label="Телефон"
      v-model="clientPhone"
      :value="clientPhone"
      :rules="rules"
      class="formField"
    ></v-text-field>
    <v-menu
      transition="slide-x-transition"
      :close-on-content-click="false"
      max-width="230"
      nudge-right="420"
    >
      <template v-slot:activator="{ on, attrs }">
        <div
          class="type lighten-5 border-0"
          v-bind="attrs"
          v-on="on"
        >
          <v-btn class="typeBtn" large color="white" depressed>
            Тип Услуги
            <v-icon dark right class="ml-4" color="primary">
              fas fa-chevron-circle-right
            </v-icon>

          </v-btn>

        </div>
      </template>
      <v-list>
        <v-list-item-group
          v-model="selectedItem"
          color="primary"
          active-class="activeClass"
        >
          <v-list-item
            v-for="(item, i) in items"
            :key="i"
          >
            <v-list-item-content>
              <v-list-item-title v-text="item.title"></v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-menu>
    <div class="sendBtnWrapper">
      <v-btn
        large
        class="mx-auto sendBtn"
        :loading="loading"
        :disabled="loading"
        color="primary"
        @click="submitForm"
      >
        Отправить
      </v-btn>
    </div>
  </div>
</template>

<script>
export default {
  name: 'WriteUs',
  data: () => ({
    rules: [
      (value) => !!value || 'Обязательное поле для заполнения',
      (value) => (value && value.length >= 3) || 'Недостаточно символов',
    ],
    items: [
      { title: 'Веб-сайт' },
      { title: 'Мобильное приложение' },
      { title: 'SEO оптимизация' },
      { title: 'SMM' },
    ],
    loader: null,
    loading: false,
    clientPhone: null,
    clientName: null,
    selectedItem: null,
    showError: false,
  }),
  methods: {
    submitForm() {
      this.loader = 'loading';
      if (this.clientPhone && this.clientName && this.selectedItem) {
        this.$emit('form', {
          name: this.clientName,
          phone: this.clientPhone,
          type: this.items[this.selectedItem].title,
        });
        console.log({
          name: this.clientName,
          phone: this.clientPhone,
          type: this.items[this.selectedItem].title,
        });
      } else {
        this.showError = true;
      }
    },
  },
  watch: {
    loader() {
      const l = this.loader;
      this[l] = !this[l];

      setTimeout(() => (this[l] = false), 2000);

      this.loader = null;
    },
  },
};
</script>

<style scoped>
  button {
    outline: none;
  }

  .typeBtn {
    margin-top: 2%;
    width: 40%;
  }

  .type {
    display: flex;
    justify-content: center;
  }

  .sendBtnWrapper {
    display: flex;
    justify-content: center;
    margin: 5% 0;
  }

  .sendBtn {
    width: 40%;
  }

  .formField {
    margin: 0 20% 3% 20%;
  }


  .titleText {
    font-family: Segoe UI;
    font-style: normal;
    font-weight: bold;
    font-size: 36px;
    line-height: 48px;
    margin: 5% 0;
  }

  .wrapper {
    background: linear-gradient(
      180deg,
      rgba(224, 223, 255, 0.8) 0%,
      rgba(236, 236, 255, 0.5) 100%
    );
    height: 100%;
  }
</style>
