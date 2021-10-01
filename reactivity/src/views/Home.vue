<template>
  <div class="home">
    <h1>Vue Pizza Reactivity</h1>
    <ul class="toppings-list">
      <li class="topping" v-for="(topping,position) in possibleToppings" :key="position" @click="addTopping(event)">
        {{ topping.item }}
      </li>
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
            "https://cdn.pixabay.com/photo/2014/12/21/23/34/cheese-575540_1280.png",
        },
        {
          item: "Olives",
          image:
            "https://cdn.pixabay.com/photo/2014/12/21/23/34/cheese-575540_1280.png",
        },
        {
          item: "Meatball",
          image:
            "https://cdn.pixabay.com/photo/2014/12/21/23/34/cheese-575540_1280.png",
        },
        {
          item: "Chicken",
          image:
            "https://cdn.pixabay.com/photo/2014/12/21/23/34/cheese-575540_1280.png",
        },
      ],
    };
  },
  methods: {
    addTopping: function (event) {
      console.log(event.target);
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
