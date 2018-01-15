<template>
  <div>
    <index-header :city="city"></index-header>
    <index-swiper :list="swiperInfo"></index-swiper>
    <index-icons :list="iconsInfo"></index-icons>
  </div>
</template>

<script>
  import IndexHeader from './header'
  import IndexSwiper from './swiper'
  import IndexIcons from './icons'
  import axios from 'axios'
  export default {
    name: 'index',
    components: {
      IndexHeader,
      IndexSwiper,
      IndexIcons
    },
    data () {
      return {
        city: '',
        swiperInfo: [],
        iconsInfo: []
      }
    },
    methods: {
      getIndexData () {
        const city = localStorage.city ? localStorage.city : ''
        axios.get('/api/index.json?city=' + city)
          .then(this.handleGetDataSucc.bind(this))
          .catch(this.handleGetDataErr.bind(this))
      },
      handleGetDataSucc (res) {
        const data = res.data.data
        this.swiperInfo = data.swiperList
        this.iconsInfo = data.iconList
        this.city = data.city
        localStorage.city = data.city
      },
      handleGetDataErr () {
        console.log('error')
      },
      bindEvents () {
        this.$bus.$on('change', this.handleCityChange.bind(this))
      },
      handleCityChange (value) {
        this.city = value
        this.getIndexData()
      }
    },
    created () {
      this.getIndexData()
      this.bindEvents()
    }
  }
</script>

<style></style>
