---
title: 'Code'
order: 2
---

## Import

```css
@import 'settings-tools/_all-settings';
@import 'components/_c.toggle';
```

## Basic usage

Wrap a `input[type="checkbox"]` and a `label` inside a `div` and apply the following classes :

```html
<div class="mc-toggle">
  <input class="mc-toggle__input" id="toggle3" type="checkbox" />
  <label class="mc-toggle__label" for="toggle3">
    Label
  </label>
</div>
```

<preview path="src/pages/Components/Toggle/previews/ToggleBase"></preview>

## Sizes

- **small** : `mc-toggle--s`
- **medium** : (default)

<preview path="src/pages/Components/Toggle/previews/ToggleSizes"></preview>

## States

- On
- off
- focus
- on disabled
- off disabled

<preview path="src/pages/Components/Toggle/previews/ToggleStates"></preview>

### Displaying on/off states in labels

In order to add on/off states to the labels, add the following code :

```html
<span class="mc-toggle__state" aria-hidden="true">
  <span class="mc-toggle__off">Off</span>
  <span class="mc-toggle__on">On</span>
</span>
```

Inside the label after you text :

```html
<div class="mc-toggle">
  <input class="mc-toggle__input" id="toggle3" type="checkbox" />
  <label class="mc-toggle__label" for="toggle3" aria-label="example toggle 4">
    My option :
    <span class="mc-toggle__state" aria-hidden="true">
      <span class="mc-toggle__off">Off</span>
      <span class="mc-toggle__on">On</span>
    </span>
  </label>
</div>
```

Don't forget to add the `aria-hidden="true"` attribute on the `mc-toggle__state` element

<preview path="src/pages/Components/Toggle/previews/ToggleStatesLabel"></preview>

## Responsive behaviors

### Responsive size classes

| breakpoint                    | `mc-toggle--s`          | `mc-toggle--m`          |
| ----------------------------- | ----------------------- | ----------------------- |
| From breakpoint s (all sizes) | `mc-toggle--s`          | default                 |
| From breakpoint m             | `mc-toggle--s@from-m`   | `mc-toggle--m@from-m`   |
| From breakpoint l             | `mc-toggle--s@from-l`   | `mc-toggle--m@from-l`   |
| From breakpoint xl            | `mc-toggle--s@from-xl`  | `mc-toggle--m@from-xl`  |
| From breakpoint xxl           | `mc-toggle--s@from-xxl` | `mc-toggle--m@from-xxl` |

## Extension and customization

### Adding a toggle size

If you want to add a toggle size, update the `$toggle-sizes` map after the `all-settings` import, then import your toggles
example :

```scss
@import 'settings/all-settings';
$toggle-sizes: map-merge(
  $toggle-sizes,
  (
    'xs': (
      'width': 2,
      'height': 1,
    ),
    'l': (
      'width': 6,
      'height': 3,
    ),
  )
);

@import 'components/_c.toggles';
```

<preview path="src/pages/Components/Toggle/previews/ToggleExtendSizes"></preview>