<script>
  let count = $state(0)
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
</script>

<button onclick={increment}>
  +
</button>
<div id="count">
  Hours Studied: {count}
</div>
<button onclick={decrement}>
  -
</button>