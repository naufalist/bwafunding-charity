<script>
  import {
    onMount,
    // onDestroy,
    // beforeUpdate,
    // afterUpdate
  } from 'svelte';

  import CharityList from "../components/CharityList.svelte";
  import Header from '../components/Header.svelte';
  import Welcome from '../components/Welcome.svelte';
  import Promo from '../components/Promo.svelte';
  import Footer from '../components/Footer.svelte';

  // import {
  //   charities
  // } from "../data/charities.js";

  let title = "Charity";
  let charities = [];

  onMount(async function() {
    const res = await fetch('https://charity-api-bwa.herokuapp.com/charities')
    charities = await res.json()
  });

  // onMount(function() {
  //   console.log("onMount")
  // });
  // onDestroy(function() {
  //   console.log("onDestroy")
  // });
  // beforeUpdate(function() {
  //   console.log("beforeUpdate")
  // });
  // afterUpdate(function() {
  //   console.log("afterUpdate")
  // });
</script>

<Header />
<Welcome />
<CharityList {charities} />
<Promo />
<Footer />