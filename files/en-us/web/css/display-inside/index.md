---
title: <display-inside>
slug: Web/CSS/display-inside
page-type: css-type
browser-compat:
  - css.properties.display.flow-root
  - css.properties.display.table
  - css.properties.display.flex
  - css.properties.display.grid
  - css.properties.display.ruby
spec-urls: https://drafts.csswg.org/css-display/#typedef-display-inside
sidebar: cssref
---

These keywords specify the element's inner {{CSSxRef("display")}} type, which defines the type of formatting context that lays out its contents (assuming it is a non-replaced element). These keywords are used as values of the `display` property, and can be used for legacy purposes as a single keyword, or as defined in the Level 3 specification alongside a value from the {{CSSxRef("&lt;display-outside&gt;")}} keywords.

## Syntax

Valid `<display-inside>` values:

- `flow`
  - : The element lays out its contents using flow layout (block-and-inline layout).

    If its outer display type is `inline`, and it is participating in a block or inline formatting context, then it generates an inline box. Otherwise it generates a block container box.

    Depending on the value of other properties (such as {{CSSxRef("position")}}, {{CSSxRef("float")}}, or {{CSSxRef("overflow")}}) and whether it is itself participating in a block or inline formatting context, it either establishes a new [block formatting context](/en-US/docs/Web/CSS/CSS_display/Block_formatting_context) (BFC) for its contents or integrates its contents into its parent formatting context.

- `flow-root`
  - : The element generates a block element box that establishes a new [block formatting context](/en-US/docs/Web/CSS/CSS_display/Block_formatting_context), defining where the formatting root lies.
- `table`
  - : These elements behave like HTML {{HTMLElement("table")}} elements. It defines a block-level box.
- `flex`
  - : The element behaves like a block element and lays out its content according to the [flexbox model](/en-US/docs/Web/CSS/CSS_flexible_box_layout).
- `grid`
  - : The element behaves like a block element and lays out its content according to the [grid model](/en-US/docs/Web/CSS/CSS_grid_layout/Basic_concepts_of_grid_layout).
- `ruby`
  - : The element behaves like an inline element and lays out its content according to the ruby formatting model. It behaves like the corresponding HTML {{HTMLElement("ruby")}} elements.

> [!NOTE]
> Browsers that support the two value syntax, on finding the inner value only, such as when `display: flex` or `display: grid` is specified, will set their outer value to `block`. This will result in expected behavior; for example if you specify an element to be `display: grid`, you would expect that the box created on the grid container would be a block level box.

## Formal syntax

{{csssyntax}}

## Examples

In this example the parent box has been given `display: flow-root` and so establishes a new BFC and contains the floated item.

### HTML

```html
<div class="box">
  <div class="float">I am a floated box!</div>
  <p>I am content inside the container.</p>
</div>
```

### CSS

```css
.box {
  background-color: rgb(224 206 247);
  border: 5px solid rebeccapurple;
  display: flow-root;
}

.float {
  float: left;
  width: 200px;
  height: 150px;
  background-color: white;
  border: 1px solid black;
  padding: 10px;
}
```

### Result

{{EmbedLiveSample("Examples", "100%", 180)}}

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- {{CSSxRef("display")}}
  - {{CSSxRef("&lt;display-outside&gt;")}}
  - {{CSSxRef("&lt;display-listitem&gt;")}}
  - {{CSSxRef("&lt;display-internal&gt;")}}
  - {{CSSxRef("&lt;display-box&gt;")}}
  - {{CSSxRef("&lt;display-legacy&gt;")}}

- [Basic concepts of flexbox](/en-US/docs/Web/CSS/CSS_flexible_box_layout/Basic_concepts_of_flexbox)
- [Basic Concepts of grid layout](/en-US/docs/Web/CSS/CSS_grid_layout/Basic_concepts_of_grid_layout)
