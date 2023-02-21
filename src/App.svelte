<script>
    import BirthdayCard from "./lib/BirthdayCard.svelte";
    import TimerWall from "./lib/TimerWall.svelte";

    let done = false;

    function handleFinishEvent() {
        done = true;
    }
</script>

<div class="d-flex flex-column justify-content-center align-items-center min-vw-100 min-vh-100 position-relative">
    {#if done}
        <BirthdayCard/>
    {:else}
        <TimerWall to="2023-02-21T15:35:00+0100" let:remaining on:finish={handleFinishEvent}>
            <div class="position-absolute top-0 start-0 vw-100 vh-100 bg-black text-white">
                {#if remaining.done === false}
                    <span>{remaining.days} Tage</span>
                    <span>{remaining.hours} Stunden</span>
                    <span>{remaining.minutes} Minuten</span>
                    <span>{remaining.seconds} Sekunden</span>
                {:else}
                    <h2>The time has come!</h2>
                {/if}
            </div>
        </TimerWall>
    {/if}
</div>
