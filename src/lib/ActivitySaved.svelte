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
  }

  .activity-title {
    text-decoration: underline;
    font-weight: bold;
    border-top: 2px solid var(--accent-color);
  }

  .activity-description {
    border-bottom: 2px solid var(--accent-color);
  }
</style>