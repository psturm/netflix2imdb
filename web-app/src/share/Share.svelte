<script>
import Button, {Label, Icon} from '@smui/button';
import ImdbShare from './ImdbShare.svelte';

let parsedUrl = new URL(window.location.toString());
let text = parsedUrl.searchParams.get('text');
let debug = parsedUrl.searchParams.has('debug');
</script>


{#if text}
	<ImdbShare shareText="{text}" debug="{debug}"/>
{:else}
	<h3>No share found!</h3>

    <p>
        This app only works as a "share target" for Netflix app.
    </p>
    <ol>
            <li>Install this app to "Home screen"</li>
            <li>Click "share" in your Netflix app</li>
            <li>Select this app as share target</li>
            <li>It will display the IMDB search for this movie</li>
        </ol>
{/if}
