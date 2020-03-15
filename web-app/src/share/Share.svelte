<script>

let parsedUrl = new URL(window.location.toString());
let title = parsedUrl.searchParams.get('title');
let text = parsedUrl.searchParams.get('text');
let url = parsedUrl.searchParams.get('url');


// HACK
text = 'Seen "Dirty Money" on Netflix yet? https://www.netflix.com/title/123123?s=a&trkid=2&t=more';

const regex = /\"(.*)\"/;
const found = text.match(regex);
let movieTitle = found[1];
console.log("regex match", found);
console.log("movieTitle", movieTitle)

var movieTitleEncoded = encodeURI(movieTitle);

let imdbUrl = "https://www.imdb.com/find?q="+movieTitleEncoded+"#tt";
</script>

<h3>Share</h3>

<div>location: {parsedUrl}</div>

<hr/>

<div>Title: {title}</div>
<div>Description: {text}</div>
<div>URL: {url}</div>

<hr/>

<a href="{imdbUrl}">go to IMDB</a> ({imdbUrl})
