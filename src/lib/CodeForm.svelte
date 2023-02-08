<script>
    import * as shared from "../shared";

    export let formWasValid;

    const codes = shared.codes;

    let form;

    const enteredCodes = [
        {
            erroneous: false,
        },
        {
            erroneous: false,
        },
        {
            erroneous: false,
        },
        {
            erroneous: false,
        },
        {
            erroneous: false,
        },
        {
            erroneous: false,
        },
        {
            erroneous: false,
        },
    ];

    let wasValidated = false;

    function validate(event) {
        // disable all default events
        event.preventDefault();
        event.stopPropagation();

        // convert form data to object
        let data = [...new FormData(event.target)].reduce((o, [k, v]) => {
            o[k] = v;
            return o;
        }, {});

        // convert form data object to array
        data = Object.values(data);

        // iterate the given data and check if they match with the valid codes
        data.forEach((value, index) => {
            enteredCodes[index].erroneous = value !== codes[index];
        });

        // check that we validated the entries
        wasValidated = true;

        // check if all codes are valid
        if (!enteredCodes.every(element => element.erroneous === false)) return;

        // call the form callback
        formWasValid();
    }
</script>

<div class="code-form">
    <form on:submit|preventDefault={validate} novalidate>
        {#each codes as code, idx}
            <div class="mb-1 row">
                <label for="code-{idx}" class="col-4 col-form-label">Code #{idx}:</label>
                <div class="col-8 has-validation">
                    <input type="text" class="form-control" name="code-{idx}" id="code-{idx}" required
                           class:is-invalid={wasValidated && enteredCodes[idx].erroneous === true}
                           class:is-valid={wasValidated && enteredCodes[idx].erroneous === false}>
                </div>
            </div>
        {/each}
        <hr>
        <div class="mb-1 row">
            <div class="col-4"></div>
            <div class="col-8">
                <button type="submit" class="btn btn-primary w-100">Überprüfen</button>
            </div>
        </div>
    </form>
</div>



