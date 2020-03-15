<script>

let parsedUrl = new URL(window.location.toString());
let title = parsedUrl.searchParams.get('title');
let text = parsedUrl.searchParams.get('text');
let url = parsedUrl.searchParams.get('url');

console.log('Title shared: ' + title);
console.log('Text shared: ' + text);
console.log('URL shared: ' + url);

let imdbUrl = "https://www.imdb.com/find?q=fnord#tt";
</script>

<h3>Share</h3>

<div>location: {parsedUrl}</div>

<hr/>

<div>Title: {title}</div>
<div>Description: {text}</div>
<div>URL: {url}</div>

<a href="{imdbUrl}">go to IMDB</a>
