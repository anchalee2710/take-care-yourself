<template>
  <q-page style="padding: 0 10px">
    <q-carousel
      animated
      v-model="slide"
      arrows
      navigation
      infinite
      style="
        width: 100%;
        height: 60vw;
        border-radius: 15px;
        box-shadow: 0px 2px 4px 1px rgba(0, 0, 0, 0.25);
        margin-bottom: 30px;
      "
    >
      <q-carousel-slide :name="1" img-src="images/carouselImage.png" />
      <q-carousel-slide :name="2" img-src="images/113.jpg" />
      <q-carousel-slide :name="3" img-src="images/114.jpg" />
      <q-carousel-slide :name="4" img-src="images/115.jpg" />
    </q-carousel>

    <div>
      <q-img
        src="images/111.jpg"
        style="border-radius: 15px; margin-bottom: 30px"
      />
    </div>
    <div
      class="row justify-center items-center q-gutter-x-md"
      style="margin-bottom: 30px"
    >
      <div class="col flex justify-center">
        <q-btn
          to="new-page"
          class="flex-1"
          style="background-color: #e0f2f2; height: 130px; border-radius: 10px"
        >
          <q-img
            :ratio="1"
            src="images/9.png"
            style="width: 70px; height: 70px; margin-top: 5px"
          />
          <span style="font-weight: 500">ฟีดข่าว</span>
        </q-btn>
      </div>

      <div class="col flex justify-center">
        <q-btn
          class="flex-1"
          style="background-color: #e0f2f2; height: 130px; border-radius: 10px"
          to="check-page"
        >
          <q-img
            :ratio="1"
            src="images/10.png"
            style="width: 60px; height: 60px; margin-top: 5px"
          />
          <span style="font-weight: 500">ตรวจสอบไทม์ไลน์</span>
        </q-btn>
      </div>
      <div class="col flex justify-center">
        <q-btn
          to="add-timline-page"
          class="flex-1"
          style="background-color: #e0f2f2; height: 130px; border-radius: 10px"
        >
          <q-img
            :ratio="1"
            src="images/11.png"
            style="width: 75px; height: 75px"
          />
          <span style="font-weight: 550; font-size: 13px">บันทึกไทม์ไลน์</span>
        </q-btn>
      </div>
    </div>

    <div class="row justify-center items-center q-gutter-x-md">
      <div class="col flex justify-center">
        <q-btn
          to="hospital-contact"
          class="flex-1"
          style="background-color: #e0f2f2; height: 130px; border-radius: 10px"
        >
          <q-img
            :ratio="1"
            src="images/12.png"
            style="width: 70px; height: 70px; margin-top: 5px"
          />
          <span style="font-weight: 500">โรงพยาบาล</span>
        </q-btn>
      </div>
      <div class="col flex justify-center">
        <q-btn
          to="station"
          class="flex-1"
          style="background-color: #e0f2f2; height: 130px; border-radius: 10px"
        >
          <q-img
            :ratio="1"
            src="images/13.png"
            style="width: 60px; height: 60px"
          />
          <span style="font-weight: 550; font-size: 11.5px">
            ตรวจสอบพื้นที่เสี่ยงใกล้คุณ</span
          >
        </q-btn>
      </div>
      <div class="col flex justify-center">
        <q-btn
          to="static-page"
          class="flex-1"
          style="background-color: #e0f2f2; height: 130px; border-radius: 10px"
        >
          <q-img
            :ratio="1"
            src="images/16.png"
            style="width: 45px; height: 75px; margin-top: 5px"
          />
          <span style="font-weight: 500">สถิติผู้ติดเชื้อ</span>
        </q-btn>
      </div>
    </div>

    <div class="q-mt-md" />

    <!-- <div v-for="(item, i) in data" :key="i">
      <q-input outlined label="title" v-model="item.title"></q-input>
      <div class="" v-for="(text, i) in item.groupText" :key="i">
        <q-input
          label="text"
          type="text"
          outlined
          v-model="text.text"
        ></q-input>
      </div>
      <q-btn label="เพิ่ม text" @click="addText(i)" />
    </div>
    <q-btn label="บันทึก" @click="onSubmit()" />
    <q-btn label="เพิ่มทั้งก้อน" @click="addTimeLine" /> -->
  </q-page>
</template>

<script>
import { defineComponent, ref } from "vue";
export default defineComponent({
  name: "IndexPage",
  setup() {
    const data = ref([
      {
        title: "",
        groupText: [
          {
            text: "",
          },
        ],
      },
    ]);

    const addTimeLine = () => {
      const test = data.value.push({
        title: "",
        groupText: [
          {
            text: "",
          },
        ],
      });
    };
    const onSubmit = () => {};
    const addText = (index) => {
      const test = data.value[index].groupText.push({ text: "" });
    };
    return {
      addTimeLine,
      onSubmit,
      addText,
      data,
      slide: ref(1),
    };
  },
});
</script>
