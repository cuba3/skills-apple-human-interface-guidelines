# Typography

Your typographic choices can help you display legible text, convey an information hierarchy, communicate important content, and express your brand or style.

## Ensuring Legibility

Use font sizes that most people can read easily. People need to be able to read your content at various viewing distances and under a variety of conditions. Follow the recommended default and minimum text sizes for each platform — for both custom and system fonts — to ensure your text is legible on all devices. Keep in mind that font weight can also impact how easy text is to read. If you use a custom font with a thin weight, aim for larger than the recommended sizes to increase legibility.

### Platform Default and Minimum Sizes

| Platform      | Default Size | Minimum Size |
|---------------|--------------|--------------|
| iOS, iPadOS   | 17 pt        | 11 pt        |
| macOS         | 13 pt        | 10 pt        |
| tvOS          | 29 pt        | 23 pt        |
| visionOS      | 17 pt        | 12 pt        |
| watchOS       | 16 pt        | 12 pt        |

Test legibility in different contexts. For example, you need to test game text for legibility on each platform on which your game runs. If testing shows that some of your text is difficult to read, consider using a larger type size, increasing contrast by modifying the text or background colors, or using typefaces designed for optimized legibility, like the system fonts.

In general, avoid light font weights. For example, if you're using system-provided fonts, prefer Regular, Medium, Semibold, or Bold font weights, and avoid Ultralight, Thin, and Light font weights, which can be difficult to see, especially when text is small.

## Conveying Hierarchy

Adjust font weight, size, and color as needed to emphasize important information and help people visualize hierarchy. Be sure to maintain the relative hierarchy and visual distinction of text elements when people adjust text sizes.

Minimize the number of typefaces you use, even in a highly customized interface. Mixing too many different typefaces can obscure your information hierarchy and hinder readability, in addition to making an interface feel internally inconsistent or poorly designed.

Prioritize important content when responding to text-size changes. Not all content is equally important. When someone chooses a larger text size, they typically want to make the content they care about easier to read; they don't always want to increase the size of every word on the screen. For example, when people increase text size to read the content in a tabbed window, they don't expect the tab titles to increase in size. Similarly, in a game, people are often more interested in a character's dialog than in transient hit-damage values.

## Using System Fonts

Apple provides two typeface families that support an extensive range of weights, sizes, styles, and languages.

### San Francisco (SF)

San Francisco (SF) is a sans serif typeface family that includes the SF Pro, SF Compact, SF Arabic, SF Armenian, SF Georgian, SF Hebrew, and SF Mono variants.

The system also offers SF Pro, SF Compact, SF Arabic, SF Armenian, SF Georgian, and SF Hebrew in rounded variants you can use to coordinate text with the appearance of soft or rounded UI elements, or to provide an alternative typographic voice.

### New York (NY)

New York (NY) is a serif typeface family designed to work well by itself and alongside the SF fonts.

### Variable Fonts

The system provides the SF and NY fonts in the variable font format, which combines different font styles together in one file, and supports interpolation between styles to create intermediate ones.

Variable fonts support optical sizing, which refers to the adjustment of different typographic designs to fit different sizes. On all platforms, the system fonts support dynamic optical sizes, which merge discrete optical sizes (like Text and Display) and weights into a single, continuous design, letting the system interpolate each glyph or letterform to produce a structure that's precisely adapted to the point size. With dynamic optical sizes, you don't need to use discrete optical sizes unless you're working with a design tool that doesn't support all the features of the variable font format.

To help you define visual hierarchies and create clear and legible designs in many different sizes and contexts, the system fonts are available in a variety of weights, ranging from Ultralight to Black, and — in the case of SF — several widths, including Condensed and Expanded. Because SF Symbols use equivalent weights, you can achieve precise weight matching between symbols and adjacent text, regardless of the size or style you choose.

### Text Styles

