# Windows 7+ DirectUI Documentation

Also good sources:
- https://github.com/seven-mile/dui70/blob/master/docs/ElementClass.g.txt
- https://www.vistastylebuilder.com/forum/index.php?topic=215.0

## Contributing
If you have additional documentation about DirectUI, fork the repository, add the documentation and make a commit.


# ResourceBitmap - resbmp()

Allows for use of bitmap resources in any binary DirectUI can read.

**Syntax:**
```
resbmp(resource_id, parameter2, parameter3, parameter4, parameter5, parameter6, parameter7, library(binary))
```

`resource_id` - The ID of the bitmap resource in the binary.

`parameter2` - Unknown.

`parameter3` - Unknown.

`parameter4` - Unknown.

`parameter5` - Unknown.

`parameter6` - Unknown.

`parameter7` - Unknown.

`library(binary)` - Binary name.

**Example:**
```
resbmp(0xA623, 2, -1, 16, 16, 0, 0, library(ieframe.dll))
```

- Contributed by @angelbruni


# ContentAlign - contentalign()
Allows us to choose the alignment of the [Content](#content).

- `TopLeft : 0x0 (0)`;
- `TopCenter : 0x1 (1)`;
- `TopRight : 0x2 (2)`;
- `MiddleLeft : 0x4 (4)`;
- `MiddleCenter : 0x5 (5)`;
- `MiddleRight : 0x6 (6)`;
- `BottomLeft : 0x8 (9)`;
- `BottomCenter : 0x9 (9)`;
- `BottomRight : 0xa (10)`.
- `WrapLeft : 0xc (12)`;
- `WrapCenter : 0xd (13)`;
- `WrapRight : 0xe (14)`;
- `EndEllipsis : 0x10 (16)`;
- `FocusRect : 0x20 (32)`;
- `PathEllipsis : 0x40 (64)`;
- `NoPrefix : 0x80 (128)`;
- `WordEllipsis : 0x100 (256)`;
- `EditControl : 0x200 (512)`;
- `StartEllipsis : 0x400 (1024)`.

**Example:**
```
contentalign(MiddleCenter)
```

- Contributed by @angelbruni


# ResourceString - resstr()
Allows for use of string resources in any binary DirectUI can read. Usually used for localisation support.

**Syntax:**
```
resstr(resource_id, library(binary))
```

`resource_id` - The ID of the bitmap resource in the binary.
`library(binary)` - Binary name.

**Example:**
```
resstr(0x7AB4, library(shell32.dll))
```

- Contributed by @angelbruni


# Icon - icon()
Allows for use of icon group resources in any binary DirectUI can read. Known to be used with [Content](#content), [Themeable](#themeable---themeable).

**Syntax:**
```
icon(resource_id, width, height, library(binary))
```

`resource_id` - The ID of the bitmap resource in the binary.
`width` - Icon width.
`height` - Icon height.
`library(binary)` - Binary name.

**Example:**
```
icon(24, sysmetric(49), sysmetric(50), library(shell32.dll))
```

- Contributed by @angelbruni


# `<if />`
Used for styling depending on the statement. The if can be used for (I think) any attribute.

```
<if accdesc="resstr(31282, library(shell32.dll))">
    <Button3d content="icon(246, sysmetric(49), sysmetric(50), library(shell32.dll))"/>
</if>
```

- Contributed by @angelbruni


# accname
An attribute used to show a string in a name (normally the control label). Known to also work with [ResourceString](#resourcestring---resstr).

**Examples:**

**Using simply text:**
```
accname="Hello world!"
```

**Using resstr:**
```
accname="resstr(0x7AB4, library(shell32.dll))"
```

- Contributed by @angelbruni


# accdesc
An attribute used to show a string in a description (normally used in tooltips). Known to also work with [ResourceString](#resourcestring---resstr).

**Examples:**

**Using simply text:**
```
accdesc="Hello world!"
```

**Using resstr:**
```
accdesc="resstr(0x7AB4, library(shell32.dll))"
```

- Contributed by @angelbruni


# Content
An attribute used to display content. Known to also work with [Themeable](#themeable---themeable), [ResourceString](#resourcestring---resstr), [Icon](#icon---icon), [DrawThemeBackground](#drawthemebackground---dtb).

**Example:**

This displays the icon 129 from NetworkExplorer.dll/NetworkExplorer.dll.mun.
```
<Button3d content="icon(129, sysmetric(49), sysmetric(50), library(NetworkExplorer.dll))"/>
```

- Contributed by @angelbruni


# Foreground
Used to set the text colour. Known to work with [AlphaRedGreenBlue](#alpharedgreenblue---argb), [GetThemeColor](#getthemecolor---gtc).

**Example:**
```
foreground="argb(255, 90, 103, 121)"
```

- Contributed by @angelbruni


# AlphaRedGreenBlue - argb()
Used to set the desired colour. Known to work with [Themeable](#themeable---themeable), [Foreground](#foreground), [Background](#background).

**Syntax:**
```
argb(alpha, red, green, blue)
```

**Example:**
```
argb(255, 90, 103, 121)
```

- Contributed by @angelbruni


# FontStyle
Allows for setting the style of the font.

- `None : 0x0 (0)`;
- `Italic : 0x1 (1)`;
- `Underline : 0x2 (2)`;
- `StrikeOut : 0x4 (4)`;
- `Shadow : 0x8 (8)`.

**Example:**

This will add a shadow to the text.
```
fontstyle="Shadow"
```

- Contributed by @angelbruni


# FontSize
Allows for setting the size of the font.

**Example:**

This will allow you to set the font size.
```
fontsize="9pt"
```

- Contributed by @angelbruni

 
# FontFace
Allows for setting the font.

**Example:**
```
fontface="Segoe UI"
```

- Contributed by @angelbruni


# Padding
Allows us to set the padding of an element. Known to work with [Themeable](#themeable---themeable), [Rect](#rect---rect).

**Example:**
```
padding="rect(2rp, 0rp, 0rp, 0rp)"
```

- Contributed by @angelbruni


# Rect - rect()
Allows us to set the size of each side of something. Known to work with [Themeable](#themeable---themeable), [GetThemeMargins](#getthememargins---gtmar), [Padding](#padding).

**Syntax:**
```
rect(left, top, right, bottom)
```

**Example:**
```
rect(2rp, 0rp, 3rp, 0rp)
```

- Contributed by @angelbruni


# Background
Used to set the background colour. Known to work with [Themeable](#themeable---themeable), [AlphaRedGreenBlue](#alpharedgreenblue---argb), [GetThemeColor](#getthemecolor---gtc), [DrawThemeBackground](#drawthemebackground---dtb).

**Example:**
```
background="argb(255, 90, 103, 121)"
```

- Contributed by @angelbruni


# Alpha
Allows us to set the alpha (transparency) of an element.

**Example:**
```
alpha="55"
```

- Contributed by @angelbruni


# Cursor
This attribute allows us to set the cursor that will show up when the cursor is in the element.

- `Arrow : 0x0 (0)`;
- `Hand : 0x1 (1)`;
- `Help : 0x2 (2)`;
- `No : 0x3 (3)`;
- `Wait : 0x4 (4)`;
- `SizeAll : 0x5 (5)`;
- `SizeNESW : 0x6 (6)`;
- `SizeNS : 0x7 (7)`;
- `SizeNWSE : 0x8 (8)`;
- `SizeWE : 0x9 (9)`;
- `IBeam : 0xa (10)`.

**Example:**
```
cursor="IBeam"
```

- Contributed by @angelbruni


# DrawThemeBackground - dtb()
For use of a `msstyles` image property. Known to be used with [Content](#content), [Themeable](#themeable---themeable), [Background](#background).

⚠️ The class, part, or state it reads from doesn't have to be a graphic. It's set by `BGTYPE:ENUM`. So you can have gradients (`horizontal`, `vertical`, and `radial`), `borderfill`, or `images`.

**Syntax:**
```
dtb(class, part, state)
```

- `class` - The class as defined in the theme's CMAP.
- `part` - A part of a class.
- `state` - The state of the part.

**Example:**

This will draw the background using the image located at `Explorer & Shell > Explorer > Items View > ListView > GroupHeader > <2>`:
```
background="dtb(ItemsView::ListView, 6, 2)"
```

- Contributed by @angelbruni


# GetThemeColor - gtc()
For use of a `msstyles` colour property. Known to be used with [Themeable](#themeable---themeable), [Foreground](#foreground), BorderColor, [Background](#background), SortColumn, Gradient.

**Syntax:**
```
gtc(class, part, state, id)
```

- `class` - The class as defined in the theme's CMAP.
- `part` - A part of a class.
- `state` - The state of the part.
- `id` - ID number.

**Example:**

This will make the text (or foreground) the color of the `TEXTCOLOR:COLOR` property in: `Explorer & Shell > Explorer > Items View > ItemsView`
```
foreground="gtc(ItemsView, 0, 0, 3803)"
```

- Contributed by @angelbruni


# GetThemeFont - gtf()
For setting the font with a `msstyles` property. Known to be used with [Font](#font), [Themeable](#themeable---themeable).

**Syntax:**
```
gtf(class, part, state, id)
```

- `class` - The class as defined in the theme's CMAP.
- `part` - A part of a class.
- `state` - The state of the part.
- `id` - ID number.

**Example:**

This will set the font defined by the `BODYFONT:FONT` property in `Buttons, Boxes & Controls > Buttons > Button > CommandLink`

⚠️ If the `id` isn't defined it will set the font defined by the `FONT:FONT` property instead.
```
font="gtf(TextStyle, 1, 0, 809)"
```

- Contributed by @angelbruni


# GetThemeMargins - gtmar()
For setting the margin with a `msstyles` property.

⚠️ This can be used for any property using a [Rect](#rect---rect) such as: `padding`, `margin`, and `borderthickness`.

⚠️ `rect()`'s values go (`left`, `top`, `right`, `bottom`) whereas in the msstyles it's (`left`, `right`, `top`, `bottom`).

**Syntax:**
```
gtmar(class, part, state, id)
```

- `class` - The class as defined in the theme's CMAP.
- `part` - A part of a class.
- `state` - The state of the part.
- `id` - ID number.

**Example:**

This will set the padding as defined by the `CONTENTMARGINS:MARGINS` property `Address, Breadcrumb & Search > Search > SearchBox > Basic > Normal > Active > Background`:
```
padding="gtmar(SearchBox, 1, 0, 3602)"
```

- Contributed by @angelbruni


# GetThemeMetrics - gtmet()
For setting the metrics with a `msstyles` property. Known to be used with [Width](#width), [Height](#height).

**Syntax:**
```
gtmet(class, part, state, id)
```

- `class` - The class as defined in the theme's CMAP.
- `part` - A part of a class.
- `state` - The state of the part.
- `id` - ID number.

**Example:**

This will set the width as defined by the `WIDTH:INT` property in `Buttons, Boxes & Controls > Buttons > Navigation > BackButton`:
```
width="gtmet(Navigation, 1, 0, 2416)"
```

- Contributed by @angelbruni


# DrawFrameControl - dfc()
**Syntax:**
```
dfc(parameter1, parameter2)
```

- `parameter1` - Unknown.
- `parameter2` - Unknown.

- Contributed by @angelbruni


# Themeable - themeable()
For using mssyles themed elements. Known to be used with [Content](#content), [Background](#background), [AlphaRedGreenBlue](#alpharedgreenblue---argb), [DrawThemeBackground](#drawthemebackground---dtb), [GetThemeColor](#getthemecolor---gtc), [GetThemeFont](#getthemefont---gtf), [Icon](#icon---icon), [Padding](#padding), [Rect](#rect---rect).

⚠️ When defining sizes in `themeable()` wrap in single quotes.

**Syntax:**
```
themeable(themed, classic)
```

- `themed` - Default value read from the msstyles.
- `classic` - Determines what value to use if a part is Aero styled or Classic styled. If a theme is applied it uses the first value, if you're using Windows Classic/Standard it uses the second value. It's best to leave as a hardcoded value.

**Example:**

The font will be the color defined by the `TEXTCOLOR:COLOR` property in `Explorer & Shell > Explorer > Items View > ItemsView`, however if this change is in a system DLL and windows classic was enabled, the font will be Window Text as defined in the control panel.
```
foreground="themeable(gtc(ItemsView, 0, 0, 3803), windowtext)"
```

- Contributed by @angelbruni

# valueWithHighContrastFallback - valueWithHighContrastFallback()
For using mssyles themed elements while respecting High Contrast. Known to be used with [Content](#content), [Background](#background), [AlphaRedGreenBlue](#alpharedgreenblue---argb), [DrawThemeBackground](#drawthemebackground---dtb), [GetThemeColor](#getthemecolor---gtc), [GetThemeFont](#getthemefont---gtf), [Icon](#icon---icon), [Padding](#padding), [Rect](#rect---rect).

⚠️ When defining sizes in `valueWithHighContrastFallback()` wrap in single quotes.

**Syntax:**
```
valueWithHighContrastFallback(themed, classic)
```

- `themed` - Default value read from the msstyles.
- `classic` - Determines what value to use if a part is Aero styled or Classic styled. If a theme is applied it uses the first value, if you're using Windows Classic/Standard it uses the second value. It's best to leave as a hardcoded value.

**Example:**

The element will have the background defined by the image texture in `Explorer & Shell > Explorer > Control Panel > ControlPanel > NavigationPane > NavigationPaneTop Background`, however if this change is in a system DLL and windows classic or high contrast was enabled, the font will be Window Text as defined in the control panel.
```
<element background="valueWithHighContrastFallback(dtb(CONTROLPANEL,1,3),window)"/>
```

- Contributed by @ImSwordQueen

# Width
Set the width of the element. Known to be used with rp, SystemMetric, [GetThemeMetrics](#getthememetrics---gtmet).

**Example:**
```
width="10rp"
```

- Contributed by @angelbruni


# Height
Set the width of the element. Known to be used with rp, SystemMetric, [GetThemeMetrics](#getthememetrics---gtmet).

**Example:**
```
height="10rp"
```

- Contributed by @angelbruni


# ShellExecute
Allows for opening executable programs.

**Example:**

This will open explorer.exe.
```
shellexecute="%windir%\\explorer.exe"
```

- Contributed by travis


# ShellExecuteParams
Allows use for opening a executable program with extra parameters. Must be used with `ShellExecute`.

**Example:**
```
ShellExecuteParams="shell:::{78F3955E-3B90-4184-BD14-5397C15F1EFC}"
```

- Contributed by travis


# NavigationTargetRoot
Allows for navigating to a directory.

**Example:**

This will open the %windir%\System32 directory.
```
navigationtargetroot="%windir%\\System32"
```

This will open the Display Control Panel page.
```
navigationtargetroot="Microsoft.Display"
```

- Contributed by travis, Brawllux


# NativationTargetRelative

**Example:**

This will take you to the pageWallpaper child page (also needs to be mentioned in the DLL's XMLFILE part).
```
navigationtargetrelative="pageWallpaper"
```

- Contributed by Brawllux


# Graphic
Allows for use of bitmap resources in any binary DirectUI can read, seems like a duplicate of `ResourceBitmap`.

**Syntax:**
```
graphic(resource_id, parameter2, parameter3, parameter4, parameter5, parameter6, parameter7, library(binary))
```

`resource_id` - The ID of the bitmap resource in the binary.

`parameter2` - Unknown.

`parameter3` - Unknown.

`parameter4` - Unknown.

`parameter5` - Unknown.

`parameter6` - Unknown.

`parameter7` - Unknown.

`library(binary)` - Binary name.

**Example:**
```
graphic(102, 2, -1, 0, 0, 0, 0)
```

- Contributed by travis


# Animation
Allows us to set an animation for an element

⚠️ Still Researching.

**Syntax:**
```
animation="parameter1|parameter2|parameter3|parameter4"
```

`parameter1` - Alpha

`parameter2` - Unknown.

- `None : 0x0 (0)`;
- `Linear : 0x1 (1)`;
- `Log : 0x2 (2)`;
- `Exp : 0x3 (3)`;
- `S : 0x4 (4)`.

`parameter3` - Animation Speed most likely.

- `VeryFast : 0x10000 (268435456)`;
- `Fast : 0x20000000 (536870912)`;
- `MediumFast : 0x30000000 (805306368)`;
- `MediumSlow : 0x50000000 (1342177280)`;
- `Medium : 0x40000000 (1073741824)`.
- `MediumSlow : 0x50000000 (1342177280)`;
- `Slow :  0x60000000 (1610612736)`;
- `VerySlow : 0x70000000 (1879048192)`;

`parameter4` - Delay before animation starts.

- `DelayShort : 0x10 (16)`;
- `DelayMedium : 0x20 (32)`;
- `DelayLong : 0x30 (48)`;

`parameter5` - Unknown.

`parameter6` - Unknown.

`parameter7` - Unknown.

`parameter8` - Unknown.

`parameter9` - Unknown.

**Example:**
```
alpha|s|slow|delayshort
```

- Contributed by Olivia


# ShadowIntensity
Sets the intensity for the shadow applied with fontstyle="Shadow"

**Syntax:**
```
shadowintensity="parameter1"
```


`parameter1` - The shadow intensity, a value between 0-200

⚠️ If not set, a default value (which is unknown) will be used.

**Example:**
```
<element shadowintensity="75" fontstyle="Shadow"/>
```

- Contributed by neptuneen


# Visible
Determines whether an element/content is visible or not

**Syntax:**
```
visible="parameter1"
```

`parameter1` - Bool (True or False)

**Example:**
```
<element visible="true"/>
```

- Contributed by Olivia



# AnimationStrip
Play a simple looped animation in DirectUI [(example)](https://discord.com/channels/1140065636857421945/1202671741969760277/1269663947435278407)

https://github.com/user-attachments/assets/6f85694a-3add-4a4e-9998-2a84ff7f3ccf

**Resource example:**
The resource must be a 32bit bitmap (bitmap with alpha channel, even it doesn't have any transparent part). Its layout must be horizontal with the same width for each frame. See an attachment for example bitmap below

https://github.com/angelbruni/windows-dui-docs/raw/refs/heads/main/Bitmap111.bmp

**Example:**
```
<AnimationStrip content="resbmp(image_id,3,0,image_width,image_height,0,0,library(binary))" framewidth="25" frameduration="80" frameindex="0"/>
```


**content**

_(Since it's kinda different with [resbmp](#resourcebitmap---resbmp) above. It's better to describe its meaning again)_

`image_id` - The ID of the bitmap resource in the binary

`3` - Unknown value. Leave it to 3 or your animation will have wrong colors. "Supposed to be the sizing type for your image."
  - Using `6` would make it blend with the color that is behind the element
  - `4` is suitable if your element is supposed to be a container for the entire app
  - `2` and `3` are suitable if your image is in "content" instead of background
  - `7` is suitable if you want to make it have transparency while keeping it "background" instead of using content, its also suitable for specifying sizing margins using borderthickness

`0` - Unknown value

`image_width` - Bitmap width. Best to leave it 0

`image_height` - Bitmap height.

`0` - Unknown value

`0` - Unknown value. Leave it to 0 or your animation will have wrong colors.

`library(binary)` - Binary name (Must be a DLL or exe in System32)

**framewidth**

Width of each frame. **Do not use rp for dpi-awareness in here or it will break your animation on hi-dpi**
_(**Not an element's width.** You must specify it with [width](#width))_

**frameduration**

Duration of each frame in milliseconds.

**frameindex**

Defines where the first frame should start playing at. Set it to `0` for the first frame.

**play**

`true/false` - Play or pause your animation. Better use it with [if](#if-).

- Contributed by Vaporvance, OjasK


# Font
Font is a shorthand property for FontSize, FontWeight, FontStyle,FontFace,FontQuality

**Syntax:**
```
<element font="font_size;font_weight;font_style;font_face;font_quality"/>
```

`font_size` - Font size in pt.
- See [FontSize](#fontsize).

`font_weight` - Font weight.
- `DontCare : 0x0 (0)`
- `Thin : 0x64 (100)`
- `ExtraLight : 0xc8 (200)`
- `Light : 0x12c (300)`
- `SemiLight : 0x15e (350)`
- `Normal : 0x190 (400)`
- `Medium : 0x1f4 (500)`
- `SemiBold : 0x258 (600)`
- `Bold : 0x2bc (700)`
- `ExtraBold : 0x320 (800)`
- `Heavy : 0x384 (900)`

`font_style` - Font style. 
- see [FontStyle](#fontstyle).

`font_face` - Font face. 
- see [FontFace](#fontface).

`font_quality` - Font quality. Very very optional.
- `Default` - Follow system setting.
- `NonAntialiased` - Force Non Anti-Aliased. Just like you turn off font smoothing.
- `Antialiased` - Force Anti-Aliased. This is different with ClearType.
- `ClearType` - Force ClearType.
- `ClearType-Natural` - Force ClearType-Natural. This is different with ClearType.

**Example:**

This will set the font to 9pt Segoe UI Bold with no styling
```
<element font="9pt;Bold;Normal;Segoe UI;ClearType"/>
```

You can also skip some properties too.

This will set the font to 12pt Arial
```
<element font="12pt;;;Arial"/>
```

- Contributed by Vaporvance


# WindowActive
`true/false` - Use with [if](#if-) to check if window is active or not. Has no effect when used in main element.

**Example:**

This will turn an element background to red if window is active, and yellow if not active
```
<if WindowActive="true">
    <element background="red"/>
</if>
<if WindowActive="false">
    <element background="yellow"/>
</if>
```

- Contributed by Vaporvance


# MinSize
Defines minimum width and height of an element

_(Yes we don't have MaxSize for some reason)_

**Syntax:**
```
minsize="size(width,height)"
```

`width` - Minimum width
`height` - Minimum height

**Example:**
```
<element minsize="size(60rp, 40rp)"/>
```

- Contributed by Vaporvance


# Typography
Defines special attributes for rich text elements.

**Syntax:**
```
typography="ss01=1,dlig=1,kern=1"
```

`ss01=1` - Stylistic set. With Segoe UI, it uses the Windows Vista/7 version without tampering with the system files. Stylistic sets may vary with different TTF files.
`dlig=1` - Special ligatures found in some typefaces, Segoe UI includes **ff**, **fi**, **fl**, **ffi**, **ffl**, **ft**, **st** as well as **Start** for Segoe UI Light.
`kern=1` - unknown

**Example:**
```
<RichText typography="ss01=1,dlig=1,kern=1"/>
```

- Contributed by WinExperiments
