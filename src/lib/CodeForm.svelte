<script>
    import {marked} from "marked";
    import * as shared from "../shared";

    const codes = shared.codes;
</script>

<div class="code-form">
    <form>
        {#each codes as code, idx}
            <div class="mb-1 row">
                <label for="code-{idx}" class="col-4 col-form-label">Code #{idx}:</label>
                <div class="col-8">
                    <input type="text" class="form-control" id="code-{idx}">
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

<style lang="scss">

</style>
