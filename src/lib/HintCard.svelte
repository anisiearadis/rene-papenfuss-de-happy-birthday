<script>
    import * as shared from "../shared";
</script>

<div class="hint-card position-relative mb-3">
    <div class="position-absolute top-50 start-50 translate-middle w-100">
        <div class="d-flex flex-column">
            <h1 class="text-center text-nowrap mb-4">#0: {shared.codes[0]}</h1>
            <span class="text-center fw-bold">Büro</span>
            <span class="text-center px-4">Manchmal müssen Pflanzen angehoben werden.</span>
        </div>
    </div>
</div>

<style lang="scss">
  @use "sass:math";

  $hint-card-background-color: #c79865;
  $hint-card-border-radius: 30px;
  $hint-card-padding: 30px;
  $hint-card-width: 100%;

  $hint-card-padding-bottom: math.div($hint-card-width, 1.414);

  .hint-card {
    background-color: $hint-card-background-color;
    border-radius: $hint-card-border-radius;
    padding-bottom: $hint-card-padding-bottom;
    width: $hint-card-width;
  }
</style>