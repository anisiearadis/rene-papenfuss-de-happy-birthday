<script>
    import BirthdayCard from "./lib/BirthdayCard.svelte";
    import TimerWall from "./lib/TimerWall.svelte";

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
        <BirthdayCard/>
    {:else}
        <TimerWall to="2023-02-22T18:00:00+0100" let:remaining on:finish={handleFinishEvent}>
            <h1 class="position-absolute top-0 start-0 vw-100 vh-100 bg-black text-white d-flex justify-content-center align-items-center">
                {#if remaining.done === false}
                    {format(remaining.days, 'Tag', 'Tage')},
                    {format(remaining.hours, 'Stunde', 'Stunden')},
                    {format(remaining.minutes, 'Minute', 'Minuten')},
                    {format(remaining.seconds, 'Sekunde', 'Sekunden')}
                {:else}
                    <h2>The time has come!</h2>
                {/if}
            </h1>
        </TimerWall>
    {/if}
</div>
