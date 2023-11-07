<template>
  <div class="q-gutter row">
    <q-card
      v-for="(item, index) in recipeData"
      :key="index"
      style="height: 500px; width: 100%; max-width: 300px"
      class="q-ma-md col-2"
      flat
      bordered
    >
      <q-img :src="item.imageURL" :ratio="1"/>

      <q-card-section>
        <q-btn
          fab
          color="primary"
          :icon="item.Icon"
          class="absolute"
          style="top: 0; right: 12px; transform: translateY(-50%)"
        />

        <div class="q-mt-xs row no-wrap items-center">
          <div class="col text-h6 ellipsis">{{ item.name }}</div>
        </div>

        <q-rating v-model="item.Rating" :max="5" size="32px" />
      </q-card-section>

      <q-card-section class="q-pt-none">
        <div class="text-caption text-grey ellipsis">
            {{ item.Description }}
        </div>
      </q-card-section>

      <q-separator />

      <q-card-actions class="justify-center" @click="viewRecipeDetails(item.id)">
        <q-btn flat round color="primary" icon="visibility"></q-btn>
        <q-btn flat color="primary"> View </q-btn>
      </q-card-actions>
    </q-card>
  </div>
</template>

<script>
import dummyData from "../DummyData.json";
// const dummyData = require('../DummyData.json');
export default {
  data() {
    return {
      // recipeData:dummyData,
    };
  },
  computed: {
    recipeData() {
      return dummyData.Data;
    },
  },
  methods:{
    viewRecipeDetails(index){
       console.log("View Recipe Details Clicked",index);
    }
  },
  mounted() {
    // console.log(dummyData);
  },
};
</script>

<style scoped></style>
