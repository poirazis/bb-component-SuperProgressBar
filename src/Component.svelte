<script>
  import { getContext } from "svelte";

  export let label = "Loading...";
  export let value = null;
  export let min = 0;
  export let max = 100;
  export let color = "var(--spectrum-global-color-green-600)";
  export let trackColor = "var(--spectrum-global-color-gray-200)";
  export let type = "percentage";
  export let valuePrefix = "";
  export let valueSuffix = "";
  export let size = "m";
  export let decimals = 0;

  const { styleable } = getContext("sdk");
  const component = getContext("component");

  $: percentage =
    value !== null && value !== "" ? ((value - min) / (max - min)) * 100 : null;
  $: isIndeterminate = value === null || value === "";
  $: formattedValue =
    value !== null && value !== "" ? Number(value).toFixed(decimals) : value;
  $: formattedPercentage =
    percentage !== null ? percentage.toFixed(decimals) : percentage;
  $: displayValue =
    type === "percentage"
      ? `${formattedPercentage}%`
      : type === "progress"
        ? `${valuePrefix}${formattedValue} / ${max}${valueSuffix}`
        : `${valuePrefix}${formattedValue}${valueSuffix}`;

  $: effectiveColor = color
    ? color
    : isIndeterminate
      ? "var(--spectrum-global-color-blue-500)"
      : "var(--spectrum-global-color-green-600)";
</script>

<div use:styleable={$component.styles}>
  <div
    class="spectrum-ProgressBar spectrum-ProgressBar--overBackground"
    class:spectrum-ProgressBar--sizeS={size === "s"}
    class:spectrum-ProgressBar--sizeM={size === "m"}
    class:spectrum-ProgressBar--sizeL={size === "l"}
    class:spectrum-ProgressBar--indeterminate={isIndeterminate}
    role="progressbar"
    aria-valuenow={isIndeterminate ? null : value}
    aria-valuemin={min}
    aria-valuemax={max}
    aria-label={label}
  >
    <div
      class="spectrum-FieldLabel spectrum-ProgressBar-label"
      class:spectrum-FieldLabel--sizeS={size === "s"}
      class:spectrum-FieldLabel--sizeM={size === "m"}
      class:spectrum-FieldLabel--sizeL={size === "l"}
    >
      {label}
    </div>
    {#if !isIndeterminate}
      <div
        class="spectrum-FieldLabel spectrum-ProgressBar-value"
        class:spectrum-FieldLabel--sizeS={size === "s"}
        class:spectrum-FieldLabel--sizeM={size === "m"}
        class:spectrum-FieldLabel--sizeL={size === "l"}
      >
        {displayValue}
      </div>
    {/if}
    <div
      class="spectrum-ProgressBar-track"
      style:--track-color={trackColor ||
        "var(--spectrum-global-color-gray-200)"}
    >
      <div
        class="spectrum-ProgressBar-fill"
        style={isIndeterminate
          ? `background: linear-gradient(to right, transparent 0%, ${effectiveColor} 50%, transparent 100%) !important;`
          : `width: ${percentage}%; background-color: ${effectiveColor} !important;`}
      ></div>
    </div>
  </div>
</div>

<style>
  .spectrum-ProgressBar {
    display: grid !important;
    grid-template-areas:
      "label . value"
      "track track track" !important;
    grid-template-columns: auto 1fr auto !important;
    width: 100% !important;
  }

  .spectrum-ProgressBar-label,
  .spectrum-ProgressBar-value {
    font-weight: 400 !important;
    color: var(--spectrum-global-color-gray-800) !important;
  }

  .spectrum-FieldLabel--sizeS {
    font-size: 12px !important;
  }

  .spectrum-FieldLabel--sizeM {
    font-size: 13px !important;
  }

  .spectrum-FieldLabel--sizeL {
    font-size: 16px !important;
  }

  .spectrum-ProgressBar-label {
    grid-area: label !important;
  }

  .spectrum-ProgressBar-value {
    grid-area: value !important;
  }

  .spectrum-ProgressBar-track {
    grid-area: track !important;
    background-color: var(--track-color) !important;
    border-radius: 2px !important;
    overflow: hidden !important;
  }

  .spectrum-ProgressBar--sizeS .spectrum-ProgressBar-track {
    height: 4px !important;
  }

  .spectrum-ProgressBar--sizeM .spectrum-ProgressBar-track {
    height: 6px !important;
  }

  .spectrum-ProgressBar--sizeL .spectrum-ProgressBar-track {
    height: 8px !important;
  }

  .spectrum-ProgressBar-fill {
    height: 100% !important;
    border-radius: 2px !important;
    transition: width 0.2s ease-in-out !important;
    background-size: 200% 100% !important;
  }

  .spectrum-ProgressBar--indeterminate .spectrum-ProgressBar-fill {
    width: 100% !important;
    animation: indeterminate-loop-ltr 1.5s linear infinite !important;
  }

  @keyframes indeterminate-loop-ltr {
    0% {
      transform: translate(-150%);
    }
    to {
      transform: translate(150%);
    }
  }
</style>