The system defines a set of typographic attributes — called text styles — that work with both typeface families. A text style specifies a combination of font weight, point size, and leading values for each text size. For example, the body text style uses values that support a comfortable reading experience over multiple lines of text, while the headline style assigns a font size and weight that help distinguish a heading from surrounding content. Taken together, the text styles form a typographic hierarchy you can use to express the different levels of importance in your content. Text styles also allow text to scale proportionately when people's system text size changes or accessibility adjustments are made.

Consider using the built-in text styles. The system-defined text styles give you a convenient and consistent way to convey your information hierarchy through font size and weight. Using text styles with the system fonts also ensures support for Dynamic Type and larger accessibility type sizes (where available), which let people choose the text size that works for them.

Modify the built-in text styles if necessary. System APIs define font adjustments — called symbolic traits — that let you modify some aspects of a text style. For example, the bold trait adds weight to text, letting you create another level of hierarchy. You can also use symbolic traits to adjust leading if you need to improve readability or conserve space.

## Using Custom Fonts

Make sure custom fonts are legible. People need to be able to read your custom font easily at various viewing distances and under a variety of conditions. While using a custom font, be guided by the recommended minimum font sizes for various styles and weights in Specifications.

Implement accessibility features for custom fonts. System fonts automatically support Dynamic Type (where available) and respond when people turn on accessibility features, such as Bold Text. If you use a custom font, make sure it implements the same behaviors.

## Supporting Dynamic Type

Dynamic Type is a system-level feature in iOS, iPadOS, tvOS, visionOS, and watchOS that lets people adjust the size of visible text on their device to ensure readability and comfort. For related guidance, see Accessibility.

Make sure your app's layout adapts to all font sizes. Verify that your design scales, and that text and glyphs are legible at all font sizes.

Increase the size of meaningful interface icons as font size increases. If you use interface icons to communicate important information, make sure they're easy to view at larger font sizes too. When you use SF Symbols, you get icons that scale automatically with Dynamic Type size changes.

Keep text truncation to a minimum as font size increases. In general, aim to display as much useful text at the largest accessibility font size as you do at the largest standard font size. Avoid truncating text in scrollable regions unless people can open a separate view to read the rest of the content.

Consider adjusting your layout at large font sizes. When font size increases in a horizontally constrained context, inline items (like glyphs and timestamps) and container boundaries can crowd text and cause truncation or overlapping. To improve readability, consider using a stacked layout where text appears above secondary items.

Maintain a consistent information hierarchy regardless of the current font size. For example, keep primary elements toward the top of a view even when the font size is very large, so that people don't lose track of these elements.

## Platform Considerations

### iOS, iPadOS

SF Pro is the system font in iOS and iPadOS. iOS and iPadOS apps can also use NY.

### macOS

SF Pro is the system font in macOS. NY is available for Mac apps built with Mac Catalyst. macOS doesn't support Dynamic Type.

When necessary, use dynamic system font variants to match the text in standard controls:

| Dynamic Font Variant | API                      |
|---------------------|--------------------------|
| Control content     | controlContentFont(ofSize:) |
| Label               | labelFont(ofSize:)       |
| Menu                | menuFont(ofSize:)        |
| Menu bar            | menuBarFont(ofSize:)     |
| Message             | messageFont(ofSize:)     |
| Palette             | paletteFont(ofSize:)     |
| Title               | titleBarFont(ofSize:)    |
| Tool tips           | toolTipsFont(ofSize:)   |
| Document text (user) | userFont(ofSize:)      |
| Bold system font    | boldSystemFont(ofSize:)  |
| System font         | systemFont(ofSize:)      |

### tvOS

SF Pro is the system font in tvOS, and apps can also use NY.

### visionOS

SF Pro is the system font in visionOS. If you use NY, you need to specify the type styles you want.

visionOS uses bolder versions of the Dynamic Type body and title styles and it introduces Extra Large Title 1 and Extra Large Title 2 for wide, editorial-style layouts.

In general, prefer 2D text. The more visual depth text characters have, the more difficult they can be to read. Although a small amount of 3D text can provide a fun visual element that draws people's attention, if you're going to display content that people need to read and understand, prefer using text that has little or no visual depth.

