<template>

<table class="table table-stripped table-center table-hover datatable" id="usersTable">
											<thead class="thead-light">
												<tr>
													<th>Name</th>
													<th>Email</th>
													<th>Registered On</th>
													<th>Role</th>
													<th>Status</th>
													<th class="text-end">Actions</th>
												</tr>
											</thead>
											<tbody>
												<tr v-for="item in users" :key="item.id">
													<td>
														<h2 class="table-avatar">
															<router-link to="/profile"><img class="avatar avatar-sm me-2 avatar-img rounded-circle" :src="loadImg(item.customer_image)" alt="User Image"> {{item.customer_name}}</router-link>
														</h2>
													</td>
													<td>{{item.email}}</td>
													<td>{{item.registered_on}}</td>
													<td><span class="text-success" v-if="item.role == 'Admin'">Admin</span>
                                                        <span class="text-info" v-if="item.role == 'Customer'">Customer</span>
                                                       </td>
													<td>
													<span class="badge badge-pill bg-success-light" v-if="item.status == 'Active'">Active</span>
                                                        <span class="badge badge-pill bg-danger-light" v-if="item.status == 'Inactive'">Inactive</span>
													</td>
													<td class="text-end">
														<a href="javascript:void(0);" class="btn btn-sm btn-white text-success me-2"><i class="far fa-edit me-1"></i> Edit</a> 
														<a href="javascript:void(0);" class="btn btn-sm btn-white text-danger me-2"><i class="far fa-trash-alt me-1"></i>Delete</a>
													</td>
												</tr>
											</tbody>
										</table>
</template>
<script>
import users from '../../../assets/json/users.json';
import util from '../../../assets/utils/util'
const images = require.context('../../../assets/img/profiles', false, /\.png$|\.jpg$/)
export default {
	data() {
		return {
			users: users
		}
	},
	mounted() {
	util.datatable('#usersTable')
	},
	methods: {
        loadImg(imgPath) {
            return images('./' + imgPath).default
        },
        
    },
}
</script>