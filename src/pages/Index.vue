<template>
  <div class="bg-primary text-white q-pt-lg q-px-md">
    <div class="row justify-center">
      <div class="column">
        <div class="text-weight-bold text-h1 bb q-pb-lg text-center title">
          刘秀
        </div>

        <div class="q-mt-lg">
          <main-introduction />
        </div>

        <div class="text-subtitle1 q-my-xl text-center">
          <div>
            {{ $t('copyright') }}
          </div>
          <div>
            {{ $t('deployed') }} <a href="https://github.com/" style="color: white !important;">GitHub</a>, <a href="https://github.com/etherein/liuxiu-about" target="_blank" style="color: white !important;">{{ $t('viewSource') }}</a>
          </div>
          <div class="inline text-subtitle2">
            <span class="langOpt" @click="changeLocale('en-US')">English</span> | <span class="langOpt" @click="changeLocale('zh-CN')">中文</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { useI18n } from "vue-i18n";
import MainIntroduction from "layouts/MainIntroduction";
export default {
  name: "Index.vue",
  components: { MainIntroduction },

  setup() {
    const { locale } = useI18n({ useScope: 'global' });
    return { locale }
  },

  methods: {
    changeLocale(locale) {
      this.locale = locale;
      this.$q.localStorage.set('locale', locale);
    },
  }
}
</script>
<style scoped>
.bb {
  border-bottom: 2px solid #fff;
}
.title {
  font-family: MyFont;
}
</style>
