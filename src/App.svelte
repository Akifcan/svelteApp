<script type="text/javascript">

	let name = null
	let author = null

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


</script>

<div class="container">
	<ul class="list-group">
		{#each songs as song}
			<li class="list-group-item">{song.name} <b class="float-right">{song.author}</b> </li>
		{/each}
	</ul>
</div>
