<template>
  <div class="hero-infos">
    <img 
      :src="`${dataDragonBaseUrl}/img/champion/${this.championData.name}.png`" 
      alt="Hero pic square" class="hero-pic" 
    />
    <h2>{{ this.championData.name }}</h2>
    <h3>{{ this.championData.title }}</h3>
    <div class="main-infos">
      <div class="role">
        <p class="label">Rôle</p>
        <p class="value">
          <span :key="key" v-for="(role, key) in this.championData.tags">{{ role }}</span>
        </p>
      </div>
      <div class="difficulty">
        <p class="label">Difficulté</p>
        <p class="value">{{ this.championData.infos.difficulty }}/5</p>
      </div>
    </div>
    <div class="sub-infos">
      <div class="attack">
        <p class="label">Attaque</p>
        <p class="value">{{ this.championData.infos.attack }}</p>
      </div>
      <div class="defense">
        <p class="label">Defense</p>
        <p class="value">{{ this.championData.infos.defense }}</p>
      </div>
      <div class="magic">
        <p class="label">Magie</p>
        <p class="value">{{ this.championData.infos.magic }}</p>
      </div>
    </div>
    <div class="history">
      <p class="label">Histoire du héro</p>
      <p class="content">{{ this.championData.blurb }}</p>
      <div class="see-more">
        <p>Lire la suite</p>
      </div>
    </div>
  </div>
</template>

<script>
import { mapGetters } from "vuex";

export default {
  props: {
    championData: {
      type: Object,
      isRequired: true
    }
  },
  computed: {
    ...mapGetters(["dataDragonBaseUrl"])
  }
};
</script>
