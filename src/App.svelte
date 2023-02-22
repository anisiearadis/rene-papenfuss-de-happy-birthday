<script>
    import BirthdayCard from "./lib/BirthdayCard.svelte";
    import TimerWall from "./lib/TimerWall.svelte";
    import MobileNotification from "./lib/MobileNotification.svelte";

    let done = false;

    function handleFinishEvent() {
        done = true;
    }

    function format(value, singular, plural) {
        if (value === 1) {
            return `${value} ${singular}`;
        }

        return `${value} ${plural}`;
    }
</script>

<div class="d-flex flex-column justify-content-center align-items-center min-vw-100 min-vh-100 position-relative">
    {#if done}
        <MobileNotification/>
        <BirthdayCard/>
    {:else}
        <TimerWall end="2023-02-22T19:00:00+0100" let:remaining on:finish={handleFinishEvent}>
            <h1 class="position-absolute top-0 start-0 vw-100 vh-100 bg-black text-white d-flex flex-column justify-content-center align-items-center">
                {#if remaining.done === false}
                    <span class="mb-3">Warte noch</span>
                    <span>{format(remaining.hours, 'Stunde', 'Stunden')}</span>
                    <span>{format(remaining.minutes, 'Minute', 'Minuten')}</span>
                    <span>{format(remaining.seconds, 'Sekunde', 'Sekunden')}</span>
                    <span class="mt-3">bis es weiter geht.</span>
                {/if}
            </h1>
        </TimerWall>
    {/if}
</div>
