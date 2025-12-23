Bootsrtap + Dialog = ❤️
=======================

This repo shows how you can use Bootstrap with <dialog> tag, using Command Invoker API which is shipped even in Safari.

# Applications

This techniques interesting when using Bootstrap with application modern hybrid full-stack solutions, like Blazor, Next.js which control all your interactivity. 

# Motivation

Bootstrap want to control how do you open and close your modal popups, so do your full-stack framework. If you use this approach, you can use Bootstrap CSS without bringing JS and writing/using bridge code or separate integration library. At least you can delay this step.

Second motivation is to have as less JS in the browser as possible for simple cases.

# Idea

Instead of relying on `data-bs-toggle="modal"`, `data-bs-dismiss="modal"` and `data-bs-target="#exampleModal"`, you can use `command="show-modal"`, `command="close"` and `commandfor="exampleModal"` respectively.

You also need to override browser styles a bit.

```css
dialog.modal {
    padding: 0;
    max-width: fit-content;
    max-height: fit-content;
    border: none;
    background: transparent;
}

dialog.modal[open] {
    display: block !important;
}
```

For backdrop dismissal, you need to use `closedby="any"` on the `dialog` tag.