Make sure text looks good and remains legible when people scale it. Use a text style that makes the text look good at full scale, then test it for legibility at different scales.

Maximize the contrast between text and the background of its container. By default, the system displays text in white, because this color tends to provide a strong contrast with the default system background material, making text easier to read.

Keep text facing people as much as possible. If you display text that's associated with a point in space, such as a label for a 3D object, you generally want to use billboarding — that is, you want the text to face the wearer regardless of how they or the object move.

### watchOS

SF Compact is the system font in watchOS, and apps can also use NY. In complications, watchOS uses SF Compact Rounded.

## Specifications

### iOS, iPadOS Dynamic Type Sizes

| Style        | Weight   | Size (pt) | Leading (pt) | Emphasized |
|--------------|----------|-----------|--------------|------------|
| Large Title  | Regular  | 31        | 38           | Bold       |
| Title 1      | Regular  | 25        | 31           | Bold       |
| Title 2      | Regular  | 19        | 24           | Bold       |
| Title 3      | Regular  | 17        | 22           | Semibold   |
| Headline     | Semibold | 14        | 19           | Semibold   |
| Body         | Regular  | 14        | 19           | Semibold   |
| Callout      | Regular  | 13        | 18           | Semibold   |
| Subhead      | Regular  | 12        | 16           | Semibold   |
| Footnote     | Regular  | 12        | 16           | Semibold   |
| Caption 1    | Regular  | 11        | 13           | Semibold   |
| Caption 2    | Regular  | 11        | 13           | Semibold   |

### iOS, iPadOS Larger Accessibility Type Sizes (AX1-AX5)

| Style        | Weight   | Size (pt) | Leading (pt) | Emphasized |
|--------------|----------|-----------|--------------|------------|
| Large Title  | Regular  | 44        | 52           | Bold       |
| Title 1      | Regular  | 38        | 46           | Bold       |
| Title 2      | Regular  | 34        | 41           | Bold       |
| Title 3      | Regular  | 31        | 38           | Semibold   |
| Headline     | Semibold | 28        | 34           | Semibold   |
| Body         | Regular  | 28        | 34           | Semibold   |
| Callout      | Regular  | 26        | 32           | Semibold   |
| Subhead      | Regular  | 25        | 31           | Semibold   |
| Footnote     | Regular  | 23        | 29           | Semibold   |
| Caption 1    | Regular  | 22        | 28           | Semibold   |
| Caption 2    | Regular  | 20        | 25           | Semibold   |

### macOS Built-in Text Styles

| Text Style   | Weight   | Size (pt) | Line Height (pt) | Emphasized |
|--------------|----------|-----------|------------------|------------|
| Large Title  | Regular  | 26        | 32               | Bold       |
| Title 1      | Regular  | 22        | 26               | Bold       |
| Title 2      | Regular  | 17        | 22               | Bold       |
| Title 3      | Regular  | 15        | 20               | Semibold   |
| Headline     | Bold     | 13        | 16               | Heavy      |
| Body         | Regular  | 13        | 16               | Semibold   |
| Callout      | Regular  | 12        | 15               | Semibold   |
| Subheadline  | Regular  | 11        | 14               | Semibold   |
| Footnote     | Regular  | 10        | 13               | Semibold   |
| Caption 1    | Regular  | 10        | 13               | Medium     |
| Caption 2    | Medium   | 10        | 13               | Semibold   |

### tvOS Built-in Text Styles

| Text Style   | Weight   | Size (pt) | Leading (pt) | Emphasized |
|--------------|----------|-----------|--------------|------------|
| Title 1      | Medium   | 76        | 96           | Bold       |
| Title 2      | Medium   | 57        | 66           | Bold       |
| Title 3      | Medium   | 48        | 56           | Bold       |
| Headline     | Medium   | 38        | 46           | Bold       |
| Subtitle 1   | Regular  | 38        | 46           | Medium     |
| Callout      | Medium   | 31        | 38           | Bold       |
| Body         | Medium   | 29        | 36           | Bold       |
| Caption 1    | Medium   | 25        | 32           | Bold       |
| Caption 2    | Medium   | 23        | 30           | Bold       |

