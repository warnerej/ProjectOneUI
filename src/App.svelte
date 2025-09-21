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

.topnav h1{
  display: flex;
  justify-content: center;
  align-items: center;       
  padding: 1rem 2rem;
  position: relative;
  background-color: var(--secondary-color);
  margin: 0;
  width: 100%;
}

#title {
  font-size: 2.5rem;
  color: var(--accent-color);
}

#time {
  position: absolute;
  right: 1rem;
  top: 1rem;
  font-size: 1rem;
  font-weight: bold;
  color: var(--accent-color);
}

.card {
  display: inline-flex;
  flex-direction: row;
  justify-content: center;
  gap: 1rem;
  padding: 2rem;
  width: 100%;
}
</style>