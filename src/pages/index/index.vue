<template>
	<div>
	  <index-header></index-header>
	  <index-content></index-content>
	  <index-formorder></index-formorder>
	  <index-message></index-message>
	  <index-footers></index-footers>
	</div>
</template>

<script>
  import IndexHeader from './header'
  import IndexContent from './content'
  import IndexFormorder from './formorder'
  import IndexMessage from './message'
  import IndexFooters from './footers'
  export default {
    name: 'index',
    components: {
      IndexHeader,
      IndexContent,
      IndexFormorder,
      IndexMessage,
      IndexFooters
    }
  }
</script>