### watchOS Dynamic Type Sizes

| Style        | Weight   | Size (pt) | Leading (pt) | Emphasized |
|--------------|----------|-----------|--------------|------------|
| Large Title  | Regular  | 30        | 32.5         | Bold       |
| Title 1      | Regular  | 28        | 30.5         | Semibold   |
| Title 2      | Regular  | 24        | 26.5         | Semibold   |
| Title 3      | Regular  | 17        | 19.5         | Semibold   |
| Headline     | Semibold | 14        | 16.5         | Semibold   |
| Body         | Regular  | 14        | 16.5         | Semibold   |
| Caption 1    | Regular  | 13        | 15.5         | Semibold   |
| Caption 2    | Regular  | 12        | 14.5         | Semibold   |
| Footnote 1   | Regular  | 11        | 13.5         | Semibold   |
| Footnote 2   | Regular  | 10        | 12.5         | Semibold   |

### watchOS Larger Accessibility Type Sizes (AX1-AX3)

| Style        | Weight   | Size (pt) | Leading (pt) | Emphasized |
|--------------|----------|-----------|--------------|------------|
| Large Title  | Regular  | 44        | 46.5         | Bold       |
| Title 1      | Regular  | 42        | 44.5         | Semibold   |
| Title 2      | Regular  | 34        | 41           | Semibold   |
| Title 3      | Regular  | 24        | 26.5         | Semibold   |
| Headline     | Semibold | 21        | 23.5         | Semibold   |
| Body         | Regular  | 21        | 23.5         | Semibold   |
| Caption 1    | Regular  | 18        | 20.5         | Semibold   |
| Caption 2    | Regular  | 17        | 19.5         | Semibold   |
| Footnote 1   | Regular  | 16        | 18.5         | Semibold   |
| Footnote 2   | Regular  | 15        | 17.5         | Semibold   |

## Tracking Values

### iOS, iPadOS, visionOS (SF Pro)

| Size (pt) | Tracking (1/1000 em) | Tracking (pt) |
|-----------|---------------------|---------------|
| 6         | +41                 | +0.24         |
| 7         | +34                 | +0.23         |
| 8         | +26                 | +0.21         |
| 9         | +19                 | +0.17         |
| 10        | +12                 | +0.12         |
| 11        | +6                  | +0.06         |
| 12        | 0                   | 0.0           |
| 13        | -6                  | -0.08         |
| 14        | -11                 | -0.15         |
| 15        | -16                 | -0.23         |
| 16        | -20                 | -0.31         |
| 17        | -26                 | -0.43         |
| 18        | -25                 | -0.44         |
| 20        | -23                 | -0.45         |
| 22        | -12                 | -0.26         |
| 24        | +3                  | +0.07         |
| 28        | +14                 | +0.38         |
| 32        | +13                 | +0.41         |
| 40        | +10                 | +0.37         |
| 48        | +8                  | +0.35         |
| 60        | +4                  | +0.26         |
| 80        | 0                   | 0             |

## Resources

- [Fonts for Apple platforms](https://developer.apple.com/fonts/)
- [SF Symbols](https://developer.apple.com/sf-symbols/)
- [Text input and output — SwiftUI](https://developer.apple.com/documentation/swiftui/text-input-and-output)
- [Text display and fonts — UIKit](https://developer.apple.com/documentation/uikit/text_display_and_fonts)
- [Fonts — AppKit](https://developer.apple.com/documentation/appkit/fonts)

## Change Log

- **December 16, 2025**: Added emphasized weights to the Dynamic Type style specifications for each platform.
- **March 7, 2025**: Expanded guidance for Dynamic Type.
- **June 10, 2024**: Added guidance for using Apple's Unity plug-ins to support Dynamic Type in a Unity-based game and enhanced guidance on billboarding in a visionOS app or game.
- **September 12, 2023**: Added artwork illustrating system font weights, and clarified tvOS specification table descriptions.
- **June 21, 2023**: Updated to include guidance for visionOS.
