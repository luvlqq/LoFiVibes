<script>
    import { onMount } from 'svelte';

    let volume = 0.5;
    let audio;

    function decreaseVolume() {
        if (audio) {
            audio.volume = volume;
            audio.play();
        }
    }

    onMount(() => {
        audio = new Audio();
    });
</script>


<div class="video-container">
    <iframe src="https://www.youtube.com/embed/jfKfPfyJRdk?autoplay=1&controls=0"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; web-share"
            allowfullscreen>
    </iframe>
</div>

<style>
    .video-container {
        position: relative;
        width: 0;
        height: 0;
        overflow: hidden;
    }

    .video-container iframe {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        opacity: 0;
    }
</style>