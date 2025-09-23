<script>
  const {title, description} = $props()
</script>

<div class="total">
  <div class="activity-title">
    {title}
  </div>
  <div class="activity-description">
    {description}
  </div>
</div>

<style>
  .total {
    display: flex;
    flex-direction: column;
    color: var(--accent-color);
    width: 100%;
    margin-bottom: 1rem;
    background-color: #cacaca;
    border-radius: .5rem;
    padding: .2rem;
  }

  .total:hover {
    background-color: #b4b4b4;
  }

  .activity-title {
    font-weight: bold;
  }

  .activity-description {
    font-size: .75rem;
  }
</style>