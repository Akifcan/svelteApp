<script type="text/javascript">

	let name = ''
	let author = ''
	let status = null

	$: songsLength = songs.length

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

	function showMessage(type, message){
		return `<div class='alert alert-${type}'>${message}</div>`
	}

	function clearInputs(){
		name = ''
		author = ''
	}

	function addToSongList(){
		if(songsLength<5){
			songs = [...songs, {name: name, author: author}]
			clearInputs()
			status = 'success'
		}else{
			status = 'error'
			clearInputs()
		}
		setTimeout(() => {
			status = null
		}, 2000)
	}


</script>

<div class="container">
	{songsLength}
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

	{#if status}
		{#if status == 'success'}
			{@html showMessage('success', 'song added successfully')}
			{:else}
			{@html showMessage('danger', 'you can only add 5 song')}
		{/if}	
	{/if}

</div>
