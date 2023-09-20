<script>
  async function fetchData() {
    const response = await fetch("https://randomuser.me/api/?results=3");
    return (await response.json()).results;
  }
</script>

{#await fetchData()}
  <p>Fetching users...</p>
{:then users}
  <ul>
    {#each users as user}
      <li>
        <img src={user.picture.thumbnail} alt="user" />
        <p>
          {user.name.first}
          {user.name.last}
        </p>
      </li>
    {/each}
  </ul>
{:catch}
  <p>An error occurred while fetching users</p>
{/await}
