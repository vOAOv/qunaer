<template>
  <div>
    <index-header @change="handleDataChange"></index-header>
    <index-body :list="listInfo"></index-body>
  </div>
</template>

<script>
import IndexHeader from './header'
import IndexBody from './body'
import axios from 'axios'
export default {
  name: 'Tour',
  components: {
    IndexHeader,
    IndexBody
  },
  data () {
		return {
  		listInfo: []
  	}
  },
  methods: {
		getIndexData () {
  		axios.get('/api/index.json')
  			.then(this.hendleGetDataSucc.bind(this))
  			.catch(this.handleGetDataErr.bind(this))
  	},
  	hendleGetDataSucc (res) {
			if (res && res.data && res.data.data.list) {
				const data = res.data.data
				this.listInfo = data.list
			}
  	},
  	handleGetDataErr () {
  		console.log('err')
  	},
  	handleDataChange (text) {
  		if (!this.oldList) {

  		} else {
  			for (var j = 0; j < this.listInfo.length; j ++) {
  				if (!this.oldList) {
  					this.oldList = []
  				} else {
  					this.oldList.push(this.listInfo[j])
  				}
  			}
  			console.log(this.oldList)
  		}
  		console.log(this.listInfo)
  		this.text = text
  		this.newList = []
			for (var i = 0; i < this.listInfo.length; i ++) {
				if (this.listInfo[i].address === this.text) {
					this.newList.push(this.listInfo[i])		
				}
			}	
			this.listInfo = this.newList
  	}
  },
  created () {
  	this.getIndexData()
	}
}
</script>

<style>

</style>
