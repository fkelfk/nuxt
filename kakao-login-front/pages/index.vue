<template>
  <a @click="loginWithKakao">
    <img src="/kakao_login_medium_narrow.png"/>
  </a>
</template>

<script>
export default {
  name: 'IndexPage',
  methods: {
    kakaoInit () {
      Kakao.init('facc6cf0ffb6bf8618a80d5bbb561896')// KaKao client key
      Kakao.isInitialized()
    },
    async loginWithKakao () {
      await Kakao.Auth.authorize({
        redirectUri: `${window.location.origin}/kakao-callback`
      })
    }
  },
  mounted () {
    this.kakaoInit()
  }
}
</script>

