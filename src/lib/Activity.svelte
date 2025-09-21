<script>
  const saveActivity = () => {
    console.log("This was clicked")
  }
</script>

<div class="activity-two">
  <div class="inputs">
    <div class="activity-title-input">
      <input type="text" placeholder="Activity Title"/>
    </div>
    <div class="activity-description-input">
        <input type="text" placeholder="Activity Description"/>
    </div>
  </div>
  <div class="submit-button">
    <button onclick={saveActivity}>Submit</button>
  </div>
</div>


<style>
  input::placeholder {
    text-align: left;
    padding-top: 5px;
  }

  .activity-two {
    display: inline-flex;
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