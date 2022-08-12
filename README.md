# $\text{Godo}\TeX$

GodoTeX is an add-on to Godot Mono that renders LaTeX expressions - in the editor and at runtime!

![](https://github.com/file-acomplaint/file-acomplaint/blob/main/assets/latex.gif?raw=true)

***Note**: This is still an early version and may change significantly. The project will be finished by October 2022.*

## Features
- It's *really* fast!
- Editor Integration
- Inherits all Functionality from [`Sprite`](https://docs.godotengine.org/en/stable/classes/class_sprite.html?highlight=sprite)
- Adjustable Font Size
- Adjustable Font Color
- Anti-Aliasing (with Toggle)

## Compatibility
The add-on is tested for Godot 3.4.x and is expected to run on 3.x. Support for Windows and Linux is planned. MacOS is sadly not being tested due to lack of appropriate hardware. A version for Godot 4.x will be provided after its release, if possible.

## Usage
A custom node `LaTeX` inheriting from `Sprite` is provided and may be instanced like any other. It has the following properties, which may be updated in the editor or programmatically at runtime

- **LatexExpression**: A `string` containing the expression to be rendered. If invalid, the corresponding error message will be rendered instead.
- **FontSize**: A `float`, the font size in points. It essentially controls the resolution of the rendered image. Decrease for better performance, increase for higher fidelity.
- **MathColor**: A Godot `Color`, the typeface's color.
- **AntiAliasing**: A `bool`. The renderer may or may not be instructed to anti-aliase the rendered typeface. Note that this is distinct from Godot's own anti-aliasing.

When updating these in the editor, the expression is automatically rendered anew. When updating properties programmatically, you decide yourself when to render by calling the `.Render()` method - to save ressources. Rendering very often (several times a millisecond) may result in errors.

## Heritage
The add-on depends on [`CSharpMath.SkiaSharp`](https://github.com/verybadcat/CSharpMath), licensed under MIT, as a nuget package.

## License
Licensed under MIT. © 2022 fi-le
