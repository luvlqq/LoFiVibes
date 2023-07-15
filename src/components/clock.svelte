<script>
    import { onMount } from "svelte";
    import { onDestroy } from "svelte";

    let today = "";
    let time = "";

    function updateTime() {
        const date = new Date();
        today = date.toLocaleDateString();
        time = date.toLocaleTimeString();
    }

    onMount(() => {
        updateTime();
        const interval = setInterval(updateTime, 1000);

        onDestroy(() => {
            clearInterval(interval);
        });
    });
</script>

<div class="hero flex items-center justify-center main">
    <div class="hero-content text-center text-black">
        <div class="text-center">
            <div class="text-5xl text-white outline-none">
                {today}
            </div>
            <div class="text-6xl text-white font-bold outline-none">
                {time}
            </div>
        </div>
    </div>
</div>


<style>
    .main {
        height: 100vh;
        display: grid;
        font-weight: 400;
    }
</style>