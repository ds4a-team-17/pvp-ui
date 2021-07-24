<script>
  import { Link } from "svelte-routing";
</script>

<nav class="blue">
  <div class="nav-wrapper">
    <Link to="/"
      ><span class="brand-logo center">Parcel Volume Predictor</span></Link
    >
    <ul id="nav-mobile" class="right hide-on-med-and-down">
      <li><Link to="/">Home</Link></li>
    </ul>
  </div>
</nav>
