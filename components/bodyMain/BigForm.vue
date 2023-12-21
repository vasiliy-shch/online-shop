<template>
  <section class="bigForm">
    <div class="bigForm__titlesBlock">
      <h3 class="bigForm__title">An easy way to send requests to all suppliers</h3>
      <p class="bigForm__subtitle">
        Lorem ipsum dolor sit amet, consectetur
        adipisicing elit, sed do eiusmod tempor incididunt.
      </p>
      <a class="formBlock__sendButton_link" href="#">
        <button
          class="formBlock__sendFormButton desktopDisplay__none"
        >
          Send inquiry
        </button>
      </a>
    </div>
    <form class="bigForm__formBlock">
      <h3 class="formBlock__titleForm">Send quote to suppliers</h3>
      <input class="formBlock__itemInput" value="What item you need?">
      <textarea
        class="formBlock__itemTextarea"
        placeholder="Type more details"
      >
      </textarea>
      <div class="formBlock__quantityBlock">
        <input class="quantityBlock__title" type="number">
        <button
          v-if="!isEdit"
          class="quantityBlock__measurement"
          @click.prevent="show"
        >
          {{ selectedMeasurement.name }}
        </button>
        <div v-else-if="isEdit">
          <button
            class="quantityBlock__measurement"
            @click.prevent="hide"
          >
            {{ selectedMeasurement.name }}
          </button>
          <ul class="quantityBlock__measurementsList">
            <li
              v-for="measurement in measurements"
              :key = 'measurement.id'
              :class="['quantityBlock__measurementInList',
                selectedMeasurement.id === measurement.id ?
                'quantityBlock__measurementInList_selectedMeasurement' : '']"
              @click="selectMeasurement(measurement)"
            >
              {{ measurement.name }}
            </li>
          </ul>
        </div>
      </div>
      <button @click.prevent class="formBlock__sendFormButton">Send inquiry</button>
    </form>
  </section>
</template>

<script>
export default {
  data () {
    return {
      isEdit: false,
      selectedMeasurement:
        {
          id: 1,
          name: 'Pcs'
        },
      measurements: [
        {
          id: 1,
          name: 'Pcs'
        },
        {
          id: 2,
          name: 'kg'
        },
        {
          id: 3,
          name: 'mg'
        },
        {
          id: 4,
          name: 'meter'
        },
        {
          id: 5,
          name: 'L'
        },
        {
          id: 6,
          name: 'mL'
        },
        {
          id: 7,
          name: 'Lb'
        },
        {
          id: 8,
          name: 'ounce'
        }
      ]
    }
  },
  methods: {
    show () {
      this.isEdit = true
    },
    hide () {
      this.isEdit = false
    },
    selectMeasurement (measurement) {
      this.selectedMeasurement = measurement
      this.isEdit = false
    }
  }
}
</script>

