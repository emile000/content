---
title: CSS reference
slug: Web/CSS/Reference
page-type: landing-page
sidebar: cssref
---

Use this **CSS reference** to browse an [alphabetical index](#index) of all of the standard [CSS](/en-US/docs/Web/CSS) properties, [pseudo-classes](/en-US/docs/Web/CSS/Pseudo-classes), [pseudo-elements](/en-US/docs/Web/CSS/Pseudo-elements), [data types](/en-US/docs/Web/CSS/CSS_Values_and_Units/CSS_data_types), [functional notations](/en-US/docs/Web/CSS/CSS_Values_and_Units/CSS_Value_Functions) and [at-rules](/en-US/docs/Web/CSS/CSS_syntax/At-rule). You can also browse [key CSS concepts](#concepts) and a list of [selectors organized by type](#selectors). Also included is a brief [DOM-CSS / CSSOM reference](#dom-css_cssom).

## Basic rule syntax

### Style rule syntax

```plain
style-rule ::=
    selectors-list {
      properties-list
    }
```

Where:

```plain
selectors-list ::=
    selector[:pseudo-class] [::pseudo-element]
    [, selectors-list]

properties-list ::=
    [property : value] [; properties-list]
```

See the index of [_selectors_](#selectors), [_pseudo-classes_](#pseudo), and _[pseudo-elements](#pseudo)_ below. The syntax for each specified _value_ depends on the data type defined for each specified _property_.

#### Style rule examples

```css
strong {
  color: red;
}

div.menu-bar li:hover > ul {
  display: block;
}
```

For a beginner-level introduction to the syntax of selectors, see our [guide on CSS Selectors](/en-US/docs/Learn_web_development/Core/Styling_basics/Basic_selectors). Be aware that any [syntax](/en-US/docs/Web/CSS/CSS_syntax/Syntax) error in a rule definition invalidates the entire rule. Invalid rules are ignored by the browser. Note that CSS rule definitions are entirely (Unicode) [text-based](https://drafts.csswg.org/css-syntax/#intro), whereas DOM-CSS / CSSOM (the rule management system) is [object-based](https://drafts.csswg.org/cssom/#introduction).

### At-rule syntax

As the structure of at-rules varies widely, please see [At-rule](/en-US/docs/Web/CSS/CSS_syntax/At-rule) to find the syntax of the specific one you want.

## Index

> [!NOTE]
> This index does not include SVG-exclusive presentation attributes, which can be used as CSS properties on [SVG](/en-US/docs/Web/SVG) elements.

> [!NOTE]
> The property names in this index do **not** include the JavaScript names which do differ from the CSS standard names.

{{CSS_Ref}}

## Selectors

The following are the various [selectors](/en-US/docs/Web/CSS/CSS_selectors), which allow styles to be conditional based on various features of elements within the DOM.

### Basic selectors

**Basic selectors** are fundamental selectors; these are the most basic selectors that are frequently combined to create other, more complex selectors.

- [Universal selector](/en-US/docs/Web/CSS/Universal_selectors) `*`
- [Type selector](/en-US/docs/Web/CSS/Type_selectors) `elementname`
- [Class selector](/en-US/docs/Web/CSS/Class_selectors) `.classname`
- [ID selector](/en-US/docs/Web/CSS/ID_selectors) `#idname`
- [Attribute selector](/en-US/docs/Web/CSS/Attribute_selectors) `[attr=value]`

### Grouping selectors

- [Selector list](/en-US/docs/Web/CSS/Selector_list) `A, B`
  - : Specifies that both `A` and `B` elements are selected. This is a grouping method to select several matching elements.

### Combinators

Combinators are selectors that establish a relationship between two or more simple selectors, such as "`A` is a child of `B`" or "`A` is adjacent to `B`", creating a complex selector.

- [Next-sibling combinator](/en-US/docs/Web/CSS/Next-sibling_combinator) `A + B`
  - : Specifies that the elements selected by both `A` and `B` have the same parent and that the element selected by `B` immediately follows the element selected by `A` horizontally.
- [Subsequent-sibling combinator](/en-US/docs/Web/CSS/Subsequent-sibling_combinator) `A ~ B`
  - : Specifies that the elements selected by both `A` and `B` share the same parent and that the element selected by `A` comes before—but not necessarily immediately before—the element selected by `B`.
- [Child combinator](/en-US/docs/Web/CSS/Child_combinator) `A > B`
  - : Specifies that the element selected by `B` is the direct child of the element selected by `A`.
- [Descendant combinator](/en-US/docs/Web/CSS/Descendant_combinator) `A B`
  - : Specifies that the element selected by `B` is a descendant of the element selected by `A`, but is not necessarily a direct child.
- [Column combinator](/en-US/docs/Web/CSS/Column_combinator) `A || B` {{Experimental_Inline}}
  - : Specifies that the element selected by `B` is located within the table column specified by `A`. Elements which span multiple columns are considered to be a member of all of those columns.

### Pseudo

- [Pseudo classes](/en-US/docs/Web/CSS/Pseudo-classes) `:`
  - : Specifies a special state of the selected element(s).
- [Pseudo elements](/en-US/docs/Web/CSS/Pseudo-elements) `::`
  - : Represents entities that are not included in HTML.

> [!CALLOUT]
>
> See also [selectors in the Selectors specification](https://drafts.csswg.org/selectors/) and the [pseudo-element specification](https://drafts.csswg.org/css-pseudo/).

## Concepts

### Syntax and semantics

- [CSS syntax](/en-US/docs/Web/CSS/CSS_syntax/Syntax)
- [At-rules](/en-US/docs/Web/CSS/CSS_syntax/At-rule)
- [Cascade](/en-US/docs/Web/CSS/CSS_cascade/Cascade)
- [Comments](/en-US/docs/Web/CSS/CSS_syntax/Comments)
- [Descriptor](/en-US/docs/Glossary/CSS_Descriptor)
- [Inheritance](/en-US/docs/Web/CSS/CSS_cascade/Inheritance)
- [Shorthand properties](/en-US/docs/Web/CSS/CSS_cascade/Shorthand_properties)
- [Specificity](/en-US/docs/Web/CSS/CSS_cascade/Specificity)
- [Value definition syntax](/en-US/docs/Web/CSS/CSS_Values_and_Units/Value_definition_syntax)
- [CSS values and units](/en-US/docs/Web/CSS/CSS_Values_and_Units)
- [CSS functional notations](/en-US/docs/Web/CSS/CSS_Values_and_Units/CSS_Value_Functions)

### Values

- [Actual value](/en-US/docs/Web/CSS/CSS_cascade/Value_processing#actual_value)
- [Computed value](/en-US/docs/Web/CSS/CSS_cascade/Value_processing#computed_value)
- [Initial value](/en-US/docs/Web/CSS/CSS_cascade/Value_processing#initial_value)
- [Resolved value](/en-US/docs/Web/CSS/CSS_cascade/Value_processing#resolved_value)
- [Specified value](/en-US/docs/Web/CSS/CSS_cascade/Value_processing#specified_value)
- [Used value](/en-US/docs/Web/CSS/CSS_cascade/Value_processing#used_value)

### Layout

- [Block formatting context](/en-US/docs/Web/CSS/CSS_display/Block_formatting_context)
- [Box model](/en-US/docs/Web/CSS/CSS_box_model/Introduction_to_the_CSS_box_model)
- [Containing block](/en-US/docs/Web/CSS/CSS_display/Containing_block)
- [Layout mode](/en-US/docs/Glossary/Layout_mode)
- [Margin collapsing](/en-US/docs/Web/CSS/CSS_box_model/Mastering_margin_collapsing)
- {{glossary("Replaced elements")}}
- [Stacking context](/en-US/docs/Web/CSS/CSS_positioned_layout/Stacking_context)
- [Visual formatting model](/en-US/docs/Web/CSS/CSS_display/Visual_formatting_model)

## DOM-CSS / CSSOM

### Major object types

- {{DOMxRef("Document.styleSheets")}}
- {{DOMxRef("HTMLElement.style")}}
- {{DOMxRef("Element.className")}}
- {{DOMxRef("Element.classList")}}
- {{DOMxRef("StyleSheetList")}}
- {{DOMxRef("CSSRuleList")}}
- {{DOMxRef("CSSRule")}}
- {{DOMxRef("CSSStyleRule")}}
- {{DOMxRef("CSSStyleDeclaration")}}

### Important methods

- {{DOMxRef("CSSStyleSheet.insertRule()")}}
- {{DOMxRef("CSSStyleSheet.deleteRule()")}}

## See also

- [Mozilla CSS extensions](/en-US/docs/Web/CSS/Mozilla_Extensions) (prefixed with `-moz-`)
- [WebKit CSS extensions](/en-US/docs/Web/CSS/WebKit_Extensions) (mostly prefixed with `-webkit-`)

## External Links

- [CSS Indices (w3.org)](https://www.w3.org/TR/css/#indices)
