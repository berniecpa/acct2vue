<template>
<!-- Page Header -->
					<div class="page-header">
						<div class="row align-items-center">
							<div class="col">
								<h3 class="page-title">Invoice Grid</h3>
								<ul class="breadcrumb">
									<li class="breadcrumb-item"><router-link to="/index">Dashboard</router-link></li>
									<li class="breadcrumb-item active">Invoice Grid</li>
								</ul>
							</div>
							<div class="col-auto">
								<router-link to="/invoices" class="invoices-links">
									<i data-feather="list"></i>
                                </router-link>
								<router-link to="/invoice-grid" class="invoices-links active">
									<i data-feather="grid"></i>
                                </router-link>
							</div>
						</div>
					</div>
					<!-- /Page Header -->
</template>