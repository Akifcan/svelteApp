<script type="text/javascript">

	let name = ''
	let author = ''

	let songs = [
		{
			name: 'Good Vibe',
			author: 'Jfla'
		},
		{
			name: 'Different World',
			author: 'Alan Walker'
		},
		{
			name: 'City of stars',
			author: 'La la land'
		},
		{
			name: 'High hopes',
			author: 'Panic! At The Disco'
		}
	]

	function clearInputs(){
		name = ''
		author = ''
	}

	function addToSongList(){
		songs = [...songs, {name: name, author: author}]
		clearInputs()
	}


</script>

<div class="container">
	<ul class="list-group">
		{#each songs as song}
			<li class="list-group-item">{song.name} <b class="float-right">{song.author}</b> </li>
		{/each}
	</ul>

	<form class="mt-2" on:submit|preventDefault={addToSongList}>
		<input type="text" class="form-control" bind:value={name} placeholder="Song Name">
		<input type="text" class="form-control" bind:value={author} placeholder="Author">
		<button class="btn btn-outline-primary btn-block" disabled={name=='' | author == ''}>Add</button>
	</form>

</div>
