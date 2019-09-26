<template>
  <div>
    <Search />
      <div class="title">
        <div class="title-details">Starwars Characters</div>
        <div class="line"></div>
      </div>
    <div class="select-group">
      <Select description="FILTER" :options="filterOptions"/>
      <Select description="VIEW" :options="viewOptions"/>
    </div>
    <div class="character-group">
      <div v-for="(character, index) in characters" v-bind:key="index">
        <Character :character="character"/>
      </div>
    </div>
  </div>
</template>
<script>
import Search from './search/Search';
import Select from './select/Select';
import Character from './character/Character';

export default {
  name: 'Home',
  data() {
    return {
      filterOptions: [{ detail: 'Male' }],
      viewOptions: [{ detail: 'Grid' }],
      characters: [
        {
          image: 'https://res.cloudinary.com/store-manager/image/upload/v1569418364/character-1.jpg',
          name: 'Luke Skywalker',
          subName: 'Son of Analkin',
          description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore voluptate...',
        },
        {
          image: 'https://res.cloudinary.com/store-manager/image/upload/v1569418364/character-1.jpg',
          name: 'Luke Skywalker',
          subName: 'Son of Analkin',
          description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore voluptate...',
        },
      ],
    };
  },
  components: {
    Search,
    Select,
    Character,
  },
};
</script>
<style scoped >
.title {
  display: flex;
  justify-content: center;
  flex-direction: column;
  text-align: center;
  margin-top: 4rem;
}

.title-details {
  font-size: 2.0rem;
  font-weight: bold;
}

.title .line {
  height: 0.4rem;
  background-color: #2c3e50;
  width: 7rem;
  margin: 0 auto;
  margin-top: 1rem;
}

.select-group {
  margin: 2rem 7rem;
  display: flex;
}

.character-group {
   margin: 2rem 7rem;
   display: flex;
}
</style>
