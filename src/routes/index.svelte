<script>
    let name=""
    let age=""
    let description=""
    async function getAge() {
        fetch('https://api.agify.io/?name='+ name)
        .then((response) => response.json())
        .then((data) => {
  	name = data.name; // Path for temperature
  	age = data.age; // Path for description
	});
}
</script>

<h1>Guess age</h1>

<form on:submit|preventDefault={getAge}>
    <label for="location">Name:</label>
    <input id="location" bind:value={name} type="text" />
    <button type="submit">Check</button>
</form>
<p>Age: {age}</p>
