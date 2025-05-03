# Bb-component-SuperProgressBar

This is a readme for your new Budibase plugin.

# Description

A Progress Bar component for Budibase, built with Adobe Spectrum CSS for a sleek, accessible design. Displays progress with customizable options for label, value, color, and size.

Find out more about [Budibase](https://github.com/Budibase/budibase).

## Features

- **Customizable Display**: Choose between percentage, raw value, or progress (value/max) formats.
- **Indeterminate State**: Animated loading state when value is empty.
- **Styling Options**: Supports small, medium, and large sizes per Adobe Spectrum guidelines.
- **Value Formatting**: Add prefixes, suffixes, and control decimal places for displayed values.

## Settings

- **Label**: Text to display above the progress bar (left side).
- **Value**: Current progress value.
- **Max Value**: Maximum value for the progress range.
- **Min Value**: Minimum value for the progress range.
- **Color**: Progress bar fill color.
- **Type**: Display format - `percentage`, `value`, or `progress`.
- **Value Prefix**: Text to prepend to the value.
- **Value Suffix**: Text to append to the value.
- **Size**: Bar size - `s` (small), `m` (medium), `l` (large).
- **Decimals**: Number of decimal places for the displayed value.

## Instructions

To build your new plugin, run the following in your Budibase CLI:

```
budi plugins --build
```

You can also re-build every time you make a change to your plugin with the command:

```
budi plugins --watch
```
