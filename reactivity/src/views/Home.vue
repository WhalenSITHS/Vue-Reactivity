<template>
  <div class="home">
    <h1>Vue Pizza Reactivity</h1>
    <ul class="toppings-list">
      <li
        class="topping"
        v-for="(topping, position) in possibleToppings"
        :key="position"
        v-on:click="addTopping"
      >
        {{ topping.item }}
      </li>
    </ul>
    <ul>
      <div v-for="(topping, position) in toppings" :key="position">
        <h2>{{ topping.item }}</h2>
        <img :src="topping.image" alt="" />
      </div>
    </ul>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "Home",
  components: {},
  data() {
    return {
      toppings: [],
      possibleToppings: [
        {
          item: "Cheese",
          image:
            "https://cdn.pixabay.com/photo/2014/12/21/23/34/cheese-575540_1280.png",
        },
        {
          item: "Pepperoni",
          image:
            "https://cdn.pixabay.com/photo/2021/02/01/15/50/pizza-5971090_960_720.png",
        },
        {
          item: "Olives",
          image:
            "https://cdn.pixabay.com/photo/2016/01/28/14/30/olives-1166333_960_720.png",
        },
        {
          item: "Meatball",
          image:
            "https://media.istockphoto.com/photos/meatballs-in-a-bowl-picture-id524052453?s=612x612",
        },
        {
          item: "Chicken",
          image:
            "https://cdn.pixabay.com/photo/2013/07/13/12/15/chicken-159496_960_720.png",
        },
      ],
    };
  },
  methods: {
    addTopping: function (event) {
      const top = event.target.innerText;
      const found = this.possibleToppings.filter((el) => el.item === top);
      this.toppings.push(found[0]);
    },
  },
};
</script>
<style>
.toppings-list {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  width: 80vw;
  margin: 1rem auto;
}
.topping {
  list-style: none;
}
img {
  width: 100px;
}
</style>