<style>
.bigForm {
 width: 1180px;
 height: 420px;
 margin: 20px auto 0;
 display: flex;
 justify-content: space-between;
 background-image: url(~/assets/images/bodyMain/bigBlueForm.svg);
}
@media screen and (max-width: 879px) {
  .bigForm {
    width: 100%;
    height: 150px;
    margin-top: 10px;
    background-size: cover;
  }
}
.bigForm__titlesBlock {
  display: flex;
  flex-direction: column;
  width: 440px;
  height: 139px;
  margin: 40px 0 0 40px;
  color: white;
  font-family: 'Inter';
  text-align: left;
}
@media screen and (max-width: 879px) {
  .bigForm__titlesBlock {
    width: 217px;
    height: 44px;
    margin: 25px 0 0 23px;
  }
}
.bigForm__title {
  margin: 0;
  font-size: 32px;
  line-height: 39px;
  font-weight: 500;
  font-style: bold;
}
@media screen and (max-width: 879px) {
  .bigForm__title {
    font-size: 18px;
    line-height: 22px;
  }
}
.bigForm__subtitle {
  width: 390px;
  text-align: left;
  margin-top: 13px;
  font-size: 16px;
  line-height: 24px;
}
@media screen and (max-width: 879px) {
  .bigForm__subtitle {
    display: none;
  }
}
.bigForm__formBlock {
  display: flex;
  flex-direction: column;
  width: 491px;
  height: 346px;
  margin: 30px 31px 0 0;
  border-radius: 6px;
  background-color: white;
  font-family: 'Inter';
}
@media screen and (max-width: 879px) {
  .bigForm__formBlock {
    display: none;
  }
}
.formBlock__titleForm {
  font-size: 20px;
  line-height: 28px;
  margin: 22px 0 0 20px;
  font-weight: 500;
}
.formBlock__itemInput {
  font-size: 16px;
  line-height: 19px;
  padding: 10px 0 9px 9px;
  border: 1px solid #DEE2E7;
  border-radius: 6px;
  width: 429px;
  margin: 18px 0 0 20px;
  outline: none;
}
.formBlock__itemTextarea {
  font-family: 'Inter';
  font-size: 16px;
  line-height: 19px;
  padding: 10px 36px 9px 9px;
  border: 1px solid #DEE2E7;
  border-radius: 6px;
  width: 393px;
  height: 52px;
  margin: 20px 0 0 20px;
  outline: none;
  resize: none;
  background-image: url(~/assets/images/bodyMain/triangleTextarea.svg);
  background-repeat: no-repeat;
  background-position: 425px 59px;
}
.formBlock__quantityBlock {
  display: flex;
  margin: 20px 0 0 20px;
  height: 40px;
  z-index: 1;
}
.quantityBlock__title {
  font-size: 16px;
  line-height: 19px;
  padding: 10px 0 9px 9px;
  border: 1px solid #DEE2E7;
  border-radius: 6px;
  width: 196px;
  outline: none;
  appearance: none;
}
.quantityBlock__measurement {
  width: 111px;
  height: 40px;
  margin-left: 8px;
  border: 1px solid #DEE2E7;
  border-radius: 6px;
  background-image: url(~/assets/images/apperance.svg);
  background-position: 79px 8px;
  background-repeat: no-repeat;
  background-color: white;
  cursor: pointer;
  text-align: start;
  padding-left: 10px;
  font-size: 16px;
  line-height: 19px;
}
.quantityBlock__measurementsList {
  width: 111px;
  margin: 0 0 0 8px;
  padding: 0 0 0 0px;
  list-style-type: none;
  border: 1px solid #DEE2E7;
  box-shadow: 0 4px 4px rgba(0,0,0,0.25);
  background-color: white;
}
.quantityBlock__measurementInList {
  font-size: 16px;
  line-height: 19px;
  padding: 5px 0 5px 10px;
  cursor: pointer;
}
.quantityBlock__measurementInList:hover {
  background-color: #E5F1FF;
}
.quantityBlock__measurementInList_selectedMeasurement {
  color: #0D6EFD;
}
.formBlock__sendFormButton {
  margin: 20px 0 0 20px;
  background-color: #0D6EFD;
  color: white;
  border: none;
  border-radius: 6px;
  cursor: pointer;
  height: 40px;
  width: 128px;
  padding: 10.5px 16px;
  font-size: 16px;
  line-height: 19px;
}
.formBlock__sendFormButton:hover {
  opacity: 0.8;
}
@media screen and (max-width: 879px) {
  .formBlock__sendFormButton {
    font-size: 13px;
    line-height: 16px;
    height: 30px;
    width: 98px;
    padding: 7px 10px;
    margin: 17px 0 0 3px;
  }
}
.formBlock__sendButton_link {
  text-decoration: none;
}
.desktopDisplay__none {
  display: none;
}
@media screen and (max-width: 879px) {
  .desktopDisplay__none {
    display: block;
  }
}
</style>
