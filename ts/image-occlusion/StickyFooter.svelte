<!--
Copyright: Ankitects Pty Ltd and contributors
License: GNU AGPL, version 3 or later; http://www.gnu.org/licenses/agpl.html
-->
<script lang="ts">
    import * as tr from "@tslib/ftl";

    import ButtonGroup from "../components/ButtonGroup.svelte";
    import LabelButton from "../components/LabelButton.svelte";

    export let hideAllGuessOne: () => void;
    export let hideOneGuessOne: () => void;
    export let editing: boolean;
</script>

<div style:flex-grow="1" />
<div class="sticky-footer">
    {#if editing}
        <div class="update-note-text">
            {tr.actionsUpdateNote()}
        </div>
    {/if}
    <ButtonGroup size={2}>
        <LabelButton
            --border-left-radius="5px"
            --border-right-radius="5px"
            on:click={hideAllGuessOne}
            class=" bottom-btn"
        >
            {tr.notetypesHideAllGuessOne()}
        </LabelButton>
        <LabelButton
            --border-left-radius="5px"
            --border-right-radius="5px"
            on:click={hideOneGuessOne}
            class=" bottom-btn"
        >
            {tr.notetypesHideOneGuessOne()}
        </LabelButton>
    </ButtonGroup>
</div>

<style lang="scss">
    .sticky-footer {
        position: fixed;
        bottom: 0;
        left: 0;
        right: 0;
        z-index: 99;
        margin: 0;
        padding: 0.25rem;
        background: var(--canvas);
        border-style: solid none none;
        border-color: var(--border);
        border-width: thin;
        display: flex;
        justify-content: flex-end;
    }
    :global(.bottom-btn) {
        margin: 2px;
    }

    :global(.update-note-text) {
        align-self: center;
        padding-right: 20px;
    }
</style>
