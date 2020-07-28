<script>
import Button, {Label, Icon} from '@smui/button';

export let debug = false;   // passed from outside
export let shareText = "";  // passed from outside
if (debug) {
  shareText = 'Seen "The Equalizer" on Netflix yet?\n'
            + 'https://www.imdb.com/title/70305892?s=a&trkid=123225&t=more'
}

let movieTitle = "";

let openIMDB = () => {
    let movieTitleEncoded = encodeURI(movieTitle);
    window.location = "https://m.imdb.com/find?q="+movieTitleEncoded+"#tt";
};


if (shareText) {
    shareText = decodeURI(shareText);

    const regex = /\"(.*)\"/;
    const found = shareText.match(regex);
    if (found) {
        movieTitle = found[1];
        if (!debug) {
          openIMDB();
        }
    }
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
