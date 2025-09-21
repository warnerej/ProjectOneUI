<script>
  import Counter from './lib/Counter.svelte'
  import Activity from './lib/Activity.svelte'
  import Goal from './lib/Goal.svelte'
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
    <div class="counter-div">
      <Counter />
    </div>

    <div class="activity-div">
      <Activity />
    </div>

    <div class="goal-div">
      <Goal />
    </div>

  </div>


</main>

<style>
  .counter-div {
    margin-right: 1rem;
  }

  .activity-div {
    margin-right: 1rem;
  }

.card {
  display: inline-flex;
  flex-direction: row;
  padding: 2rem;
}
</style>