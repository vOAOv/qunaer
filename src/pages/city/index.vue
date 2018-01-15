<template>
  <div class="body">
	  <city-header></city-header>
	  <city-search  @searchCity="handleShowCity"></city-search>
	  <city-show v-if="show" :showCity="showCity"></city-show>
	  <city-list :hotCityInfo="hotCityInfo"
               :domesticCityList="domesticCityList"
               :city="city"
                v-else>
	  </city-list>
  </div>
</template>

<script>
  import CityHeader from './header'
  import CitySearch from './search'
  import CityList from './cityList'
  import CityShow from './cityShow'
  import axios from 'axios'
  export default {
    name: 'cityIndex',
    components: {
      CityHeader,
      CitySearch,
      CityList,
      CityShow
    },
    data () {
      return {
        hotCityInfo: [],
        domesticCityList: [],
        city: '',
        showCity: [],
        show: false
      }
    },
    methods: {
      getCityListData () {
        const city = localStorage.city ? localStorage.city : ' '
        axios.get('/api/cityList.json?city=' + city)
          .then(this.handleGetDataSucc.bind(this))
          .catch(this.handleGetDataErr.bind(this))
      },
      handleGetDataSucc (res) {
        const data = res.data.data
        this.hotCityInfo = data.hotcity
        this.domesticCityList = data.china
        this.city = data.city
        this.$bus.$emit('change', data.city)
        localStorage.city = data.city
      },
      handleGetDataErr () {
        console.log('error')
      },
      handleShowCity (e) {
        this.showCity = []
        var cityListLength = this.domesticCityList.length
        if (e) {
          var reg = /^[\u4e00-\u9fa5]+$/
          if (reg.test(e)) {
            this.showCity = []
            for (var i = 0; i < cityListLength; i++) {
              var chineseCityList = this.domesticCityList[i][1]
              var chineseCityLength = chineseCityList.length
              for (var j = 0; j < chineseCityLength; j++) {
                var str = chineseCityList[j].cityarea
                if (str.indexOf(e) !== -1) {
                  this.showCity.push(str)
                }
              }
            }
          } else {
            this.showCity = []
            for (var k = 0; k < cityListLength; k++) {
              var englishCityList = this.domesticCityList[k][1]
              var englishCityLength = englishCityList.length
              for (var l = 0; l < englishCityLength; l++) {
                var obj = englishCityList[l]
                if (obj.itemName.indexOf(e) !== -1) {
                  this.showCity.push(obj.cityarea)
                }
              }
            }
          }
          if (this.showCity) {
            this.show = true
          } else {
            this.show = false
          }
        } else {
          this.showCity = []
          this.show = false
        }
      }
    },
    created () {
      this.getCityListData()
    }
  }
</script>

<style lang="stylus" scopde>
	.body
		overflow: hidden
</style>
