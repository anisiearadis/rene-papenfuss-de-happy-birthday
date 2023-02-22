<script>
    import Lightbox from 'bs5-lightbox';

    export let thumbnailUrl;
    export let originalUrl;
    export let caption;

    function foo(event) {
        event.preventDefault();

        new Lightbox(event.target).show();
    }
</script>

<div on:click|preventDefault|stopPropagation={foo}>
    <img src="{thumbnailUrl}" data-toggle="lightbox" data-remote="{originalUrl}" class="img-thumbnail img-fluid" data-caption="{caption}">
</div>
