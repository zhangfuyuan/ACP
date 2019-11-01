<template>
  <div class="portal-page home">
    <page-header />

    <div class="page-wrapper">
      <router-link to="/admin">666</router-link>
    </div>

    <page-footer />
  </div>
</template>

<script>
import PageHeader from '@/components/PageHeader'
import PageFooter from '@/components/PageFooter'

export default {
  name: 'Home',
  components: {
    PageHeader,
    PageFooter
  },
  data() {
    return {

    }
  },
  watch: {

  },
  methods: {

  }
}
</script>

<style lang="scss" scoped>
	.page-wrapper {
		background-color: #f9f9f9;
		min-height: 1000px;
	}
</style>
