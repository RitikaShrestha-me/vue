<template>
    <!-- <input v-model="shopName" type="text" placeholder="Enter 1-2 word shop name"/> -->
  
  <ul class="ml-96">
    <!-- v-bind used to link dom with data in script -->
    <!-- v-for used for looping -->
    <!-- <li v-for="pet in pets" v-bind:key="pet">{{ pet }} <span>x</span></li> -->
    <li v-for="(wildPet, index) in wildPets" v-bind:key="wildPet.name">
      {{ wildPet.name }}
      <button v-on:click="remove(index)">x</button><br /><br>
    </li>
  </ul><br><br>

  <form @submit.prevent="addPet" class="ml-96">
    <!-- Can use v-bind: as : and its same -->
    <!-- <input type="text" v-bind:value="newPet" />
    <button :disabled="isDisabled">Add Pet</button> -->

    <!-- 
        v-model used to bind and directly change data in the actual value 
        .trim removes unnecessary white spaces
        .number converts input to number
        .lazy can be used in blogs and long texts to only update real value when clicked outside the entry field increasing efficiency
    -->
    <input placeholder="Enter Pet Name" v-model.trim="newPet" />

    <!-- v-on: is same as @ -->
    <button type="submit">Add Pet</button>
    <br />
    <span> Number of Pet Names: {{ petCount }} pets</span>
  </form>
</template>

<script>
export default{
  // computed are cached & only recalculated when its dependancies are changed
  computed: {
    petCount() {
      return this.wildPets.length;
    },
  },
  // methods are not cached
  methods: {
    addPet() {
      if (this.newPet !== "") {
        this.wildPets.unshift({ name: this.newPet });
        this.newPet = "";
      }
    },
    remove(index) {
      this.wildPets = this.wildPets.filter((wildPet, i) => i != index);
    },
  },
  data() {
    return {
      newPet: "",
      isDisabled: true,
      //   pets: ["Dog", "Cat", "Mongoose", "White Rat", "Cow"],
      wildPets: [
        { name: "Hyna" },
        { name: "Tiger" },
        { name: "Wild Buffalo" },
        { name: "Musk Deer" },
        { name: "Elephant" },
      ],
    };
  },
};
</script>