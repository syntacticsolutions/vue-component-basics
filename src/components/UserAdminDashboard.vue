<template>
	<div class="user-admin-dashboard">
		<Search v-model="searchTerm"/>
		<Toast :val="searchTerm" />
		<Table :data="users" :searchTerm="searchTerm"  />
	</div>
</template>

<script>
let users = require('../assets/users.json')

import Table from './Table'
import Search from './Search'
import Toast from './Toast'

export default {
    name: 'HelloWorld',
    components: {
		Table,
		Search,
		Toast
    },
    data: () => ({
		users: users,
		searchTerm: ''
    }),
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.user-admin-dashboard {

}

</style>
