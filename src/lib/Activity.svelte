<script>
  import ActivitySaved from "./ActivitySaved.svelte";

  let activityTitle = $state();
  let activityDesc = $state();

  let sendTitle = $state();
  let sendDesc = $state();

  let pastActivities = $state([]);

  const addActivity = () => {
    pastActivities = [...pastActivities, {title: sendTitle, description: sendDesc}]
  }

  const saveActivity = () => {

    sendTitle = activityTitle;
    sendDesc = activityDesc;
    if (sendTitle != "" && sendDesc != "") {
      addActivity();
    }

    activityDesc = "";
    activityTitle = "";    

  }
</script>

<div class="past-activity-title">
  Activities Tracker:
</div>

<div class="activity-two">
  <div class="inputs">
    <div class="activity-title-input">
      <input type="text" placeholder="Activity Title" bind:value={activityTitle}/>
    </div>
    <div class="activity-description-input">
        <input type="text" placeholder="Activity Description" bind:value={activityDesc}/>
    </div>
  </div>
  <div class="submit-button">
    <button onclick={saveActivity}>Submit</button>
  </div>
</div>

<div class="past-activity-title">
  Past Activities:
</div>

<div class="scrolled-activity">
  {#each pastActivities as pastActivity}
    <ActivitySaved title={pastActivity.title} description={pastActivity.description} />
  {/each}
</div>

<style>
  input::placeholder {
    text-align: left;
    padding-top: 5px;
  }

  .past-activity-title {
    color: var(--accent-color);
    font-weight: bold;
    text-decoration: underline;
    margin-top: 1rem;
    margin-bottom: .5rem;
  }

  .scrolled-activity {
    display: flex;
    flex-direction: column;

    height: 10rem;
    background-color: var(--secondary-color);
    border: 2px solid var(--accent-color);
    border-radius: .25rem;
    padding: 0.5rem;
    overflow-y: auto;
    overflow-x: hidden;
    max-width: 14.75rem;
  }

  .activity-two {
    display: flex;
    background-color: var(--secondary-color);
    padding: .25rem;
    padding-top: .75rem;
    border-radius: .25rem;
    border: 2px solid var(--accent-color); 
  }

  .submit-button {
    display: inline-flex;
    justify-content: center;
    writing-mode: vertical-lr;
    padding: .75rem;
    padding-left: 1rem;
    padding-right: 1rem;
    border-left: 2px solid var(--accent-color);
  }

  .submit-button button {
    width: 2rem;
    height: 8rem;
    border: 0;
    border-radius: .25rem;
    background-color: var(--accent-color);
    font-size: 1rem;
    font-weight: bold;
  }

  .submit-button button:hover {
    background-color: var(--hover-color);
  }

  .inputs {
    display: inline-flex;
    flex-direction: column;
    margin-right: 1rem;
    margin-left: 1rem;
  }

  .activity-description-input input{
    width: 9rem;
    padding-bottom: 6rem;
  }

  .activity-title-input input{
    width: 7rem;
    padding-bottom: .1rem;
  }

</style>