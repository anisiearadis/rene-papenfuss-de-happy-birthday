<script>
    import {createEventDispatcher, onMount} from "svelte"
    import {intervalToDuration, isAfter, isEqual, parseISO} from "date-fns";
    export let end;

    let remaining = {
        years: 0,
        months: 0,
        days: 0,
        hours: 0,
        minutes: 0,
        seconds: 0,
        done: false,
    };

    const dispatch = createEventDispatcher();

    let timer;

    onMount(() => {
        end = parseISO(end);

        timer = setInterval(() => {
            const start = new Date();

            remaining = Object.assign({}, intervalToDuration({
                start,
                end,
            }), {done: false});

            if (isEqual(start, end) || isAfter(start, end)) {
                remaining.done = true;
                clearInterval(timer);

                dispatch('finish', {
                    text: 'Hello!'
                });
            }
        }, 1000);
    });
</script>

<slot {remaining}></slot>
