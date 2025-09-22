<script>
  const saveActivity = () => {
    console.log("This was clicked")
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
    <textarea placeholder="Input your goal"></textarea>
  </div>

  <div class="submit-button">
    <button onclick={saveActivity}>Submit</button>
  </div>
</div>

<style>
  .activity-three {
    display: flex;
    background-color: var(--secondary-color);
    border-radius: .25rem;
    border: 2px solid var(--accent-color); 
    padding: .5rem;
    justify-content: center;
  }

  .goal-title {
    color: var(--accent-color);
    font-weight: bold;
    text-decoration: underline;
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