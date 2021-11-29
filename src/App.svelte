<script>
	import FeedbackList from './components/FeedbackList.svelte';
	let feedback = [
		{
			id: '1',
			rating: 10,
			text: "uvslyfsibf guslfvs sigfuivsb text one uvslyfsibf guslfvs sigfuivsb text one uvslyfsibf guslfvs sigfuivsb text one"
		},
		{
			id: '2',
			rating: 9,
			text: "uvslyfsibf guslfvs sigfuivsb text two uvslyfsibf guslfvs sigfuivsb text one uvslyfsibf guslfvs sigfuivsb text one"
		}, 
		{
			id: '3',
			rating: 2,
			text: "uvslyfsibf guslfvs sigfuivsb text three uvslyfsibf guslfvs sigfuivsb text one uvslyfsibf guslfvs sigfuivsb text one"
		}
]

$: count = feedback.length;
$: average = feedback.reduce((a, {rating}) => a + rating, 0 ) / feedback.length
const deleteFeedback = (e) => {
	const itemId = e.detail;
	feedback = feedback.filter((item) => item.id != itemId)
}
</script>

<main>
	<div class='container'>
		<FeedbackList feedback={feedback} on:delete-feedback={deleteFeedback}/>
	</div>
</main>

<style>
main {
	background-color: #a4a4a4;
	height: 100vh;
	display: flex;
	justify-content: center;
	align-items: center;
}
</style>