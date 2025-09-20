<script>
  import Counter from './lib/Counter.svelte'
  import { onDestroy } from 'svelte';

  let time = new Date().toLocaleTimeString();

  const interval = setInterval(() => {
    time = new Date().toLocaleTimeString();
  }, 1000);

  onDestroy(() => clearInterval(interval));
</script>

<main>

  <div class="topnav">
    <h1 id="title">Language Tracker</h1>
    <p id="time">Hello Elliot, it's currently {time}</p>
  </div>



  <div class="card">
    <Counter />
  </div>

</main>

