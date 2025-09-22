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

  let darkMode = false;

  function toggleTheme() {
    darkMode = !darkMode;
    document.documentElement.setAttribute("data-theme", darkMode ? "dark" : "light");
  }
</script>

<main>

  <div class="topnav">
    <h1 id="title">Language Tracker</h1>
    <p id="time">Hello Elliot, it's currently {time}</p>
    <p id="user-since">You have been a user since 2022</p>
  </div>

  <div class="card">
    <div class="activity-div">
      <Activity />
    </div>

    <div class="counter-div">
      <Counter />
    </div>

    <div class="goal-div">
      <Goal />
    </div>
  </div>

  <button on:click={toggleTheme}>
    {darkMode ? 'Switch to Light Mode' : 'Switch to Dark Mode'}
</main>



<style>
:root {
  --primary-color: #ffffff;
  --secondary-color:  #F5F5F7;
  --accent-color: #4a9f99;
  --hover-color: #316864;
}

:root[data-theme="dark"] {
  --primary-color: #2f2f2f;
  --secondary-color:  #b8b8b8;
  --accent-color: #ffffff;
  --hover-color: #306e6a;
}

.topnav h1{
  display: flex;
  justify-content: center;
  align-items: center;       
  padding: 1rem;
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

#user-since {
  position: absolute;
  left: 1rem;
  top: 1rem;
  font-size: 1rem;
  font-weight: bold;
  color: var(--accent-color);
}

.card {
  display: flex;
  flex-direction: row;
  justify-content: center;
  gap: 1rem;
  padding: 2rem;
  width: 100%;
}
</style>