# WP Theme Styles Library v2.0

A comprehensive SCSS library for WordPress theme development with Bootstrap integration, responsive utilities, navigation components, form styles, and Gutenberg block support.

## Overview

This library provides a modular, reusable set of SCSS tools designed specifically for WordPress theme development. It integrates with Bootstrap's RFS (Responsive Font Size) system while providing WordPress-specific utilities for Gutenberg blocks, navigation menus, forms, and layout patterns.

## File Structure

```
wp-theme-styles-lib/
├── wp-theme-styles-lib.scss    # Main entry point (v2.0)
├── _mixins.scss                # Core mixins and functions
├── _functions.scss             # Utility functions (SVG, string, math)
├── _defaults.scss              # CSS reset and base styles
├── _wrappers.scss              # Layout containers and grid systems
├── _features.scss              # Feature mixins (cover images, pagination, etc.)
├── _helpers.scss               # Utility classes
├── _navigation.scss            # Navigation and menu styles
├── _forms.scss                 # Form input and button styles
├── _sliders.scss               # Carousel/slider components
├── _wp-core.scss               # WordPress Gutenberg block styles
├── _wp-custom-blocks.scss      # Custom block styles
└── README.md                   # This file
```

## Core Modules

### 1. Mixins (`_mixins.scss`)

#### Accessibility & Visibility
- `textHidden()` - Hides text visually while keeping it screen-reader accessible
- `visually-hidden()` - Alternative visually hidden pattern

#### Typography
- `font($size, $line-height, $weight, $style, $font-family)` - Comprehensive font styling
- `font-rfs($size, ...)` - Font styling with Responsive Font Size support
- `line-height($size, $important)` - Line height with nrfs conversion
- `text-size($size, $height, $important)` - Combined font-size and line-height
- `calculateRem($value)` - Convert pixels to rem units
- `strip-unit($number)` - Remove units from values
- `nrfs-value($values)` - Non-responsive font-size value conversion

#### Layout & Positioning
- `clearfix()` - Modern clearfix using ::after
- `%clearfix` - Legacy clearfix placeholder
- `make-container($gutter-x)` - Bootstrap-style container
- `absolute($top, $index)` - Absolute positioning shorthand
- `fixed($top, $index)` - Fixed positioning shorthand
- `sticky($top, $index)` - Sticky positioning shorthand

#### Property Generation
- `generate-properties($properties, $important)` - Generate CSS from property maps
- `generate-rfs-properties($properties, $important)` - RFS-aware property generation
- `generate-properties-from($array, $key, $important)` - Generate from nested maps
- `generate-rfs-properties-from($array, $key, $important)` - RFS version

#### Images & Backgrounds
- `img-cover` - Object-fit cover for images
- `bg-cover($url, $positions, $attachment, $size)` - Full-screen background images
- `overlay-bg($color, $opacity, $next)` - Semi-transparent overlay

#### Text Utilities
- `ellipsis($width, $display)` - Text truncation with ellipsis
- `vertical_align` - Vertical centering using transform
- `text-shadow($color, $darken)` - Text shadow with automatic darkening

#### Visual Effects
- `prefix($property, $value, $vendors, $default)` - Vendor prefix generator
- `linear-gradient($top-color, $bottom-color, $opacity)` - Cross-browser gradients
- `triangle($color, $size)` - CSS triangle generator
- `transition($transition...)` - Transition with reduced-motion support

#### Font Loading
- `font-face($name, $path, $weight, $style, $exts, $display)` - @font-face generator
- `headings-typography($typography, $rfs)` - Apply typography to h1-h6

#### Breakpoints
- `breakpoint-min($bp)` - Min-width media query
- `breakpoint-max($bp)` - Max-width media query
- `breakpoint-min-max($bp1, $bp2)` - Range media query
- `breakpoint-greater-than($bp)` - Exclusive min-width
- `breakpoint-less-than($bp)` - Exclusive max-width

#### Forms
- `$all-buttons` - Selector list for all button types
- `$all-text-inputs` - Selector list for all text inputs
- `_assign-inputs($inputs, $pseudo)` - Add pseudo-classes to input lists

### 2. Functions (`_functions.scss`)

#### SVG Utilities
- `escape-svg($string)` - URL-encode SVG for CSS backgrounds

#### String Manipulation
- `str-replace($string, $search, $replace)` - Find and replace in strings

#### Mathematics
- `divide($dividend, $divisor, $precision)` - Safe division with unit handling

#### Map Operations
- `sub-map-get($map, $key1, $key2)` - Access nested map values

### 3. Layout Wrappers (`_wrappers.scss`)

#### Container Classes
- `.container` - Full-width flex container
- `.content-wrapper` - Bootstrap-style container with gutters
- `.content-block` - Centered content block with max-width
- `.content-block-fluid` - Fluid width content block
- `.content-grid` - CSS Grid layout with breakout areas
- `.container-with-sidebar` - Two-column layout with sidebar

#### Grid Features
- Full-width breakout support
- Responsive spacing variables
- Content width variants (narrow, default, wider)

### 4. Features (`_features.scss`)

#### Page Features
- `enable-page-cover-image()` - Hero/cover image sections
- `enable-wp-adminbar-spacing()` - WordPress admin bar compensation
- `enable-cf7-form-styles()` - Contact Form 7 styling
- `enable-h-like-classes()` - Utility classes matching heading styles
- `enable-columns-layout-styles()` - Flexbox column layouts
- `enable-list-columns-layout-styles()` - Multi-column lists
- `enable-buttons-classes()` - Custom button style variants
- `enable-social-icons-styles()` - Social media icon links
- `enable-pagination-styles()` - Archive pagination styling

