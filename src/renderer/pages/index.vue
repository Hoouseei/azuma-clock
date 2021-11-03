<template>
  <main>
    <client-only>
      <v-app>
        <v-main>
          <MainCanvas />
          <InfoWrapper v-if="isShowText" />
          <LevelSlider></LevelSlider>
          <SettingModal v-model='isShowSetting'></SettingModal>
        </v-main>
      </v-app>
    </client-only>
  </main>
</template>

<script>
import LevelManager from '~/assets/scripts/level-manager.js'

export default {
  mounted() {
    this.update()
  },
  data() {
    return {
      isShowText: LevelManager.levelStatus.isShowText,
      isShowSetting: false
    }
  },
  methods: {
    update: function() {
      requestAnimationFrame(this.update)
      this.isShowText = LevelManager.levelStatus.isShowText
    }
  }
}
</script>

<style lang="stylus">
main
  position relative
  width 1280px
  height 800px
</style>
