<script>
  const saveActivity = () => {
    console.log("This was clicked")
  }
</script>

<div class="activity-three">
  <div class="checkboxes">
    <label id="good">
      <input type="checkbox" />
        Good
    </label>

    <label id="okay">
      <input type="checkbox" />
        Okay
    </label>

    <label id="bad">
      <input type="checkbox" />
        Bad
    </label>

    <label id="not-Sure">
      <input type="checkbox" />
        Not Sure
    </label>
  </div>

  <div class="goal-input">
    <input type="text" placeholder="Input your goal"/>
  </div>

  <div class="submit-button">
    <button onclick={saveActivity}>Submit</button>
  </div>
</div>

<style>
  .activity-three {
    display: inline-flex;
    background-color: var(--secondary-color);
    padding: .25rem;
    padding-top: .75rem;
    border-radius: .25rem;
    border: 2px solid var(--accent-color); 

  }

  .checkboxes {
    justify-content: center;
    display: inline-flex;
    flex-direction: column;
    color: black;
    margin-bottom: .1rem;
  }

  .checkboxes label {
    margin: .1rem;
  }

  .goal-input {
    display: inline-flex;
    margin: 1rem;
  }

  .goal-input input{
    width: 8rem;
    padding-bottom: 6rem;
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


</style>