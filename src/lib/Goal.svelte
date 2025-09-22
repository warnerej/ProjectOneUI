<script>
  import ActivitySaved from "./ActivitySaved.svelte";
  const saveActivity = () => {
    sendChoice = choice;
    sendGoal = goalInput;

    addActivity();

    choice = "";
    goalInput = "";
  }
  let choice = $state("");
  let goalInput = $state("");

  let sendChoice = $state();
  let sendGoal = $state();

  let pastActivities = $state([]);

  const addActivity = () => {
    pastActivities = [...pastActivities, {title: sendChoice, description: sendGoal}]
  }
</script>

<div class="goal-title">
  Goal Tracker:
</div>

<div class="activity-three">

  <div class="checkboxes">
    <div id="question">
      Goal Feeling:
    </div>

    <label id="good">
      <input type="radio" bind:group={choice} value="Good"/>
        Good
    </label>

    <label id="okay">
      <input type="radio" bind:group={choice} value="Okay"/>
        Okay
    </label>

    <label id="bad">
      <input type="radio" bind:group={choice} value="Bad"/>
        Bad
    </label>

    <label id="not-Sure">
      <input type="radio" bind:group={choice} value="Not Sure"/>
        Not Sure
    </label>
  </div>

  <div class="goal-input">
    <textarea placeholder="Input your goal" bind:value={goalInput}></textarea>
  </div>

  <div class="submit-button">
    <button onclick={saveActivity}>Submit</button>
  </div>
</div>

<div class="past-activity-title">
  Past Goals:
</div>

<div class="scrolled-activity">
  {#each pastActivities as pastActivity}
    <ActivitySaved title={"You feel " + pastActivity.title + " about: "} description={pastActivity.description} />
  {/each}
</div>

<style>
  .past-activity-title {
    color: var(--accent-color);
    font-weight: bold;
    /* text-decoration: underline; */
    margin-top: 1rem;
    margin-bottom: .5rem;
  }

  #question {
    font-weight: bold;
    margin-bottom: .5rem;
  }

  .scrolled-activity {
    display: flex;
    flex-direction: column;

    height: 10rem;
    background-color: var(--secondary-color);
    /* border: 2px solid var(--accent-color); */
    border-radius: .5rem;
    padding: 0.5rem;
    overflow-y: auto;
    overflow-x: hidden;

    max-width: 20.5rem;
  }

  .activity-three {
    display: flex;
    background-color: var(--secondary-color);
    border-radius: .5rem;
    /* border: 2px solid var(--accent-color);  */
    padding: .5rem;
    justify-content: center;
    max-height: 10rem;
    min-height: 10rem;
  }

  .goal-title {
    color: var(--accent-color);
    font-weight: bold;
    /* text-decoration: underline; */
    margin-top: 1rem;
    margin-bottom: .5rem;
  }

  .checkboxes {
    justify-content: center;
    display: flex;
    flex-direction: column;
    color: var(--accent-color);
    font-weight: bold;
  }

  .checkboxes label {
    margin: .1rem;
    white-space: nowrap;
  }

  .goal-input {
    display: inline-flex;
    margin: 1rem;
    margin-bottom: 0rem;
  }

  .goal-input textarea{
    width: 8rem;
    padding-bottom: 6rem;
    resize: none;
  }

  .submit-button {
    display: inline-flex;
    justify-content: center;
    writing-mode: vertical-lr;
    padding: .75rem;
    padding-left: 1rem;
    padding-right: 1rem;
    /* border-left: 2px solid var(--accent-color); */
  }

  .submit-button button {
    width: 2rem;
    height: 8rem;
    border: 0;
    border-radius: .5rem;
    background-color: var(--accent-color);
    font-size: 1rem;
    font-weight: bold;
  }

  .submit-button button:hover {
    background-color: var(--hover-color);
  }


</style>