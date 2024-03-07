1. `_vars.scss` should be created in a prent folder. It should be a project related file. Can be changed per project. Copy it from any previous project.


Examples:

* Include font:
```scss
@include mx.font-face('Anago', vars.$font-path/Anago-Book, 400, normal, eot woff ttf);
```

* Enable cover image styles:
```scss
@include features.enable-page-cover-image();
```

* Enable CF7 styles:
```scss
@include features.enable-cf7-form-styles();
```

* Adds sliders styles:
```scss
// Should be imported after bootstrap-required.
@import "../sliders";
```

* Adds like headings styles (from `.h1` to `.h6`) for using non-semantic headings (like `<span class="h1">`):
```scss
@include features.enable-h-like-classes();
```

* _:
```scss

```

