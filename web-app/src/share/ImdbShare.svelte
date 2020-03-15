<script>
import Button, {Label, Icon} from '@smui/button';

export let shareText = null; // passed from outside
let movieTitle = "";

if (shareText) {
    const regex = /\"(.*)\"/;
    const found = shareText.match(regex);
    if (found) {
        movieTitle = found[1];
    }
}

let openIMDB = () => {
    let movieTitleEncoded = encodeURI(movieTitle);
    let imdbUrl = "https://www.imdb.com/find?q="+movieTitleEncoded+"#tt";
    window.location = imdbUrl;
}

</script>

<div class="description-box">
    <h3 class="h3-title">Shared</h3>
    <p class="text">{shareText}</p>
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