#### Grid & Listing
- `grid-list-container()` - CSS Grid listing layout
- `masonry-listing-styles()` - Masonry-style post listings

### 5. Navigation (`_navigation.scss`)

#### Main Navigation
- `enable-nav-bar()` - Complete navigation system with:
  - Desktop dropdown menus
  - Mobile hamburger menu
  - Current page highlighting
  - Customizable link states (hover, active, current)
  - Background colors for items and containers

#### Mega Menu
- `enable-mega-menu()` - Multi-column dropdown menus

#### Mobile Navigation
- Slide-out mobile menu
- Customizable toggle button
- Dropdown arrow indicators
- Touch-friendly spacing

### 6. WordPress Core (`_wp-core.scss`)

#### Gutenberg Block Support
- `wp-main-styles()` - Core WordPress alignment classes
  - `.alignleft`, `.alignright`, `.aligncenter`
  - `.alignwide` - Wide width blocks
  - `.alignfull` - Full width blocks
  - `.wp-block-group` - Group block styling
  - `.wp-block-buttons` - Button blocks
  - `.wp-block-image` - Image blocks with captions

#### Comments
- `wp-comments-styles()` - Comment form and list styling

#### Editor Support
- `enable-wp-editor-align-full()` - Editor alignment styles
- `wp-color-pallete($colors)` - Custom color palette
- `wp-font-sizes($typography)` - Custom font size classes
- `wp-headings($typography, $rfs)` - Heading styles for editor
- `wp-block-button-styles()` - Button block variants
- `wp-block-button()` - Single button style

### 7. Forms (`_forms.scss`)

#### Form Components
- `.form-fields-container` - Flexbox form layout
- Text input styling (all types)
- Button styling with state variants
- Search form layout
- Contact Form 7 integration

### 8. Sliders (`_sliders.scss`)

#### Carousel Components
- `.carousel` - Base carousel container
- `.carousel-item` - Individual slides
- `.carousel-fade` - Fade transition variant
- `.carousel-control-prev/next` - Navigation arrows
- `.carousel-indicators` - Dot indicators
- `.carousel-caption` - Slide captions
- `.hero-slider` - Full-height hero slider

### 9. Helpers (`_helpers.scss`)

#### Utility Classes
- `.display-none` / `.d-flex` - Display utilities
- `.hidden` - Screen-reader only
- `.visually-hidden` - Alternative hidden class
- `.pt-0` / `.pb-0` - Padding utilities
- `.clearfix` - Float clearing
- `.align-center` / `.align-right` - Text alignment
- `.page-scrolled` - Scrolled state styling

### 10. Defaults (`_defaults.scss`)

#### CSS Reset & Base
- Box-sizing reset
- Typography normalization
- Link styling
- List styling
- Form element normalization
- Table styling
- Code/preformatted text

## Usage Examples

### Basic Typography
```scss
@use "wp-theme-styles-lib/mixins" as mx;

.my-heading {
    @include mx.font(24px, 1.4, 700);
}
```

### Responsive Breakpoints
```scss
@use "wp-theme-styles-lib/mixins" as mx;

.responsive-element {
    width: 100%;
    
    @include mx.breakpoint-min(768px) {
        width: 50%;
    }
}
```

### Container Setup
```scss
@use "wp-theme-styles-lib/wrappers";

// HTML structure:
// <div class="content-grid">
//   <div class="breakout">Wide content</div>
//   <p>Normal content</p>
// </div>
```

### Navigation
```scss
@use "wp-theme-styles-lib/navigation" as nav;

@include nav.enable-nav-bar();
@include nav.enable-mega-menu();
```

### WordPress Blocks
```scss
@use "wp-theme-styles-lib/wp-core" as wp;

.wp-core {
    @include wp.wp-main-styles();
}
```

### Property Generation from Maps
```scss
@use "wp-theme-styles-lib/mixins" as mx;

$button-styles: (
    primary: (
        background-color: #007bff,
        color: white,
        padding: 10px 20px
    )
);

.button-primary {
    @include mx.generate-properties-from($button-styles, primary);
}
```

## Integration Notes

### Bootstrap Integration
This library is designed to work alongside Bootstrap 5.x. It uses Bootstrap's RFS system for fluid typography and spacing when available.

### WordPress Requirements
- Designed for WordPress 5.8+ with Gutenberg block editor
- Supports full-site editing patterns
- Compatible with classic themes and block themes

### Variable Dependencies
The library expects certain variables to be defined in your project's `_vars.scss`:
- `$mobile`, `$tablet`, `$narrow` - Breakpoint values
- `$container-padding-x` - Container gutter width
- `$post-content-max-width` - Content width
- `$navbar-mobile` - Mobile nav breakpoint
- Color variables for theming

## Browser Support

- Chrome/Edge (latest 2 versions)
- Firefox (latest 2 versions)
- Safari (latest 2 versions)
- IE11 (partial, graceful degradation)

## Version History

### v2.0 (Current)
- Added comprehensive JSDoc/SassDoc documentation
- Organized mixins into logical groups
- Added version headers to all files
- Improved breakpoint consistency
- Enhanced WordPress block editor support

## License

MIT License - Free for personal and commercial use.
