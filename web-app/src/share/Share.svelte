<script>
import Button, {Label, Icon} from '@smui/button';


let parsedUrl = new URL(window.location.toString());
//let title = parsedUrl.searchParams.get('title');
let text = parsedUrl.searchParams.get('text');
//let url = parsedUrl.searchParams.get('url');

const regex = /\"(.*)\"/;
const found = text.match(regex);
let movieTitle = found[1];


let openIMDB = () => {
    let movieTitleEncoded = encodeURI(movieTitle);
    let imdbUrl = "https://www.imdb.com/find?q="+movieTitleEncoded+"#tt";
    window.location = imdbUrl;
}

</script>

<div class="description-box">
    <h3 class="h3-title">Shared</h3>
    <p class="text">{text}</p>
</div>

<div class="movie-box">
    <h3 class="h3-title">Movie title</h3>
    <p class="text">{movieTitle}</p>
</div>

<br/>
<br/>

<Button on:click={openIMDB} variant="unelevated" style="width: 100%;">
    <Label>
        Search IMDB
    </Label>
</Button>


<style>
.description-box { }
.h3-title {
	color: #999;
}
.text {
	
}
</style>