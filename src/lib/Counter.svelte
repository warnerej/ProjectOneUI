<script>
  let count = $state(0)
  let hoursStudied = $state(0)
  let dateEntry = $state(new Date())

  const increment = () => {
    if (count < 24){
      count += 1
    }
  }
  const decrement = () => {
    if (count > 0){
      count -= 1
    }
  }
  const saveActivity = () => {
    hoursStudied = count;
    console.log(hoursStudied)
    dateEntry = selectedDate;
    console.log(dateEntry)

    console.log(`You have studied ${count} hours on ${selectedDate}`)
  }

  import { DateInput } from 'date-picker-svelte';
  let selectedDate = $state(new Date()); // Initialize with a default date
</script>

<div class ="activity-one">
  <div class="hour-date">
    <div class="hour-wrapper">
      <div class="hour-title">Select Hours:</div>
      <div class="hour-counter">
        <div class="hour-count">{count}</div>
        <div class="hour-buttons">
          <button onclick={increment}>▲</button>
          <button onclick={decrement}>▼</button>
        </div>
      </div>
    </div>

    <div class="date-wrapper">
      <div class="date-title">Select Date</div>
      <DateInput bind:value={selectedDate} />
    </div>
  </div>

  <div class="submit-button">
    <button onclick={saveActivity}>Submit</button>
  </div>

</div>


<style>

  /* Activity */
  .activity-one {
    display: flex;
    background-color: var(--secondary-color);
    padding: .25rem;
    padding-bottom: .4rem;
    border: 2px solid var(--accent-color);
    border-radius: .25rem;
  }
  /* Activity End*/

  /* Hour Date */
  .hour-date {
    display: inline-flex;
    flex-direction: column;
    margin-right: 1rem;
    padding-left: 1rem;
  }
  /* Hour Date*/

  /* Submit */
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
  /* Submit End */
    
  /* Counter */
  .hour-wrapper {
    display: inline-flex;
    flex-direction: column;
    padding: .5rem;
  }

  .hour-title {
    display: flex;
    flex-direction: column;
    color: var(--accent-color);
    font-weight: bold;
    text-decoration: underline;
  }

  .hour-counter {
    display: inline-flex;
    align-items: center;
    padding: 0.25rem;
    border-radius: .25rem;
    background-color: var(--secondary-color);
  }

  .hour-count {
    padding: 0 0.5rem;
    min-width: 2rem;
    text-align: center;
    color: var(--accent-color);
    font-size: 2rem;
    font-weight: bold;
  }

  .hour-buttons {
    display: flex;
    flex-direction: column;
  }

  .hour-buttons button {
    width: 4rem;
    height: 1.5rem;
    padding: 0;
    margin: .2vw;
    font-size: 0.8rem;
    background-color: var(--accent-color);
    border-radius: .25rem;
    border: 0px;
  }

  .hour-buttons button:hover {
    background-color: var(--hover-color);
  }
  /* Counter End*/

  /* Date Selection */
  .date-wrapper {
    display: inline-flex;
    flex-direction: column;
    padding: .25rem;
    border-radius: .25rem;
    background-color: var(--secondary-color);
  }

  .date-title {
    color: var(--accent-color);
    font-weight: bold;
    text-decoration: underline;
    padding-bottom: .25rem;
  }
  /*Date Selection Ends*/
</style>