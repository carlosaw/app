<template>
<div id="app">
	<div class=container-fluid>
		<div class="row bg-dark">
			<div class="col-lg-12">
				<p class="text-center text-light display-4 pt-2" style="font-size:25px;">CRUD Application</p> 				
			</div>
		</div>
	</div>
	<div class="container">
		<div class="row mt-3">
			<div class="col-lg-6">
				<h3 class="text-success float-left">Registered Users</h3>
			</div>
			<div class="col-lg-6">
				<button class="btn btn-success float-right" @click="showAddModal=true">
				<i class="fas fa-user"></i>&nbsp;&nbsp;Add New User</button>				
			</div>
		</div><br/>
	
		<b-table striped hover :fields="fields" :items="items">      
			<template v-slot:cell(actions)="data">
				<div>
					<button class="btn btn-info float-right" @click="showEditModal=true">
					<i class="fas fa-user"></i>&nbsp;&nbsp;Edit User</button>				
				</div>
			</template>
		</b-table>

		<!-- Add User Modal -->
		<div id="overlay" v-if="showAddModal">
			<div class="modal-dialog">
				<div class="modal-content">
					<div class="modal-header">
						<h5>Add New User</h5> 
						<b-button type="button" class="close" @click="showAddModal=false">
						<span aria-hidden="true">&times;</span></b-button>						
					</div>             
					<div class="modal-body p-6">
						<form action="#" method="post">
						<div class=form-group>
							<input type="text" name="name" class="form-control form-control-lg" placeholder="Name" />
						</div>
						<div class=form-group>
							<input type="tel" name="phone" class="form-control form-control-lg" placeholder="Phone" />
						</div>
						<div class=form-group>
							<input type="text" name="address" class="form-control form-control-lg" placeholder="Address" />
						</div>
						<div class=form-group>
							<input type="email" name="email" class="form-control form-control-lg" placeholder="E-mail" />
						</div>
						<div class="form-group">
							<button class="btn btn-info btn-block btn-lg" @click="showAddModal=false">Add User</button>
						</div>                    
						</form>                            
					</div>                
				</div>
			</div>
		</div> 
	</div>

	<!-- Edit User Modal -->
		<div id="overlay" v-if="showEditModal">
			<div class="modal-dialog">
				<div class="modal-content">
					<div class="modal-header">
						<h5>Edit User</h5> 
						<b-button type="button" class="close" @click="showEditModal=false">
						<span aria-hidden="true">&times;</span></b-button>						
					</div>             
					<div class="modal-body p-6">
						<form action="#" method="post">
							<div class=form-group>
								<input type="text" name="name" class="form-control form-control-lg" />
							</div>
							<div class=form-group>
								<input type="tel" name="phone" class="form-control form-control-lg" />
							</div>
							<div class=form-group>
								<input type="text" name="address" class="form-control form-control-lg" />
							</div>
							<div class=form-group>
								<input type="email" name="email" class="form-control form-control-lg" />
							</div>
							<div class="form-group">
								<button class="btn btn-info btn-block btn-lg" @click="showEditModal=false">Update User</button>
							</div>                    
						</form>                            
					</div>                
				</div>
			</div>
		</div> 
	</div>
</div>
</template>

<script>
export default {
	data() {
		return {
			items: [
				{ id: 1, name: 'Carlos', phone: '3682-5291', address:'New York', email:'carlos@gmail.com', isActive: true },
				{ id: 2, name: 'Ana Paula', phone: '3686-8374', address:'San Diego', email:'ana@gmail.com', isActive: true },
				{ id: 3, name: 'José', phone: '3682-9745', address:'San Francisco', email:'mara@gmail.com', isActive: true },
				{ id: 4, name: 'Alberto', phone: '3682-5291', address:'New York', email:'alberto@gmail.com', isActive: true },
				{ id: 5, name: 'Maria', phone: '3686-8374', address:'San Diego', email:'maria@gmail.com', isActive: true },
				{ id: 6, name: 'José', phone: '3682-9745', address:'San Francisco', email:'jose@gmail.com', isActive: true }				
			],
			fields: [
				{
					key: 'id',
					label: 'Id',
					sortable: true
				},
				{
					key: 'name',
					sortable: true
				},
				{
					key: 'phone',
					sortable: false
				},
				{
					key: 'address',
					label: 'Address',
				},
				{
					key: 'email',
					label: 'Email',
				},
				{
					key: 'actions',
					label: 'Ações',
				}
			],
			showAddModal:false,
			showEditModal:false			
		}
    }
}
</script>

<style>
#overlay {
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background: rgba(0, 0, 0, 0.6);
}
.mr2 {
  float:right;
}
</style>