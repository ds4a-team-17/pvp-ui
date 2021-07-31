<script>
	import "../node_modules/materialize-css/dist/css/materialize.min.css"
	import "../node_modules/materialize-css/dist/js/materialize.min.js"	
	import { Router, Route } from "svelte-routing";
	import Navbar from "./components/Navbar.svelte";
	import Home from "./pages/Home.svelte"
</script>

<Router basepath="/pvp-ui">
	<Navbar/>
	<div class="container">
		<Route path="/" component={Home} />
	</div>
</Router>