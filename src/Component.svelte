<script>
  import { getContext } from "svelte";
  import { Label, Layout, ModalContent, Modal } from "@budibase/bbui";

  export let titre = "Nouveau titre";
  export let btOk = "Ok";
  export let btAnnule = "Annuler";
  export let clickFermer;
  export let clickAnnuler;
  export let clickOk;
  export let styleBtOk = "overBackground";
  export let styleBtAnnule = "overBackground";
  export let isFooter = true;
  export let colorHeader = "#000";
  export let sizeButton = "M";

  const { styleable } = getContext("sdk");
  const component = getContext("component");
</script>

<div use:styleable={$component.styles} class="jta_container">
  <div class="jta_header" style="border-bottom: 1px solid {colorHeader}">
    <div>
      <h2 style="color:{colorHeader};">{titre}</h2>
    </div>
    <div class="jta_close">
      <i
        class="ri-close-line ri-xl svelte-1ghy1wa"
        draggable="true"
        style="color: {colorHeader};"
        on:click={clickFermer}
        on:keydown={clickFermer}
      />
    </div>
  </div>
  <div class="jta_travail">
    <!-- Contenu du travail ici -->
    <slot />
  </div>

  {#if isFooter}
    <div class="jta_footer">
      <button
        class:spectrum-Button--cta={styleBtAnnule == "cta"}
        class:spectrum-Button--primary={styleBtAnnule == "primary"}
        class:spectrum-Button--secondary={styleBtAnnule == "secondary"}
        class:spectrum-Button--warning={styleBtAnnule == "warning"}
        class:spectrum-Button--overBackground={styleBtAnnule ==
          "overBackground"}
        class="spectrum-Button spectrum-Button--size{sizeButton}"
        on:click={clickAnnuler}>{btAnnule}</button
      >
      <button
        class:spectrum-Button--cta={styleBtOk == "cta"}
        class:spectrum-Button--primary={styleBtOk == "primary"}
        class:spectrum-Button--secondary={styleBtOk == "secondary"}
        class:spectrum-Button--warning={styleBtOk == "warning"}
        class:spectrum-Button--overBackground={styleBtOk == "overBackground"}
        class="spectrum-Button spectrum-Button--size{sizeButton}"
        on:click={clickOk}>{btOk}</button
      >
    </div>
  {/if}
</div>

<style>
  .jta_container {
    display: flex;
    flex-direction: column;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    z-index: 11111;
  }

  .jta_header {
    padding: 10px;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .jta_header h2 {
    margin: 0;
    font-family: var(--font-accent);
    font-weight: 600;
  }

  .jta_header .jta_close {
    cursor: pointer;
  }

  .jta_travail {
    flex-grow: 1;
    padding: 10px;
    overflow: auto;
    overflow-x: hidden;
  }

  .jta_footer {
    padding: 10px;
    display: flex;
    justify-content: flex-end; /* Aligner les éléments à droite */
  }

  .jta_footer button {
    margin-left: 10px; /* Marge entre les boutons */
  }
</style>
