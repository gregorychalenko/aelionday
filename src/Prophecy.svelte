<script>
    import { slide } from 'svelte/transition';
    export let text;
    export let great = false;
    export let pvp = false;
    export let place = '';
    export let note = '';
</script>

<li class:great class:pvp={ pvp } transition:slide>
    <h4>{ place }</h4>
    <div class="text">{ text }</div>
    {#if note }
    <small>Note: { note }</small>
    {/if}
</li>

<style>
li {
    list-style-type: none;
    margin: 1.5em 0;
    color: rgb(40, 52, 77);
}

h4 {
    color: gray;
    padding: 0;
    margin: 0;
    font-weight: lighter;
}

li.great {
    color: blueviolet;
}

li.pvp h4::after {
    content: 'pvp';
    background-color: gold;
    padding: 0 0.3em;
    margin-left: 0.3em;
    font-size: x-small;
    vertical-align: super;
}
</style>