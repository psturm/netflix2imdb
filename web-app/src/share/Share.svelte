<script>

var parsedUrl = new URL(window.location.toString());
console.log('Title shared: ' + parsedUrl.searchParams.get('name'));
console.log('Text shared: ' + parsedUrl.searchParams.get('description'));
console.log('URL shared: ' + parsedUrl.searchParams.get('link'));
</script>

<h3>Share ?</h3>