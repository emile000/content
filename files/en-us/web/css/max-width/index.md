---
title: max-width
slug: Web/CSS/max-width
page-type: css-property
browser-compat: css.properties.max-width
sidebar: cssref
---

The **`max-width`** [CSS](/en-US/docs/Web/CSS) property sets the maximum width of an element. It prevents the [used value](/en-US/docs/Web/CSS/CSS_cascade/Value_processing#used_value) of the {{cssxref("width")}} property from becoming larger than the value specified by `max-width`.

{{InteractiveExample("CSS Demo: max-width")}}

```css interactive-example-choice
max-width: 150px;
```

```css interactive-example-choice
max-width: 20em;
```

```css interactive-example-choice
max-width: 75%;
```

```css interactive-example-choice
max-width: 20ch;
```

```html interactive-example
<section class="default-example" id="default-example">
  <div class="transition-all" id="example-element">
    Change the maximum width.
  </div>
</section>
```

```css interactive-example
#example-element {
  display: flex;
  flex-direction: column;
  background-color: #5b6dcd;
  height: 80%;
  justify-content: center;
  color: #ffffff;
}
```

`max-width` overrides {{cssxref("width")}}, but {{cssxref("min-width")}} overrides `max-width`.

## Syntax

```css
/* <length> value */
max-width: 3.5em;
max-width: anchor-size(--myAnchor inline, 245px);
max-width: calc(anchor-size(width) + 4em);

/* <percentage> value */
max-width: 75%;

/* Keyword values */
max-width: none;
max-width: max-content;
max-width: min-content;
max-width: fit-content;
max-width: fit-content(20em);
max-width: stretch;

/* Global values */
max-width: inherit;
max-width: initial;
max-width: revert;
max-width: revert-layer;
max-width: unset;
```

### Values

- {{cssxref("&lt;length&gt;")}}
  - : Defines the `max-width` as an absolute value.
- {{cssxref("&lt;percentage&gt;")}}
  - : Defines the `max-width` as a percentage of the containing block's width.
- `none`
  - : No limit on the size of the box.
- `max-content`
  - : The intrinsic preferred `max-width`.
- `min-content`
  - : The intrinsic minimum `max-width`.
- `fit-content`
  - : Use the available space, but not more than [max-content](/en-US/docs/Web/CSS/max-content), i.e., `min(max-content, max(min-content, stretch))`.
- `fit-content({{cssxref("&lt;length-percentage&gt;")}})`
  - : Uses the `fit-content` formula with the available space replaced by the specified argument, i.e., `min(max-content, max(min-content, argument))`.
- `stretch`
  - : Limits the maximum width of the element's [margin box](/en-US/docs/Learn_web_development/Core/Styling_basics/Box_model#parts_of_a_box) to the width of its [containing block](/en-US/docs/Web/CSS/CSS_display/Containing_block#identifying_the_containing_block). It attempts to make the margin box fill the available space in the containing block, so in a way behaving similar to `100%` but applying the resulting size to the margin box rather than the box determined by [box-sizing](/en-US/docs/Web/CSS/box-sizing).

    > [!NOTE]
    > To check aliases used by browsers for the `stretch` value and its implementation status, see the [Browser compatibility](#browser_compatibility) section.

## Accessibility

Ensure that elements set with a `max-width` are not truncated and/or do not obscure other content when the page is zoomed to increase text size.

- [MDN Understanding WCAG, Guideline 1.4 explanations](/en-US/docs/Web/Accessibility/Guides/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.4 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-scale.html)

## Formal definition

{{cssinfo}}

## Formal syntax

{{csssyntax}}

## Examples

### Setting max width in pixels

In this example, the "child" will be either 150 pixels wide or the width of the "parent," whichever is smaller.

#### HTML

```html
<div id="parent">
  <div id="child">
    Fusce pulvinar vestibulum eros, sed luctus ex lobortis quis.
  </div>
</div>
```

#### CSS

```css
#parent {
  background: lightblue;
  width: 300px;
}

#child {
  background: gold;
  width: 100%;
  max-width: 150px;
}
```

#### Result

{{EmbedLiveSample("Setting_max_width_in_pixels", 350, 100)}}

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- {{Cssxref("min-width")}}
- {{Cssxref("width")}}
- {{cssxref("max-inline-size")}}
- {{cssxref("max-block-size")}}
- {{cssxref("box-sizing")}}
- [Introduction to the CSS box model](/en-US/docs/Web/CSS/CSS_box_model/Introduction_to_the_CSS_box_model) guide
- [CSS box model](/en-US/docs/Web/CSS/CSS_box_model) module
