---
title: 'Code'
order: 2
---

##The margins and paddings utility classes

You can add to your bundle the margins or paggings utility classes like so :

```css
@import 'utilities/_u.margin.scss';
@import 'utilities/_u.padding.scss';
```

```html
<div class="mu-mb-100">
  I will have a 16px margin bottom
</div>
<div class="mu-pl-050">
  I will have a 8px padding left
</div>
```

Please considere that those utilities are looping through all magic-unit authorized values up to 10x magic-units (160px), and trought all possible sides (left, top, right, bottom).This is resulting in a lot of classes that you will potentialy not use.

**You may want to add your utilities one by one as you use them instead**. In that case, use the space mixin.

<br>

##The space mixin

You can implement your own margins or paggings utility using the space mixin :

```css
@import 'settings-tools/_all-settings.scss';

@include space-util(m, t, 075);
/*
.mu-mt-075 { 
    margin-top: 12px !important;
}
*/
```

<br/><br/>

<hintitem dont="true">
    Do not use margin and padding utilities inside components
</hintitem>

```html
<div class="mc-list">
  <div class="mc-list__item mu-mb-025">item</div>
  <div class="mc-list__item mu-mb-025">item</div>
</div>
```

<br/>

<hintitem>
    Use utilities to manage space between components
</hintitem>

```html
<div class="mc-list mu-mb-025">
  <div class="mc-list__item">item</div>
  <div class="mc-list__item">item</div>
</div>
<div class="mc-other">other</div>
```

<br/>

<hintitem>
    Use margins and padding using variables or functions to define inner spaces
</hintitem>

```css
@import 'settings-tools/_all-settings.scss';

.mc-list {
  /* ... list styles */

  &__item {
    margin-bottom: $mu-025;
  }
}
```

Utilities are meant to provide you with easy to use spacing.
When building reusable components, you should try to colocate all related styles within your component CSS definition.
It makes it easier for your coworker to understant what is related to what.

<br>

##Removing border-sizes from vertical paddings

<hintitem>
  You should remove border sizes from the vertical paddings values
</hintitem>

To remove border sizes from vertical padding, as borders are expressed in `px` and padding in `rem`, use the `calc()` css function :

```css
@import 'settings-tools/_all-settings.scss';

.exemple {
  border: solid 1px block;
  line-height: $mu-150;
  padding: calc($mu-025 - 1px) $mu-025;
}
```