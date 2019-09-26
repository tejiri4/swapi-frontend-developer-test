<template>
  <div class="character">
    <div class="character-image">
      <img src="https://res.cloudinary.com/store-manager/image/upload/v1569418364/character-1.jpg" />
    </div>
    <div class="character-content">
      <div class="character-name">{{ character.name }}</div>
      <small>{{ character.subName }}</small>
      <p>
        {{ character.description }}
        <a
          href
        >Read more</a>
      </p>
    </div>
  </div>
</template>
<script>
export default {
  name: 'Character',
  props: ['character'],
  data() {
    return {};
  },
};
</script>
<style scoped>
.character {
  display: flex;
  width: 600px;
  height: 400px;
  background-color: #f2f2f2;
  margin-right: 15rem;
}

.character-content {
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 1.5rem;
  width: 45%;
}

.character-content p {
  margin-top: 2rem;
  line-height: 1.7rem;
}

.character-content small {
  font-style: italic;
}

.character-name {
  font-size: 1.2rem;
  font-weight: 700;
}

.character-content a {
  font-size: 1.2rem;
  font-weight: 600;
  color: rgb(53, 53, 56);
}

.character-image img {
  width: 100%;
  height: 400px;
}

.character-image {
  width: 70%;
}
</style>
