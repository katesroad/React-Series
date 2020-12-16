# React Styling Guidelines

## The CSS Basics

### The Order of Css properties

Follow the rule of from the most important to normal
Rules that effect the layout and box size

> 1.  position and layout
> 2.  display and visbility
> 3.  clipping
> 4.  animation
> 5.  box model
> 6.  background
> 7.  typogratphy
> 8.  pesudo-classes

Reference: https://9elements.com/css-rule-order

### OCSS

The React Component

```ts
const ListingCard = () => {
  return (
    <article class="ListingCard ListingCard--featured">
      <h1 class="ListingCard__title">Adorable 2BR in the sunny Mission</h1>

      <div class="ListingCard__content">
        <p>Vestibulum id ligula porta felis euismod semper.</p>
      </div>
    </article>
  );
};
```

The css naming convention

```css
.ListingCard {
}
.ListingCard--featured {
}
.ListingCard__title {
}
.ListingCard__content {
}
```

- Airbnb ocss guidelines

## Styling React

### create-react-app supports css module by default

```ts
import styles from "./button.module.css";

const Button = () => <button className={styles.button}>Click Me</button>;
```

### Styled-components

### Styling Material-UI

