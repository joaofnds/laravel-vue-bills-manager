<template>
	<div class="col m12">
		<div class="row">
			<nav>
				<div class="nav-wrapper">
					<a href="#" class="brand-logo">Code Contas</a>
					<a href="#" data-activates="mobile-demo" class="button-collapse"><i class="material-icons">menu</i></a>
					<ul id="nav-mobile" class="right hide-on-med-and-dow">
						<li v-for="o in links">
							<router-link :to="{path: o.routePath}">{{ o.label }}</router-link>
						</li>
					</ul>
					<ul id="mobile-demo" class="side-nav">
						<li v-for="o in links">
							<router-link :to="{path: o.routePath}">{{ o.label }}</router-link>
						</li>
					</ul>
				</div>
			</nav>
			<router-view></router-view>	
		</div>
	</div>
</template>

<script>
    export default {
        data() {
			return {
				links: [
					{ label: 'Contas a pagar', routePath: "/app/bill-pays" }
				]
			}
        },
        ready()  {
			$(function() {
				$(".button-collapse").sideNav();
			})
        }
    }
</script>
