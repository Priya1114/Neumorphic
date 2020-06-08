# Neumorphism

Blend of Minimalism and Skeuomorphism.

Minimilistic UI is simple, easy to understand and contain only neccessary elements.

Skeuomorphic UI describs element which is mimic their real world counterparts, in how they appear and how user interacts with them.

Neumorphic UI elements looks like they are connected to the background(extruded from background or inset in background).
Properties that adds neomorphic effect to the elements are Background colors, Borders, Edges and Shadows.

## 1. Background color

One major requirement for neomorphic design is, Background color should be same as (or similar to) background color of parent element. This color constraint blends the element with the background and it looks like connected.

### CSS Implementation for background

In CSS background/background-color property sets the background color of the element.
We can have both solid and gradient background in neomorphic design. Solid background makes the element look flat while gradient adds Concave(surface curves inwards) and Convex(surface curves outwards) effects.

```css
  .body {
    background: #afd275;
  }

  .element {
    background: #afd275;
  }
```

To add Concave and Convex effect set linear-gradient to the background property.

```css
.element {
  background: linear-gradient(var(--bg-angle), var(--bg-start), var(--bg-end));
}
```

*Concave

```css
  background: linear-gradient(135deg, rgba(0,0,0,0.22), rgba(255,255,255,0.25));
```

*Convex

```css
  background: linear-gradient(-45deg, rgba(0,0,0,0.22), rgba(255,255,255,0.25));
```

## 2.Shadows

Core part of Neomorphic element is the use of two shadows: light shadow and dark shadow. That's how the element connected to the background gets sort of "Raised" effect.

### CSS Implementation for shadow effect

In CSS 'box-shadow' property is used to add shadows to the element.
Box-Shadow on an element can be both Outwards and Inwards. Following are the value of box-shadow.

  ```css
  box-shadow: [horizontal offset] [vertical offset] [blur radius] [optional spread radius] [color];
  ```

  1. Horizontal Offset: A positive value offsets shadow to the right and negative value offsets shadow to the left.
  2. Vertical Offset: A positive value offsets shadow upwards and negative value offsets downwards.
  3. Blur Radius : sets the length of shadow, Longer the length, bigger and lighter is the shadow.No negative value.
  4. Spread Radius: also a length value (mostly not required in neumorphism)
  5. Color: set the color of shadow.
  6. Inset: sets the shadow inwards.

Outer Shadow

  ```css
  box-shadow: [horizontal offset] [vertical offset] [blur radius] [optional spread radius] [color];
  ```

Inner Shadow

  ```css
    box-shadow: [horizontal offset] [vertical offset] [blur radius] [optional spread radius] [color] inset;
  ```

In css element can have multiple box-shadows set to it seprated by comma operator.

To implement Neomorphism we need to add two shadows, first one with positive offset values and light color and other one with negative offset values and dark color.

```css
box-shadow: var(--h1) var(--v1) var(--blur1) var(--color-dark),
            var(--h2) var(--v2) var(--blur2) var(--color-light);
```

```css
box-shadow: 20px 20px 50px #00d2c6,
            -30px -30px 60px #00ffff;
```

## 3. Edges

Round Edges are preferred for neomorphic design.

### CSS Implementation for rounded edges

In CSS use border-radius porperty to add curved edges to the element. Set border-radius value depending on the height and width of the element.
Setting it to 100% makes the element look circular.

```css
  border-radius: 50px;
```

## 4.Borders

Element can have optional subtle border to improve the contrast.

```css
  border: 1px solid #afd275;
```
