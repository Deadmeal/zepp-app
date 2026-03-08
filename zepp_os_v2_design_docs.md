# Zepp OS v2 Design Specifications — Complete Documentation Extraction

> **Source:** https://docs.zepp.com/docs/v2/designs  
> **Version:** v2 (Zepp OS Developers Documentation)  
> **Extracted:** March 2026

---

## Table of Contents

1. [Zepp OS Design Specifications — Overview](#overview)
2. [Design Concept](#design-concept)
   - [Design Values](#design-values)
   - [Design Principles](#design-principles)
3. [Structure](#structure)
   - [Page Types](#page-types)
   - [Switching Pages](#switching-pages)
   - [Interface Framework](#interface-framework)
4. [Interaction](#interaction)
   - [Screen Touch Control](#screen-touch-control)
   - [Physical Buttons](#physical-buttons)
   - [Definition of the keyType Field](#keytypefield)
   - [Digital Crown](#digital-crown)
5. [Visual](#visual)
   - [Color](#color)
   - [Font](#font)
   - [Icons](#icons)
   - [Illustrations](#illustrations)
   - [Animations](#animations)
6. [Templates](#templates)
   - [List](#list)
   - [Pop-up Windows](#pop-up-windows)
   - [Cards](#cards)
   - [Empty Pages](#empty-pages)
7. [Elements](#elements)
   - [Text](#text)
   - [Progress](#progress)
   - [Loading](#loading)
   - [Charts](#charts)
   - [Status Bars](#status-bars)
   - [Page Indicators](#page-indicators)
   - [Operations](#operations)
   - [Input](#input)
8. [Watchface Design Specifications](#watchface-design-specifications)
   - [Introduction](#watchface-introduction)
   - [Composition](#watchface-composition)
   - [Safe Area](#watchface-safe-area)
   - [Screen Off Mode](#screen-off-mode)
9. [Internationalization](#internationalization)
   - [Introduction](#i18n-introduction)
   - [Languages](#languages)
   - [Interface Layouts](#interface-layouts)
   - [Visual Graphics](#visual-graphics)
   - [Regional Standards](#regional-standards)
10. [Accessibility Design](#accessibility-design)
    - [Introduction](#accessibility-introduction)
    - [Color](#accessibility-color)
    - [Contrast Ratio](#contrast-ratio)
11. [Designer's Self-Checklist](#designers-self-checklist)
12. [Resource Downloads](#resource-downloads)

---

## 1. Zepp OS Design Specifications — Overview {#overview}

Zepp OS is a health management system for smart watches and wearable devices that aims to create products and user experiences based on the concept of **"creating health value for users"**. At the same time, on the upper layer of the operating system, through its "lightweight" application development framework (ZMPF), Zepp OS supports the development of mini program applications.

To help businesses build applications that offer excellent quality and consistent experience, this guide combines design and technology to provide necessary guidance and resources as a means to reduce redundant production costs, improve design and development efficiency, and create an intelligent health management system that enables value symbiosis.

**Design specifications:** We provide complete design guidelines and best practices that cover concepts, structure, interaction, vision, elements, customization, internationalization, and design self-checklists to help businesses produce high-quality product design solutions in an efficient manner.

**Resource downloads:** We provide the latest Figma design component library and font resources.

---

## 2. Design Concept {#design-concept}

### 2.1 Design Values {#design-values}

Design values are the core of our design system. They provide a guideline and direction for Zepp OS product design and all design activities are carried out based on these design values.

#### Natural

Natural design connects the real-world experience with product design by arousing user cognition, so that users can quickly understand and feel related, which ensures a comfortable experience while using the wearable device.

**Natural recognition:** Express elements and content presented on the smart wearable interface using the essence of natural elements, including visual, auditory, tactile, and other means that conform to the laws of nature, such that they are self-evident and easy to understand. This helps to reduce the user's cognitive load and create a harmonious, visually pleasurable, and natural product experience.

**Natural interaction:** Choose recognition over recall. System operation must be consistent with the process, logic, and habits in real life. Strive for high adaptability to the user's daily habits by means of scenario definition, behavior analysis, cloud computing, and AI algorithms. Give users the sense that they are in full control of the interface. Improve natural interaction and help users understand and use the product with ease.

#### Simple

Zepp OS is a system designed for wearable devices. Therefore, product design should consider and utilize device features, analyze usage scenarios, focus on core features, and be suitable for wearers, thereby providing them with a simple and lightweight user experience.

**Simple interface:** The element style should be simple and straightforward, the interface structure should be clear with proper information hierarchy, the core features should be distinct, and the key information should be highlighted to help users acquire information with higher efficiency.

**Simple operation:** Operations on smart wearable devices should be adapted to small screens and use short paths. Interfaces should be as simple as possible with proper information hierarchy, so that users can quickly complete tasks through simple operations.

**Easy to understand:** Consider the usage scenarios and introduce advanced features through gradual guidance and clear demonstrations to reduce the user's learning burden and cognitive load, so that they can quickly understand and make decisions.

#### Symbiosis

As a system running on personal wearable devices, Zepp OS is closely connected with users. In product design, consider user requirements, product values and technological development, and integrate them into one system so that they can develop together.

**Experience symbiosis:** Wearable devices create a more intimate connection with the wearer through physical devices. To provide better user experience, hardware and software should complement each other and work together. A good system design considers the development of hardware and software and reduces the physical boundaries between them, giving users a better experience and making the product more versatile and competitive.

**Value symbiosis:** The opinions, pain points, preferences, and requirements of users are the core of product design. Designers should think about design in a systematic way, gain insight into the value of product features, provide services to users, establish a connection between value and demand, and allow product value to be discovered. Efforts should be made to help users pay more attention to themselves and improve their health and quality of life.

---

### 2.2 Design Principles {#design-principles}

Design principles are concrete and feasible guidelines and tips for practicing design values. They describe the benchmarks and design constraints in the design process.

#### Friendly

**Friendly feedback:** The interface is under the user's control. Offer appropriate feedback through emotionally considerate design to soothe the user's negative emotions and promote positive emotions.

**Friendly guidance:** Use timely notifications and guidance to help users better complete tasks and solve problems.

**Friendly and universal:** Focus on inclusiveness to ensure barrier-free and international designs. Pay attention to the user experience of key groups and in special scenarios while considering the requirements of most users. Expand product target groups and allow more users to easily and efficiently use the product.

#### Light

**Light interface:** Keep the interface concise and clear at all times and remove visual clutter, so that users can focus on truly useful information.

**Light layering:** Reflect the layering and spatial relationship between elements and establish cognitive continuity between the user and the interface.

**Light operation:** Provide lighter operation and effortless cognition to vitalize the interface.

**Light process:** In feature process design, use short paths where possible to improve feature use efficiency.

#### Efficient

**Efficient design:** System design is the product of labor division and cooperation. Explore design rules and modular design ideas, provide abstract rules, components and patterns for partners, enhance the flexibility and maintainability of interface design, reduce unnecessary design elements, maintain system consistency, and improve design efficiency.

**Efficient use:** Always pay attention to the effectiveness of product use, focus on specific user requirements, and provide users with a flexible and satisfying individual experience.

---

## 3. Structure {#structure}

### 3.1 Page Types {#page-types}

| **Page Type** | **Priority** | **Typical Page Example** |
|---|---|---|
| Permanent | P0 | Watch face synchronization |
| Floating layer — important reminders | P1 | Alarm clock reminders |
| Floating layer — normal pop-up windows | P1 | Battery life warnings |
| Floating layer — message reminders | P1 | Goal reached reminders and notifications |
| Floating layer — short reminders | P1 | WeChat, Alipay successfully enabled, Watchface synchronized successfully |
| Basic | P2 | Weather |
| Watchface | P2 | Watch face, quick access apps |
| Basic — In Progress status | P2 | Timer in use |

#### Usage Specifications

Pages of the same priority level are arranged in chronological order; pages that appear earlier will be overlaid with pages that appear later, and pages of higher priority levels will not be overlaid with pages of lower priority levels.

Pages that do not support right-swipe exit will appear as overlaid. For the exit animation, see Overlay Pages.

---

### 3.2 Switching Pages {#switching-pages}

#### Same-level Pages

Refers to switching between pages of the same priority level, such as swiping left and right to switch between quick access apps and swiping up and down to turn pages in an app.

#### Parent-child Pages

- Access deeper levels of content in the app's hierarchy by going from parent pages to child pages.
- Go through an ordered process page, such as setting height and weight.
- Go from one page to any other page in the app, such as from a Watchface to a page within an app.
- Return from a child page to the parent page.

#### Overlay Pages

This is how a permanent page appears.

---

### 3.3 Interface Framework {#interface-framework}

The interface framework diagram (visible in the documentation as an image) shows the following navigation structure centered on the **Watch Face**:

- **Control Center** — accessible by swiping down from the top edge
- **App List** — accessible by pressing the side/upper button
- **Negative Screen** — accessible by swiping right from the watch face
- **Widget 1, Widget 2, Widget 3** — accessible by swiping horizontally
- **Notification** — accessible by swiping up from the bottom edge
- **Quick Start** — accessible via dedicated button or gesture

The watch face is the central hub from which all major areas of the interface are accessible.

---

## 4. Interaction {#interaction}

### 4.1 Screen Touch Control {#screen-touch-control}

Screen touch control allows users to interact with screen elements using touch and gestures. Users can apply varying levels of pressure to the touch screen to access other features. An app can be opened when people touch and press the app icon.

#### Design Principles

People generally expect the following standard gestures to behave the same in every Zepp OS experience. Avoid using standard gestures to perform non-standard actions. Redefining the meaning of standard gestures adds complexity and can lead to confusion.

#### Rules for Use

**Tap:** A tap selects a button or an item.

**Swipe:** A swipe displays the content of another screen. Swiping in different directions can have different effects:
- Downward swipes in a content area can display the context.
- In a page-based app, horizontal swipes can display the next or previous screen.
- Vertical swipes can scroll the content on the current screen.
- Two-finger swipe/one-finger swipe in response to the same event is supported.

**Edge swipe:** Swiping from the edge of the screen can reveal shortcut features.
- On system screens, swiping down from the top edge displays Control Center. Swiping up from the bottom edge displays Notification Center.
- Right-edge swipes navigate back to a parent screen.

**Firm press and long press:** In Zepp OS, users can press firmly on the screen to change the Watchface.

---

### 4.2 Physical Buttons {#physical-buttons}

Wearable devices often have multiple physical buttons, also known as "crown buttons". There has always been at least one button on a Zepp OS device, namely the power button. In addition to this, there may be multiple multifunction buttons (or none).

#### Design Principles

- Provide visual feedback in response to physical button interactions.
- Avoid defining multiple button interactions to minimize confusion.

#### Naming Rules

Watches connected to Zepp OS display names on the user interface when the name of the physical button is not printed on the hardware. The product definition principles are based on the following:

- If the button name is marked on the printing of the hardware, use the name printed on the hardware, such as: Blanc Select or Blanc Back.
- If the printing on the hardware does not indicate the name of the button, the position of the button on the watch is used to mark the name of the button. The feature of the physical button as defined by the specific software is not used as the button name.

**Single button watch:** Name: Side Button①

**Double button watch:**

| **A name that expresses the related feature when a specific operation (ECG touch, tap, long press, double tap, triple tap) is performed** | **The name used to express the rotation feature** |
|---|---|
| Upper Button① | Crown① |
| Lower Button② | Lower Button② |

**Triple button watch:** Names: Upper Button①, Middle Button②, Lower Button③

**Four button watch:**

| **Left button names** | **Right button names** |
|---|---|
| Upper Button① | SELECT③ |
| Lower Button② | BACK④ |

#### Rules for Use

Allow applications and a specific interface to have the ability to define physical button features (including: tap, long press for 1 second, and long press for 5 seconds).

- **Non-JS applications:** have the permission to intercept all physical button operations.
- **JS applications:**
  - Tap: do not have the permission to intercept physical button operations.
  - Long press for 1 second or 5 seconds: have the permission to intercept all physical button operations.

**Single button watch — operation table:**

| **Operation** | **Triggered Event** |
|---|---|
| Press the side button | Go to the application list. Press the upper button again to jump to the Watchface |
| Press and hold the side button for 1 second | Quick start default online voice |
| Press and hold the side button for 5 seconds | Power-off/Reboot |
| Press and hold the side button for 12 seconds | Force reboot |

**Double button watch — operation table:**

| **Operation** | **Triggered Event** |
|---|---|
| Press the upper button | Jump to the application list. Press the upper button again to jump to the Watchface |
| Press and hold the upper button for 1 second | Quick start default online voice |
| Press and hold the upper button and the lower button for 5 seconds | Power-off/Reboot |
| Press and hold the upper button for 12 seconds | Force reboot |
| Press the lower button | Quick start-up (default) |

**Four button watch — operation table:**

| **Interface location → Button ↓ interaction ↘** | **Watch faces** | **Stopwatch & ongoing workout** | **Dialog box** | **Majority of other interfaces** |
|---|---|---|---|---|
| Tap = press and release quickly (SELECT) | Quick start-up: default workout list | Pause/resume | Right button | Go to next level/interact with focused item |
| BACK | App List | Record lap | Left button | Back to previous level |
| UP | Control center | View previous page/view more above/ +1 | — | — |
| DOWN | Shortcut Cards | View next page/view more below/ -1 | — | — |
| Press and hold SELECT for 5 seconds | Select power-off or reboot | — | — | — |
| Press and hold SELECT for 12 seconds | Force reboot | — | — | — |
| Press BACK for 1 second | Screen off | — | No operations | — |
| Press and hold UP without releasing | Page up quickly (if applicable) | — | — | — |
| Press and hold DOWN without releasing | Page down quickly (if applicable) | — | — | — |

#### Response Speed

**Double button watch — supports tap, long press, and super long press:**

Response action definitions (Red = screen off, Blue = screen on):

| **Response Action** | **Response Time Definition** |
|---|---|
| Tap | ①Press ②Lift ③Response to screen on ④Response to tap ⑤Response to long press |
| Long press | ①Press ②Lift ③Response to screen on ④Response to long press |
| Super long press | ①Press ②Lift ③Response to screen on ④Response to long press ⑤Response to super long press |

**Single button watch — supports tap, double tap, long press, and super long press:**

Response action definitions (Red = screen off, Blue = screen on, Gray = both states):

| **Response Action** | **Response Time Definition** |
|---|---|
| Tap | ①Press ②Lift ③Response to screen on ④Response to tap |
| Double tap | ①Press ②Lift ③Response to screen on ④Response to double tap in region |
| Long press | ①Press ②Lift ③Response to screen on ④Response to long press |
| Super long press | ①Press ②Lift ③Response to screen on ④Response to long press ⑤Response to super long press |

---

### 4.3 Definition of the keyType Field {#keytypefield}

You can use this field to determine the definitions of the watch buttons, including the following:

- Number of buttons
- Whether crown exists
- Mode type distinction (Normal/Workout)

**Naming convention:**

```
{button mode}_{number of buttons} // {whether crown exists, 1 means yes, 0 means no}
```

For example, `sport_21` indicates that "the number of buttons is 2", "crown exists", "button mode: workout".

- **Button mode:** Normal, Workout
- **Number of buttons:** 1 (single-button), 2 (double-button), 4 (four-button)
- **Whether crown exists:** 0 (no), 1 (yes)

| **Name** | **Type: English** |
|---|---|
| Single button watch / crown exists / normal mode | normal_11 |
| Single button watch / no crown exists / normal mode | normal_10 |
| Double button watch / crown exists / normal mode | normal_21 |
| Double button watch / no crown exists / normal mode | normal_20 |
| Double button watch / crown exists / workout mode | sport_21 |
| Double button watch / no crown exists / workout mode | sport_20 |
| Four button watch / no crown exists / workout mode | sport_40 |

**Notes:**
- Default button mode for a sport watch: Workout
- Default button mode for a non-sport watch: Normal
- The button mode will be added later, so there will be two button modes supported in the double button watch.

---

### 4.4 Digital Crown {#digital-crown}

The Digital Crown is the primary hardware input for watch devices. As people rotate the Digital Crown, it generates information you can use to enhance or facilitate interactions with your app, like scrolling or operating standard or custom controls. You can use a set of methods to track user interactions with the Digital Crown and receive notifications when the user rotates the crown or when the rotation stops.

#### Design Principles

- As people rotate the Digital Crown slowly, the page content should move smoothly and with animation between every two page refreshes.
- When the page stops, the animation deceleration curve after stopping should be determined according to the acceleration before the crown stops scrolling.
- The scrolling effect of all pages should be roughly the same on the level perceived by the user.
- Accidental touch prevention is required for all rotation interactions: When the user has an obvious intent to rotate in the app list, a response is required (see the table below for the definition of the obvious rotation intention parameter), and the page should not move when there is no obvious rotation intention.

#### Rules for Use — Dual Accidental Touch Prevention Logic

**First layer: accidental touch prevention that is not displayed to the user**

The value reported from when the digital crown is at rest (no value reported for 1 second) to when it starts to rotate: The first time, only after there are changes in the value report for **20 consecutive cycles (16 ms per cycle)** will the input be displayed to the user on the page and digital crown-related responses engage (e.g. list rotation and long page scrolling).

**Second layer: accidental touch prevention that is displayed to the user**

When the rotation passes first-layer screening, the second layer of accidental touch prevention logic is triggered, and different accidental touch prevention effects are used according to different control types. Only when there is a clear intention to rotate the crown can the user trigger the corresponding rotation effect of the page. Otherwise, rotation effect processing should not be engaged.

> For example: When the list page is rotated, which satisfies the first layer logic but does not satisfy the second layer logic, the effect displayed on the page is a slight jump repeated in this list item, and the page will not rotate to the next list item.

---

## 5. Visual {#visual}

### 5.1 Color {#color}

Color is an intuitive way for users to perceive interface information and product features. Zepp OS's color system originates from our **"natural"** design value and follows the law of color changes in nature. The color, light, and shadow characteristics of **Magic Hour** are extracted to obtain different types of color palettes and guide and standardize color application scenarios.

#### Design Principles

Fully understand the psychological effects of different colors and use colors following the basic principles of color psychology. In terms of color matching, use a global accent color to give each page consistency and familiarity. At the same time, we recommend testing colors in different usage scenarios to improve interface usability.

#### Color Types

**System colors** — Colors for key content and information, alerts, controls, base graphics, and so on.

Usage examples:
- ① Switch
- ② Delete button

**Text colors** — The color of text content in titles, subtitles, descriptions, buttons, and other elements.

**Secondary colors** — Data chart colors, special colors within features, etc.

#### Color Status Changes

Change the color of page elements based on the properties or states of page elements, such as tapped state and disabled state.

For a control element in a **"tapped state"**, when the tap action is triggered, the overall color brightness of the control element is reduced by **40%**. After the tap action is completed, the color returns to the normal state.

- ①② List: Normal state
- ③④ List: Tapped state
- ①②③ Button: Normal state
- ④⑤⑥ Button: Tapped state

For a control element in the **"disabled state"**, the overall color brightness of the control element is reduced by **30%–50%**. At the same time, for controls in the highlighted state, replace the highlight color with a grayscale color.

- ① Radio button list: Normal state
- ② Radio button list: Disabled state

#### Color Availability

To ensure the readability of information and the integrity of the visual element display, follow these principles when using colors:

- **Avoid excessive use of low grayscale colors** (RGB values between 1 and 46). Make sure that the RGB value is not between 1 and 46.
- **Avoid gradients with too great a span.** At the same time, we recommend testing the colors used on a real device to ensure correct color display.
- The recommended **color contrast ratio** between foreground and background content is **≥ 3:1**. For more information, see Accessibility Design.
  - ① Button text : button background = 12.63 (acceptable)
  - ② Button text : button background = 1.74 (not acceptable)
  - ③ The contrast ratio between the foreground content and the background should be equal to or greater than 3:1

#### Color System Reference (from visual tables on the page)

The color system includes named semantic color tokens:

- `color_sys_key` — Key/accent color (used for emphasis buttons, selected states)
- `color_sys_item_bg` — Item background color (used for default button backgrounds, slider backgrounds)
- `color_sys_normal_graphic` — Normal graphic/bar color
- `color_text_title` — Title text color
- `color_text_button` — Button text/icon color
- `color_text_link` — Link/text button color

---

### 5.2 Font {#font}

Text is the most direct and clear way of expressing information, and font directly determines whether the text information can be conveyed correctly and accurately. Fonts distinguish the layer and priority of information through the differences in font size, font weight, capitalization, and font style.

The main font used by Zepp OS is **Noto Sans**. Usage specifications for special fonts are described in the Special Fonts section below.

#### Font Size

Based on the results of user survey, the best reading experience occurs in different scenarios when the viewing distance from the wearable device falls within the range of **25 cm–50 cm** and the screen subtends a visual angle of **5 minutes of arc** at the eye.

Based on the Snellen theory, it has been deduced that on a 1.45-inch AMOLED screen with a display resolution of 480×480 pixels and a pixel density of 331 PPI, the calculation formula for the minimum font size for the Zepp OS main font is:

> Caption1 = 0.0143 × 331 × 5 = 23.6665

Rounding up to the nearest integer gives us **24px**, so 24px is the minimum size for the main font on this screen. To ensure the readability of text, use this formula to calculate the minimum font size for devices that have different screen sizes.

**Font style sizes by device:**

| **Font Style Name** | **Round Screen Device 480** | **Round Screen Device 466** | **Square Screen Device 390** |
|---|---|---|---|
| Caption2 | 24 | 23 | 24 |
| Caption1 | 28 | 27 | 28 |
| Subheadline | 32 | 31 | 32 |
| Body | 36 | 35 | 36 |
| Title | 40 | 39 | 40 |

A typographic scale is a progression of font sizes that grow by the same ratio. Use different sets of typographic scales to fit different screen sizes. We use **arithmetic progression** to define font sizes in a typographic scale, so as to distinguish the information layer of system content and offer a more comfortable and smooth reading experience.

#### Text Box Height Calculation Rules

A text box is a container that wraps text content. Calculation rule for the height of a line of text:

> **line height = font size + 10**

#### Special Fonts

**DIN1451** — Use `DIN1451MittelschriftAlternat` for special digits.

**ZEPP OS NUMBER** — Use the ZEPP OS NUMBER font to fit the screen display during workout and provide a better reading experience.

#### Font Usage Rules

- Avoid using text smaller than 24 in interface content.
- Use special digit fonts for prominent large digits.

---

### 5.3 Icons {#icons}

Icons are specific graphics that guide the user with information. Zepp OS provides various icon elements to suit applications in different scenarios. This specification lists the usage scenarios, icon composition, graphic modeling, icon size, resource output, and other rules to guide the use of icon elements.

#### Design Principles

Zepp OS icons follow the **"lightweight"** and **"friendly"** design concepts. Use simple geometric configurations in modeling, simplify redundant details, ensure recognizability, and convey meanings clearly. Avoid straight edges and sharp corners in details, and use curves that are curvature continuous to convey natural beauty.

#### Icon Types

**App Icons**

An application icon should clearly and transparently convey its feature/brand/service information, and the design style should follow Zepp OS system application icons. Provide resources in multiple sizes based on the requirements of this specification to ensure that the icons are suitable for mobile devices, mobile application stores, and other scenarios.

- The application icon as a whole should be **round**, with a size of **124×124px**, and a blank and transparent safe area should be reserved inside (2px on the top, bottom, left, and right).
  - ① App icon content size
  - ② Transparent safe area
  - ③ App icon final size

- The app icon consists of a **main graphic** and a **background image**.
  - ① Main graphic
  - ② Background image

- The size of the app icon's main graphic is **80×80px**, and generally the drawing area is kept at **70×70px**. If the graphic needs additional visual weight to ensure consistency with other icons, the drawing area can be extended to the reserved area (note: in any case, the graphic should remain within the 80×80px range).
  - ① Basic drawing area of the icon body
  - ② Reserved area of the icon body
  - ③ Actual size of the icon body
  - ① The size of the icon body should not exceed 80×80px.

- The background image of the icon is circular, with a size of **124×124px**, and a blank and transparent safe area should be reserved inside (2px on the top, bottom, left, and right).

- **Do not use non-circular background images.**
- **Avoid using a solid black background image, transparent areas, and transparency.**
  - ① Do not use a solid black background image.
  - ② The background image should not contain transparent areas.
  - ③ Do not use transparency.
- The main graphic of an app list icon should not exceed the background image area.
- The icon resource should output an image in **PNG format** with a blank transparent safe area.

**App icon resource output sizes:**

| **Device Resolution** | **App Icons** | **Store Icons** |
|---|---|---|
| 480×480px | 124×124px | 240×240px |
| 466×466px | 124×124px | 240×240px |
| 454×454px | 124×124px | 240×240px |
| 390×450px | 124×124px | 240×240px |

Note: The icon needs to contain a blank and transparent safe area (2px on the top, bottom, left, and right). Format: a PNG image surrounded by a blank and transparent area.

**General Feature Icons**

Feature icons are mainly used to communicate system or feature information and indicate status information. Common feature icons support regular size, medium size, and ultra-small size.

Usage examples:
- ① Settings page: List icon (regular size)
- ② Temperature page: Thermometer icon (regular size)
- ① Sun and moon page: Moonrise/sunset time icons (medium size)
- ② Pre-workout page: Heart rate icon (medium size)
- ① Call record card: Outgoing call icon (ultra-small size)
- ② Event reminder card: Location icon (ultra-small size)

**General feature icon resource output sizes:**

| **Device Resolution** | **Regular Size** | **Medium Size** | **Ultra-Small Size** |
|---|---|---|---|
| 480×480px | 64×64px | 52×52px | 32×32px |
| 466×466px | 63×63px | 51×51px | 32×32px |
| 454×454px | 61×61px | 50×50px | 31×31px |
| 390×450px | 64×64px | 52×52px | 32×32px |

Note: The icon needs to contain a blank and transparent safe area (2px on the top, bottom, left, and right). Format: a PNG image surrounded by a blank and transparent area.

**Button Icons**

Button icons are used to represent actions and guidance for a specific operation button. Button icons support regular size, medium size, small size, and ultra-small size.

Usage examples:
- ① Refresh button icon (regular size)
- ② Confirm button icon (regular size)
- ③ Backspace button icon (regular size)
- ① Delete button icon (regular size)
- ② Hang Up button icon (regular size)
- ① Add button icon on the right side of a list (medium size)
- ② Download button (medium size)
- ① Watch face edit button icon (small size)
- ② Explanation button icon at the bottom of a page (small size)
- ① Explanation button icon after text information (ultra-small size)

**Button icon resource output sizes:**

| **Device Resolution** | **Regular Size** | **Medium Size** | **Small Size** | **Ultra-Small Size** |
|---|---|---|---|---|
| 480×480px | 64×64px | 52×52px | 40×40px | 32×32px |
| 466×466px | 63×63px | 51×51px | 39×39px | 32×32px |
| 454×454px | 61×61px | 50×50px | 38×38px | 31×31px |
| 390×450px | 64×64px | 52×52px | 40×40px | 32×32px |

Note: The icon needs to contain a blank and transparent safe area (2px on the top, bottom, left, and right). Format: a PNG image surrounded by a blank and transparent area. We recommend expanding the tappable area for smaller icon buttons, and the size of the drawing area should not be less than 52px.

---

### 5.4 Illustrations {#illustrations}

As an important part of the product's visual experience, illustrations can express information graphically, improve legibility and aesthetic experience to a certain extent, and shape the brand image.

#### Design Principles

Zepp OS illustrations follow the **"lightweight"**, **"friendly"**, and **"effective"** design principles. Use lightweight and concise graphics, reduce excessive modeling combinations, convey friendly and appropriate emotions, and express the meaning in a clear and easy-to-understand manner to ensure efficient operation for the user.

#### Types

**Illustrations of Status Descriptions**

The type of illustration that clarifies the state of the page, with certain illustrative, soothing and decorative qualities.

**User-guided Illustrations**

Guide the user to carry out the corresponding operation or explain the current way of using the function, with certain explanatory and guiding nature. To ensure the clarity of the illustration, user-guided illustrations often use dynamic representations.

**Notification and Reminder Illustrations**

Communicate to users the content of application notifications with time information or physical condition alerts, with a certain motivational, decorative and illustrative nature.

**Third-party App Illustrations**

The illustration performance of third-party apps is relatively flexible. Appropriately add colors, modify the shapes, and increase the emotional and brand elements based on the brand features of third-party apps.

#### Rules for Use

- The basic visual style of system illustrations is **white graphics** ①.
- Use **gray graphics** ② in empty page status illustrations for apps.
- For the empty pages of quick access apps (indicating that connection to mobile application is required for operation), use **color graphics**. To ensure that the user understands, the app icon is usually used ③.
- In guidance and feedback illustrations with animations, you can add full-screen animations to decorate the background layer.
- Consider the presence of status bars for square screen devices. No titles are required for page illustrations within an app.
  - ④ Basic visual style of system illustrations in a square screen device
  - ⑤ App empty page illustration in a square screen device

#### Visual Specifications

The size of the main slice of the illustration is ③, and a blank and transparent safe area should be reserved inside.

The illustration graphics area is ①, and the drawing area should generally be kept within the range of ②. If the graphic needs extra visual weight to ensure consistency with other icons, the drawing area can be extended to the reserved area (note: a **2px safety distance** must be maintained around the edge when making the slice).

---

### 5.5 Animations {#animations}

The Zepp OS **"Air"** dynamic animation system creates an operation experience with a sense of nature, space, and transparency to vitalize the product.

- **Nature:** Follow the physical laws of nature, display perceptible changes in the elements of the real world, and allow users to recognize, understand, and accept them more quickly.
- **Space:** Create a vertical visual space using animations, strengthen page structure and the relationship between parent-child pages, and establish a sense of space and order. Give users a more direct perception of the connection between interfaces.
- **Transparency:** The best animations are the ones the user doesn't notice at all. The movement is silent and imperceptible and the effects are only perceived when needed. They are concise, moderate, and appropriate.

#### Design Principles

**Natural and smooth** — The animations should be visually consistent, and the movement method should conform to the laws of natural movement.

**Clear hierarchy** — The animations must clearly express the hierarchical relationship within the system, so that the connection between interfaces is natural and clear, and users can perceive the page structure through animations.

**Exercise restraint** — Due to the screen size limitation of wearable devices, animations should be concise and moderate. Reduce animation elements and motion paths. Do not exceed the user's operation time limit. Pay attention to the psychological impact of the animations on the user.

#### Icon Animations

Icon guidance animations use the change of icon elements in the interface to attract user's attention or guide user operation. Reduce the interference of other visual elements to keep the user focused.

Icon transition animation: an animated icon between two visual states. Toggling between the two icons means they are linked, and pressing one icon makes the other available.

#### Illustration Animations

Illustrated animations can enhance the visual information expressed, engage users' emotions, and help them understand features and processes.

- **Transition animations** — Transition animations in measurement apps can reduce user anxiety while they are waiting for the results.
- **Motivational animations** — Motivational animations can stimulate positive emotions as users interact with and use the product.
- **Guide animations** — Guide animations help users quickly understand how to conduct operations, reduce confusion, and complete tasks.

#### Chart Animations

Chart animations can make it easier to read charts, reduce feelings of monotony, and improve the user experience.

#### Control Animations

Control animations use animations to reflect an element's operation logic.

- Radio button
- Checkbox
- Delete
- Toasts

#### Page Animations

Page animations are used to display switching between different pages in the system and indicate the page hierarchy.

#### Rules for Use

**Basic time unit**

Regardless of the animation style, the animation transition time should not be too long or too short. Animations with moderate transitions can bring users a comfortable experience.

Based on the scope and type of animation, animation transition time intervals can be divided into the following types:

- **Shortest time: 200 ms** — Lightweight interactive animation of controls, such as radio buttons and checkboxes.
- **Median time: 300 ms** — Interactive animations for page switching, such as toasts, page switching, and deletion.
- **Long time: 400 ms** — Chart animations, such as indicator animations.
- **Custom animation time** — Illustrations and icon animations, such as animated instruction for wearing a watch.

Subsequent time intervals are divided by multiples of 100 ms.

**Animation Curve**

In the physical world, elements do not move or stop immediately. Instead, they are affected by natural forces such as friction and gravity, and take time to accelerate and decelerate, which is also known as easing.

| **Animation Type** | **Easing** | **Cubic Bezier** |
|---|---|---|
| Movement shift animations (within visible range) | ease-in-out | cubic-bezier(.42, 0, .58, 1) |
| Entry animations (into visible range) | ease-out | cubic-bezier(0, 0, .58, 1) |
| Exit animations (out of visible range) | ease-in | cubic-bezier(.42, 0, 1, 1) |

---

## 6. Templates {#templates}

### 6.1 List {#list}

Usually, a list is a finite sequence of data items of the same width, or in other words, a set of data items arranged in a certain linear order.

#### Composition

The list consists of icons, text, and operation buttons.

**Inoperable list** — List items that only contain text descriptions. The user cannot go to the next level or perform any operations.

**Operable list** — List items for which the user can perform further operations according to the description. The list item consists of a schematic icon, a description text, and an operation option. The operation option includes entry, switch, radio button, and checkbox.

**Auxiliary text** — The description text in the text box must maintain a fixed distance from the bottom. If a super-long line of description text is wrapped, the text cannot be tapped.

#### Rules for Use

- Users can select an item from the list to view details or perform more tasks.
- A list page can contain multiple list items of different types.
- If the list text occupies one line, it is the minimum height of the list. Even if the content of the list is empty, the minimum height should still be maintained.
- List headers have different layout schemes on different devices:
  - ① On a **circular screen**, the title is at the top of the list.
  - ② On a **square screen**, the title is on the status bar.
- ① The height of the list component is adaptive, and you can directly enter the text as needed.
- ② Use an ellipsis (...) at the end of the text when the text exceeds the display range.

---

### 6.2 Pop-up Windows {#pop-up-windows}

A pop-up window is a container displayed on the user interface. It is used for user operation guidance, information presentation, and message prompts.

#### Design Principles

**Effective:** Provide informative feedback to help users improve operation efficiency.

**Easy to understand:** The pop-up window must be brief and clear, the task must be short and focused, making it easy for users to quickly understand the information and tasks.

**Restraint:** Since the pop-up window will affect the user's current operation, select an appropriate reminder method according to the priority of the information, avoid excessive use, and ensure a good user experience.

#### Types

Based on the usage scenarios and feature attributes, pop-up windows on wearable devices can be divided into four categories: task completion, notification display, status notification, and information prompt.

**Pop-up window interaction rules:**

| **Pop-up Window Type** | **Page Type Name** | **Display Time** | **Display After Screen is Off for 10 Seconds** | **Swipe Right to Exit** | **Page Operations** | **Long Page** |
|---|---|---|---|---|---|---|
| Status notification pop-up window | Alert pop-up window | NO time limit | Display | NO | Button operations | Yes |
| Notification display pop-up window | Notification pop-up window | NO time limit | Follow system (return to the Watchface or the on-going page) | Yes | Button operations/None | Yes |
| Message prompt pop-up window | Drawer | Disappear after 6 seconds / Disappear after pressing the UP/DOWN button | Follow system | NO | None | NO |
| Message prompt pop-up window | Toast | Disappear after 3 seconds | Follow system | NO | None | NO |

**Alert pop-up windows** — Based on the user's status or operation, the system needs to clearly inform the user of the feedback result and allow the user to select or confirm the information. Long page display is supported.

**Notification pop-up windows** — Navigate the user to the Notification Center, convey notification content, and inform the user of the current state of the system. The user is not forced to give feedback. Long page display is supported.

**Drawers** — A drawer appears by sliding in from the edge of the screen. Drawers are suitable for items strongly related to the current task, and allow immediate task information prompts while the task is in progress. They significantly reduce the sense of obstruction by using a translucent background. To reduce disturbance to the user, persistence time can be set or manually turned off.

**Toasts** — A toast is the most lightweight feedback and does not affect the user's operations. The user can choose not to respond to a toast.

#### Visual Specifications

- There should be no space between illustrations, titles, and text, and a safe distance should be left on both sides.
- The illustrations, titles, and body text are **centered left and right** for round devices, and **left aligned** for square devices.
- When the operation buttons of the pop-up window are capsule buttons, it is recommended to use **no more than 4 operation buttons**.

---

### 6.3 Cards {#cards}

A card is a content container that aggregates information. It contains one type or a small group of elements centered on one element.

#### Design Principles

**Keep cards simple and relatively independent.** Card design should be kept minimalist, content length should be limited, and each card should only contain important information and one relevant point.

**Distinguish primary and secondary hierarchies**, make good use of the hierarchical structure of cards, highlight key content and information, and guide users to focus on the most important information or operations so that users can complete tasks more quickly.

**Make sure that the entire card can be tapped.** Generally, cards provide larger tap target areas and trigger ranges for users. Users should be able to tap any part of the card to trigger the content.

#### Composition

As an information container, a card can support almost all UI elements, including text, rich media, buttons, and more.

- **Text:** Titles, subtitles, and description text.
- **Rich media:** Cards can contain a variety of rich media elements to display icons, graphs, or charts.
- **Operations:** Buttons and icons for operations.

#### Card Swipe

When the card is swiped to the right, the delete operation prompt occurs. The height of the button is the same as that of the card. The user can tap to delete the current card.

#### Visual Specifications

- A single card cannot exceed one screen.
- Maintain a safe distance around the card.
- The spacing between cards must be kept uniform.
- There are no special layout restrictions within cards. If there is an operation area in the card, it should be clearly different from the content, and a safe distance should be maintained around the card.

---

### 6.4 Empty Pages {#empty-pages}

When no content is displayed in the initial state and no-data state, an empty page occurs to help users understand the cause of such case. It is also a placeholder prompt for operations that can be performed.

#### Design Goals

- Provide simple and clear prompts to help users understand the cause of the empty state and avoid misunderstanding and confusion.
- Give users a recommended operation prompt and tell them how to deal with the problem.

#### Types

**Operable empty page:** Informs the user of the current page state and guides the user to resolve the state using operable buttons.

**Inoperable empty page:** Only informs the user of the current page state or an operation prompt that can change the current state. Operations on the current page are not supported.

#### Rules for Use

**No-data scenarios**

No-data scenarios refer to scenarios where no data but a combination of elements is displayed in the content area. Four types of elements are displayed: graphics (including illustrations and icon elements), the "--" symbol, prompt text, and suggested operation elements. Whether to provide suggested operations depends on the specific usage scenario.

- ① The no-data status of a data item is represented by "--" as a placeholder.
- ② The text is used to clearly inform the user of status information or guide user operation.
- ③ For charts, no-data mode is displayed using the chart's grid lines or indicator background. Whether there is data on the time axis and scale axis determines which display elements are used based on the actual chart.

**Guided operation scenarios**

An empty page that is used to guide user operations consists of three parts: prompt text, graphics, and suggested operation elements. Graphics must have clear meanings, prompt text needs to offer clear descriptions, and text length cannot exceed one screen.

#### Visual Specifications

- The initial state of the app is shown in a **gray state illustration**.
- Empty pages can contain **up to two lines of text**, which needs to be displayed on one screen.
- Leave a safe distance to the left and right.

---

## 7. Elements {#elements}

### 7.1 Text {#text}

#### Design Principles

**Meaningful:** The text should help the user make a choice, take an action, or understand the current state.

**Concise and comfortable:** The text should be simple, user-friendly, and relevant. Keep the user focused on the task and make the user feel good.

#### Title

**Main titles** — The main title is used to explain or summarize the content of the next level. The main title should be consistent with the name of the feature on the previous interface.

**Subtitles** — When the main title cannot fully convey the content, add subtitles to supplement the information. ① The subtitle should have a lower-level style than the main title to show the page hierarchy.

#### Body Text

The body text should show the full text without omission. Description text and introductions.

#### Auxiliary Text

For more information about time, date, day of week, and unit, refer to: International textual usage. For more information about charts, refer to: Charts.

#### Copywriting Principles

Provide simple, direct, clear, and context-appropriate copywriting to avoid confusion.

| **Principle** | **Preferred** | **Incorrect** |
|---|---|---|
| Using the fewest possible words without sacrificing accuracy | Save changes? | Do you want to save your changes? |
| Express key points to be communicated in the current situation | Your phone is connecting with us. This may take up to 5 minutes. | Your phone needs to connect with our servers before you can log in to your account. This may take up to 5 minutes. |
| Avoid jargons | Generating record... | Buffering… |
| Use Arabic numerals | You have 3 messages. | You have three messages. |
| Clearly define the user and don't describe the same person using both first-person and second-person pronouns | Change preferences in "My Account". | In "My Account", you can change your preferences. |
| Use the correct tense and voice | Message sent. | Send message. |
| Describe goals and methods | To delete a photo from this album, drag it to the recycle bin. | Drag photos to the recycle bin to remove them from this album. |
| For text on buttons or switches, do not describe the type of element or control, and avoid repetition. | Tap Continue. | Tap the Continue button. |

---

### 7.2 Progress {#progress}

The progress indicator provides feedback on the current task progress and reasonable time consumption. It guides users to complete the target tasks and makes the wait clear and hassle-free.

#### Design Goals

- Help the user understand the current status and provide sufficient support for the user's subsequent decision-making.
- Provide well-founded reasons for the wait to ease user anxiety while waiting.

#### Types

**Horizontal progress bars** — Used to describe the progress of a task.

**Circular progress bars** — Used to describe the progress of a task. In order to fit the layout of a non-circular screen, a circular progress bar will be changed to a horizontal progress bar on pages that exceed one screen.

**Text progress indicators** — Used to describe the progress of a task in text.

---

### 7.3 Loading {#loading}

Loading refers to the continuous feedback provided to the user when the system cannot respond quickly to achieve the user's goal after receiving the user's instructions. It relieves user anxiety as they wait, informs the user of the current task status, and maintains communication with the user.

#### Rules for Use

During the loading process, the natural circular animation effect should be maintained. Loading without animation gives users the impression that the interface has frozen.

#### Visual Specifications

The overall layout is oriented towards the upper part to keep the visual focal point in the center.

---

### 7.4 Charts {#charts}

Charts are composed of graphics, images, digits, and other elements that explain and present the relationships between and properties of target data.

#### Composition

Charts are composed of: ① scale axis, ② data display, ③ horizontal grid line, ④ vertical grid line. Elements can be displayed based on the actual situation.

#### Histograms

Histograms are used to compare two or more values (at different time points or under different conditions). They contain only one variable and are typically used to analyze smaller datasets.

Choose the most suitable timeline according to different time granularities:
- **48-column histograms**
- **24-column histograms**
- **7-column histograms**

The width and height of columns can be adjusted as needed, but there should be clear separation between the columns.

#### Rules for Use

- With grid lines provided, start the first data item of the timeline from the beginning of the grid line, and align the last data item of the timeline with the end of the grid line.
- The timeline should display the corresponding time format under different time format settings (SC: Simplified Chinese, TC: Traditional Chinese, JP: Japanese).
- The width and height of a chart should be changed based on the usage scenario to keep the visual focal point in the center while maintaining a certain amount of white space.

#### Colors with Assigned Meanings

In data display, typically, some colors can be used to indicate fixed meanings. The color value does not need to be kept uniform. While hue consistency is maintained, fine-tuning can be done to improve poor display of screen colors on different devices.

- **Heart rate zone**
- **VO₂ Max**
- **Training load**
- **Sleep**

---

### 7.5 Status Bars {#status-bars}

The status bar is displayed at the top of the screen to inform the user of the current page location and useful information such as page title, time, and battery level.

#### Rules for Use

- The status bar is used to inform the user of the current page. It is **not displayed on non-application pages**. For example, Control Center, Notifications, and Shortcut Cards.
- Whether to cancel the display of the status bar at the top of the current page depends on the screen size limitations of wearable devices, how users utilize special or tool applications in specific scenarios, and the rationality of page layout. For example: the selector or calculator page.
- Text information in titles should be concise and clear, and the extra-long text information should be displayed in the **marquee form**.

---

### 7.6 Page Indicators {#page-indicators}

#### Scroll Bars

A scroll bar is a control used to indicate the current position on a page as the user scrolls down a long page.

**Rules for use:**
- If the content on the interface exceeds the display area, the scroll bar will be displayed at a fixed position when the user enters the page.
- If no operation is performed, the scroll bar will disappear after **2 seconds** (the scroll bar will be displayed again if the user touches the screen or uses the crown to interact).
- The background bar ➁ has a fixed length, while the length of the dynamic bar ➀ changes dynamically with the length of the content. The longer the content, the shorter the dynamic bar.

#### Horizontal Pagination

Pagination points are used to display the number of horizontal pages and the current page location.

**Rules for use:**
- When there are multiple horizontal pages, pagination points are displayed at the top.
- The number of pagination points is same as that of horizontal pages displayed on the screen. The user can swipe left or right or rotate the crown to switch to the corresponding page.

---

### 7.7 Operations {#operations}

#### Buttons

A button is an interactive element that indicates a specific action. It triggers functionality, guides user actions, and supports user cognitive actions.

**Design Principles:**
- Write button labels that clearly explain what each button does, so that users can quickly understand its action.
- Provide feedback for button interactions, reduce unnecessary user operations, and enhance usage efficiency.
- Ensure the tappable area of the button. Due to the screen size limitation of wearable devices, for smaller buttons, expand the tappable area of the button to ensure the accuracy of user operations.
- Avoid using too many buttons. Be sure to control the number of buttons on the page, consider the most important actions, and control the priority and complexity of buttons.
- Pay attention to the order of buttons. The order of buttons on the page should follow the directional principle, which is in line with the user's interaction habits. Ensure that the buttons are in the same order to help the user improve operation efficiency and reduce the likelihood of user operation errors.

**Floating buttons** — Fixed buttons contain highly informative features. They float on the top layer of a page and do not slide with the page.

**Capsule buttons** — As a common button style displayed on pages, capsule buttons slide with the interface. Based on the usage scenario, they are divided into:
- ➀ Default buttons
- ② Emphasis buttons
- ③ Warning buttons

**Circular buttons** — Circular buttons use graphics to visualize the button content and display more content in a relatively small screen space. Limit the number of circular buttons of different sizes on the page.

**Icon buttons** — Compared with circular buttons, icon buttons offer a more lightweight visual hierarchy as they can save more interface space. Avoid using icon buttons to express complex meanings.

**Text buttons** — Because text buttons don't have a visible container, they don't distract from nearby content and are less visually appealing. Text buttons have a low level of emphasis to less important actions.

**Rules for use:**
- Choose an appropriate button style based on the current level of button interaction behavior, and take into account both the screen space size and the overall layout.
- Keep the button text concise. The length limit of the capsule button text is **two lines**.
- Avoid all caps to increase the level of visual perception.
- Add key colors to the button to inform the user of progress and status.

**Visual Specifications:**

Buttons on square screens and round screens have different specifications. Call the button components in the corresponding component library as required.

- Floating button styles on square screen and round screen devices
- The size of a capsule button on a square device is different from that on a round screen device
  - ① Round screen device
  - ② Square screen device
- Circular buttons are available in **six sizes**. When a specific circular button is used, its size remains unchanged in round screen devices and square screen devices.
- Icon buttons are available in **two specifications**. When a specific icon button is used, its specification remains unchanged in round screen devices and square screen devices.
- Make sure that you follow the corresponding icon size specifications when drawing a slice (we recommend expanding the tappable area for smaller icon buttons, and the size of the drawing area should not be less than **52px**).

**Color value definitions:**
- ➀ Default button background color: `color_sys_item_bg` / Text/icon: `color_text_button`
- ② Emphasis button background color: `color_sys_key` / Text/icon: `color_text_button`
- ③ Define the color value of a button with a special attribute based on the color specifications, such as the incoming call button and the delete button
- ④ Text button color value: `color_text_link`
- When a tap action is triggered, the overall color brightness of the button is reduced by **40%**.
  - ➀ Default state and tapped state of a colored button
  - ② Default state and tapped state of a colorless button

#### Switches

A switch is a control used to toggle the state of a single option/card.

**Rules for use:** When the user toggles the "switch" button, it directly triggers a state change.

**Visual Specifications — four states:**
- ① On. The switch is turned on, and the user can manually turn it on/off.
- ② Off. The switch is turned off, and the user can manually turn it off/on.
- ③ On (disabled). The switch is turned on, and the user cannot manually turn it off.
- ④ Off (disabled). The switch is turned off, and the user cannot manually turn it on.
- As for the page layout, a switch is always displayed on the **right side** of a list item or a card.

#### Selection and Status Indicators

Selection and status indicators allow the user to choose from a set of predetermined options.

**Radio buttons** — Radio buttons (required) allow the user to select one out of several options.

Visual specifications — four states:
- ① Selected
- ② Unselected
- ③ Selected (disabled) — The item is selected, but the user cannot manually switch between the selected and unselected states.
- ④ Unselected (disabled) — The item is not selected, but the user cannot manually switch between the selected and unselected states.

**Checkboxes** — Checkboxes (optional) allow the user to make multiple selections from provided options.

Visual specifications — four states:
- ① Selected
- ② Unselected
- ③ Selected (disabled)
- ④ Unselected (disabled)

**Status indicators** — A status indicator is used to indicate the completion of an operation, such as indicating a completed to-do item.

Visual specifications — two states:
- ① Completed
- ② Uncompleted

#### Sliders

Slider controls (referred to as Sliders) allow the user to select an appropriate value from a continuous range while displaying the progress. At the minimum value, the top edge of the slider will be at the top end of the scroll bar. At the maximum value, the bottom edge of the slider will be at the bottom end of the scroll bar.

**Design Principles:**
- **Valid operations.** Given the characteristics of wearable devices, it is necessary to ensure that the entire page can respond to the sliding operation. In certain devices, users can also rotate the crown or operate the buttons to make operations even more efficient.
- **Clear feedback.** When the user operates the device, use progress, icons, and colors to distinguish different states and give clear feedback in a timely manner.

**Continuous sliders** — Continuous sliders allow users to select a value along a subjective range when the precise value won't matter. This allows users to make more meaningful adjustments, such as volume sliders.

Visual specifications:
- The volume icon status and color value should change correspondingly with sliding.
- The icon status has four levels: **strong, medium, weak, and mute**.
- The color value of the icon changes at a constant speed with the sliding, from `#000000` to `#999999`.
- Color value at the bottom of the slider: `color_sys_item_bg`
- Bar color value: `color_sys_normal_graphic`

**Operable sliders** — Sliders that support other operations in addition to value adjustment. For example, when the user operates a brightness slider, the slider area can increase or decrease continuously, and the user can tap the button to enable/disable the automatic screen brightness adjustment.

Visual specifications:
- Background color of the automatic screen brightness adjustment button: `color_sys_item_bg` by default, and `color_sys_key` in activated state.

---

### 7.8 Input {#input}

#### Selectors

**Data Selectors** — A data selector component is an option collection control that provides a single or multiple parameters for the user.

**Design Principles:**

*Reasonable:*
- Provide reasonable default options: Provide reasonable default options to convey the correct information, reduce the number of user operations, and improve efficiency.
- Reasonable sorting: Sort the options based on product features, logics, or user experience to help users make quick selections.

*Simplicity:*
- Simple description: The text (titles and description text) in the selector should be simple and clear, so the user can understand it with ease. Use internationally accepted abbreviations for option units.
- Simple options: Due to the screen size limitation of smart wearables, if there are too many options or the options are complicated and difficult to understand, use another form of operation. We recommend that selector options do not exceed **3 lines**. Try not to use selectors that require text description for options.

**Types:**
- Digit selectors
- Combination selectors

**Rules for use:** Use internationally accepted abbreviations for option units.

**Visual specifications:**
- The control should be positioned at the center of the entire page.
- Option digit font: DIN1451
- Default color value: `color_text_title`
- Color value for selected digits: `color_sys_key`

**Page Selectors** — A page selector is a control that provides the user with a choice of pages.

**Rules for use:** The user switches pages by swiping horizontally or rotating the crown, and taps to confirm the current page. For example, Watchface editing.

**Visual specifications:**
- Scrollable pages ➀ The interval space between two pages is **2px**, color value name: `color_sys_item_bg`
- The same interval space applies to scrollable pages on both square screen devices and circular screen devices.

#### Digit Input

Digit input provides users with a visual way to enter digit-related information.

**Design Goals:**
- Provide users with a simple and effective form to enter digital information so that they can complete tasks with efficient input.
- Provide clear visual feedback to guide user input during operations.

**Types:**
- Unlock control
- Dial control
- Calculator tool

**Rules for use:**
- The unlock control is enabled when it detects that the wearable device is off the wrist. The user taps to enter the digits, and the screen displays the digits for **500ms** before it hides the digits.

**Visual specifications:**
- For the dial/unlock control, when the user taps a digit in the digit input area, the digit and its background color are enlarged by a ratio of **1.26**, and they will return to the normal size when the tap ends.
- Background color value for a tapped digit: `#FFFFFF 20%`
- In the circular button area of the calculator tool, when the user taps a digit/character, the digit/character and its background color are enlarged by a ratio of **1.26**, and they will return to the normal size when the tap ends.
- The changes of the background color values for tapped digits/symbols/signs:
  - ① digits: `#333333` → `#666666`
  - ② math symbols: `#666666` → `#999999`
  - ③ equals sign: `#0986D4` → `#3A9EDD`
- The calculator tool symbol button will light up after the user taps OK to inform the user of the current calculation method.

---

## 8. Watchface Design Specifications {#watchface-design-specifications}

### 8.1 Introduction {#watchface-introduction}

The Watchface is the core experience element of smart wearable devices and the most frequently used feature. The Watchface has the time display feature of traditional watches and is also capable of displaying different types of data. The design of Watchfaces needs to adapt to the individual requirements of users and match different scenarios.

*(The documentation page shows a gallery of 15 diverse watchface designs, ranging from minimalist digital to analog styles, colorful to monochrome, featuring various data complications.)*

---

### 8.2 Composition {#watchface-composition}

#### Time

**Hours, minutes, and seconds:**
- Digits (negative picture-spacing values are supported to achieve cascading effects) and hands.
- The display order of the watch hands: the **second hand is on the top**, the **minute hand is in the middle**, and the **hour hand is at the bottom**.

**AM/PM:** Text.

**Week:** Icons, digits, pointer, and progress.

**Year/month/day:**
- Icons, digits, pointer, and progress.
- If the Watchface displays the year, it must be displayed in the year/month/day format. Separate display of the year is not supported.

**Lunar calendar:**
- Text
- Festivals and solar terms can be configured separately.

#### Workouts

**Steps:**
- Icons, pictures, digits, hands, and progress.
- Digital display of steps: up to **5 characters**. For example, "00000".
- Digital display of target steps: up to **5 characters**. For example, "00000".
- Empty state: "0"

**Distance:**
- Icons and digits.
- Digital display of distance: up to **4 characters**. For example, "0.00", "00.0".
- Empty state: "0"

**Calories:**
- Icons, pictures, digits, hands, and progress.
- Digital display of calorie consumption: up to **4 characters**. For example, "0000".
- Empty state: "0"

**Standing:**
- Icons, pictures, digits, hands, and progress.
- Digital display of current standing times: up to **2 characters**. For example, "00".
- Digital display of the standing times within 12 hours.
- Empty state: "0"

#### Health

**Heart rate:**
- Consists of icons, pictures, digits, hands, and progress.
- Digital display of heart rate: up to **3 characters**. For example, "000".
- Empty state: "- -"

**PAI:**
- Icons, pictures, digits, hands, and progress.
- Digital display of PAI: up to **3 characters**. For example, "000".
- Empty state: "0"

#### Weather

**Temperature:**
- Icons, pictures, digits, hands, and progress.
- Digital display of real-time temperature: up to **5 characters**. For example, "-000°".
- Digital display of lowest temperature: up to **5 characters**. For example, "-000°".
- Digital display of highest temperature: up to **5 characters**. For example, "-000°".
- Empty state: "- -"

**UV ray:**
- Icons, pictures, digits, hands, and progress.
- Digital display of UV ray level: up to **2 characters**. For example, "00".
- Empty state: "- -"

**Humidity:**
- Icons, pictures, digits, hands, and progress.
- Digital display of humidity: up to **4 characters**. For example, "000%".
- Empty state: "- -"

**Air quality:**
- Icons, pictures, digits, hands, and progress.
- Digital display of air quality: up to **3 characters**. For example, "000".
- Air quality display is **not supported in regions outside China**. Replace it with humidity.
- Empty state: "- -"

**Sunrise and Sunset:**
- Icons, pictures, digits, hands, and progress.
- Current time display: up to **5 characters**. For example, "00:00".
- Sunrise time display: up to **5 characters**. For example, "00:00".
- Sunset time display: up to **5 characters**. For example, "00:00".
- Empty state: "- -"

**Moon phase:**
- Image
- 7/13/30 Moon phase images

**Air pressure:**
- Icons, pictures, digits, hands, and progress.
- Air pressure display: up to **5 characters**. For example, "00000".
- Empty state: "- -"

#### System

**Battery level:**
- Icons, pictures, digits, hands, and progress.
- Digital display of battery level: up to **4 characters**. For example, "100%".

**System status:**
- Icons.
- Switch status is required for **DND, Bluetooth, screen lock, and alarm clock**.

---

### 8.3 Safe Area {#watchface-safe-area}

Leave a **2px safe margin** around the central area. Leave display areas for status points and offline voice commands at the top and bottom, where no important information is placed.

---

### 8.4 Screen Off Mode {#screen-off-mode}

The screen-off mode means that the Watchface displays only important information such as time in a limited manner, which helps users obtain information without raising their wrists. It is an essential mode for a Watchface.

There are two types of screen-off mode display:
1. One which follows the current Watchface
2. One that users can configure independently

The screen-off mode display that follows the current Watchface requires special design from the Watchface designer.

#### Design Rules

- **Minimize Watchface elements.** When an element on the Watchface lights up, its pixels cannot exceed **10%** of the pixels of the screen.
- Watch face hands may **not include a second hand**.
- The background color of the Watchface must be **black (#000000)**, and the main color of the hands must be **white (#FFFFFF)**.
- Keep the hands/digital slices the **same size**.
- Since switching between screen off and screen on states must occur, try to minimize the movement of elements to avoid jumping during switching.
- To ensure legibility, try to retain the basic timescale (not mandatory).
- Except for time, the priority of other elements is: **steps > date > weather > battery level > heart rate > others** (not mandatory but should be followed in most cases).

#### Hand Processing Methods

**Hand silhouette/digit silhouette + black border on the outer edge:**
- Remove texture parameters such as gradients, highlights, and shadows, but retain the silhouette graphics of hands/digits.
- The hand should have an additional **black border of 1–2px** on the outer edge. The purpose is to distinguish the hand at the upper layer from the hand at the lower layer, and to distinguish the relationship between the upper and lower layers of the hands and the data.
- The colors of the hands can be increased based on the characteristics of the Watchface, but add as few colors as possible.

**White film + black border on the outer edge:**
- The hands should retain part of the structural light and shadow to achieve the overall "white film" effect.
- The hand should have an additional **black border of 1–2px** on the outer edge. The purpose is to distinguish the hand at the upper layer from the hand at the lower layer, and to distinguish the relationship between the upper and lower layers of the hands and the data.

#### Digital Time Processing Methods

- Digital time displays typically occupy a large graphical area, so the outer border is used. The **border width should not be less than 2px**.
- The border color must be **white or another color with high brightness**. When the illuminated area is less than 10%, the border area can be omitted.

---

## 9. Internationalization {#internationalization}

### 9.1 Introduction {#i18n-introduction}

For products and applications to be released globally, globalization processes need to be considered, namely "internationalization" and "localization".

> **Internationalization**, referred to as **"i18n"**, is a convergent design method that meets the needs of different countries through a certain type of solution.

> **Localization**, referred to as **"L10n"**, is a solution customized for each country.

The strategy of internationalization + localization, that is, **"glocal — global+local"**, refers to the combination of international unity and regional differences. Under the premise of unity, this strategy provides flexible configurations to ensure personalized user experience in different regions. As a cost-effective design solution, it can satisfy the requirements for unified maintenance, improve product efficiency, and meet the special demands of local users.

This guide summarizes the common problems encountered in internationalization and localization design. The following rules help to achieve effective globalization of products and applications.

---

### 9.2 Languages {#languages}

**Default text:** Use the Zepp OS default font library for design and development. English is the default language when the product cannot match the language. It is recommended to design based on the English version.

**Capitalization:** For the use of capitalization and lowercase in different languages, it is necessary to judge the language type first. Do not use capitalization and lowercase alone to convey a necessary message.

**Punctuation:** Make sure that the punctuation marks are localized, and pay special attention to the placement of punctuation when wrapping lines.

**System special symbols:**

| **Name** | **Symbol** |
|---|---|
| Angle | ° |
| Minute | ′ |
| Sec | ″ |

**Units:** Units need to be localized. Only the United States, Liberia, and Myanmar use the imperial system. Other countries or regions use the metric system. Hong Kong, China, and Canada use a mixture of the two systems.

| **Data** | **Metric Unit** | **Imperial Unit** |
|---|---|---|
| Distance | km | mi |
| Speed | km/h | mph |
| Stride | cm | in |
| Swimming distance | m | yd |
| Calorie consumption | kcal | kcal |
| Temperature | ℃ | ℉ |

**Text styles:** Avoid text styles such as italics and underlines.

---

### 9.3 Interface Layouts {#interface-layouts}

**Separation of graphics and text:** Do not embed text directly into images. When creating text in an image, we recommend layering the image and text.

**Text space:** Considering the large differences in the length of translated texts in different languages, try to use concise descriptions, reserve enough space for all texts, and set the processing methods in case of overflow.

Reserve enough space for the display of localized control text based on the text length:
- If the number of letters is **less than 10**, reserve **50%** of the space.
- If the number of letters is **greater than 10 and less than 20**, reserve **30%** of the space.
- If the number of letters is **greater than 20**, reserve **20%** of the space.

When the text cannot wrap and is too long, use an **ellipsis (...)**.

When the text needs to be displayed completely and cannot be omitted, use the **"marquee" effect**.
- ① Only single-line text can use the "marquee" effect.
- ② The marquee effect features a gradient mask on the right side of the text, moving from 0% to 100% opaque. It is a square with the same height as the single-line text box.

**Correct handling of RTL languages:**

RTL (Right to Left) languages refer to languages written from right to left. Common features of this language are: sentences are read from right to left; sequence of events progresses from right to left; an arrow pointing right to left (←) indicates forward motion, and an arrow pointing left to right (→) indicates backward motion.

- ① When the direction in which UI elements is displayed is changed, untranslated text (even if it is part of a phrase) and digits are not mirrored, and they should be maintained in the correct direction that fits the target language.
- ② Mirror the operations that indicate specific directions.
- ③ Maintain consistency in icons that do not indicate directions and only change their positions.
- ④ Mirror the icons that indicate specific directions.
- ⑤ After a word is translated, it is written from right to left.

---

### 9.4 Visual Graphics {#visual-graphics}

- Try to use common graphic images (for common graphic images, see: Illustration), and reduce the metaphors used in graphics, images, and colors.
- Avoid the use of gestures to convey meaning in graphic designs.
- Avoid religious, mythological, politically related content, signs, symbols, and similar.

---

### 9.5 Regional Standards {#regional-standards}

#### Week

The first day of the week should be adjusted according to local standards.

| **Standard Type** | **First Day of the Week** | **Applicable Region** |
|---|---|---|
| ISO standard | Monday | Eurasia |
| North American standard | Sunday | American continent |
| Islamic standard | Saturday | Middle East |

#### Year/Month/Day

| **English** | **Chinese** |
|---|---|
| YYYY/MM/DD (2020/03/12) | YYYY 年 M 月 D 日 (2020 年 3 月 12 日) |
| YY/MM/DD (20/03/12) | — |
| MM/DD (03/12) | M 月 D 日 (3 月 12 日) |

#### Time

In the case of 12-hour mode, the descriptions of morning and afternoon should be displayed in different places according to cultural differences.

| **Mode** | **00:00** | **00:01** | **09:01** | **12:00** | **12:01** | **21:01** | **23:59** |
|---|---|---|---|---|---|---|---|
| 24-hour mode | 00:00 | 00:01 | 09:01 | 12:00 | 12:01 | 21:01 | 23:59 |
| 12-hour mode (Chinese: Simplified/Traditional) | 上午 12:00 | 上午 12:01 | 上午 9:01 | 下午 12:00 | 下午 12:01 | 下午 9:01 | 下午 11:59 |
| 12-hour mode (other) | 12:00 AM | 12:01 AM | 9:01 AM | 12:00 PM | 12:01 PM | 9:01 PM | 11:59 PM |

Note the half-width spaces between the time and AM/PM signs.

#### Multilingual Localization Reference (9 AM / 9 PM)

| **Language** | **9 AM** | **9 PM** | **Mode** |
|---|---|---|---|
| French (FR) | 9:00 | 21:00 | 24-hour mode only |
| German (DE) | 9:00 | 21:00 | 24-hour mode only |
| Spanish (ES) | 9:00 a.m. or 9:00 | 9:00 p.m. or 21:00 | Both 12-hour and 24-hour modes support switchable displays |
| Italian (IT) | 9:00 AM | 9:00 PM | 12-hour mode only |
| Brazilian Portuguese (PT-BR) | 9:00 | 21:00 | 24-hour mode only |
| Russian (RU) | 9:00 | 21:00 | 24-hour mode only |
| Polish (PL) | 9:00 | 21:00 | 24-hour mode only |
| Ukrainian (UK) | 9:00 | 21:00 | 24-hour mode only |
| Japanese (JA) | 9:00 AM | 9:00 PM | 12-hour mode only |
| Korean (KO) | 오전 9시 or 9 am | 오후 9시 or 9 pm | 12-hour mode only |
| Arabic (AR) | 9:00 صباحًا | 9:00 مساءً | 12-hour mode only |
| Turkish (TR) | 9:00 ÖÖ | 9:00 ÖS | 12-hour mode only |
| Hebrew (HE) | 9:00 | 21:00 | 24-hour mode only |
| Thai (TH) | 9:00 น. | 21:00 น. | 24-hour mode only |
| Vietnamese (VI) | 9:00 SA | 9:00 CH | 12-hour mode only |
| Czech (CS) | 9:00 | 21:00 | 24-hour mode only |
| Indonesian (ID) | 9:00 pagi or 9:00 | 9:00 sore or 21:00 | Both 12-hour and 24-hour modes support switchable displays |
| Greek (EL) | 9:00 π.μ. | 9:00 μ.μ. | 12-hour mode only |
| Serbian (SR_RS) | 9:00 | 21:00 | 24-hour mode only |
| Catalan (ca-ES) | 9:00 | 21:00 | 24-hour mode only |

> **Remarks:** Countries that use 12-hour mode only can switch to 24-hour mode in the 9:00 format. Countries that use 24-hour mode only can switch to 12-hour mode in the 9PM format. The rest can be localized as required.

#### Time Abbreviations

Time abbreviations are used to display the current time in some scenarios. The display of AM or PM is not required.

| **Mode** | **00:00** | **00:01** | **09:01** | **12:00** | **12:01** | **21:01** | **23:59** |
|---|---|---|---|---|---|---|---|
| 24-hour mode | 00:00 | 00:01 | 09:01 | 12:00 | 12:01 | 21:01 | 23:59 |
| 12-hour mode (Chinese: Simplified/Traditional) | 12:00 | 12:01 | 9:01 | 12:00 | 12:01 | 9:01 | 11:59 |
| 12-hour mode (other) | 12:00 | 12:01 | 9:01 | 12:00 | 12:01 | 9:01 | 11:59 |

---

## 10. Accessibility Design {#accessibility-design}

### 10.1 Introduction {#accessibility-introduction}

Accessibility design in Zepp OS is mainly a consideration for users who are visually impaired. It ensures that people with visual impairment can better obtain information, and it can adapt to different devices and complex lighting environments to ensure comfortable reading and better product experience. Based on accessibility design considerations, the product design needs to ensure **natural perception, convenient operation, and clear understanding**.

---

### 10.2 Color {#accessibility-color}

**Avoid using colors as the only way to convey important information.**

Many visually impaired users have difficulty distinguishing between blue and orange or red and green. In the application design process, avoid using only colors to convey information. Combine text or graphics to help visually impaired users understand.

Choose colorblind-friendly palettes based on the requirements of visually impaired users. You can simulate color vision deficiency to find proper colorblind-friendly palettes. You can use the color vision deficiency (CVD) simulator to improve your design.

Two colors that need to be distinguished must have a sufficient hue difference to ensure **△Euv ≥ 20** (ISO 9421-307).

- The color difference value is **△Eab\*** in the CIE L\*A\*B\* color space and **△Euv\*** in the CIE LUV color space.
- Color toolset is used to convert RGB color to CIE L\*A\*B\* color space and CIE LUV color space.
- Color difference calculator is used to calculate △Euv.

---

### 10.3 Contrast Ratio {#contrast-ratio}

Follow the **WCAG principles** (Web Content Accessibility Guidelines).

According to WCAG principles, the visual presentation of text and images of text has a contrast ratio of at least **4.5:1** (contrast ratio between text and background behind the text), except for the following:

- **Large text:** Large-scale text and images of large-scale text have a contrast ratio of at least **3:1**.
- **Incidental:** Text or images of text that are part of an inactive user interface component, that are pure decoration, that are not visible to anyone, or that are part of a picture that contains significant other visual content, have **no contrast requirement**.

Use the contrast checker to check the text contrast.

---

## 11. Designer's Self-Checklist {#designers-self-checklist}

The self-checklist describes the rules that need to be followed in the system design process, which will improve the consistency across the system and reduce user confusion and mistakes in interactive data visualization.

The self-checklist has two categories, **"Required"** and **"Recommended"**. For the "Recommended" category, consider the product definition and make appropriate modifications.

| **Dimension** | **Item** | **Requirement** | **Measurements** |
|---|---|---|---|
| Structure | Right swipe return | Avoid interactions that conflict with the right swipe return. If this constrains your design, you can negotiate to modify the interaction or change the hot zone. | Required |
| Visual | Color | Whether the colors of key content and information, warnings, controls, basic graphics, and so on refer to component library presets. | Required |
| Visual | Font | Whether the font size refers to the component library. | Required |
| Visual | Icon | Reserve a 2px blank and transparent safe area around the icon. The icon output resource must be in PNG format, and the blank area must be transparent. | Required |
| Visual | Icon (style) | The style of app icon design must follow that of system app icons. | Recommended |
| Visual | Illustrations | Use different types of illustrations on different pages. | Required |
| Templates | Pop-up windows | Whether the component is referenced. Distinguish between round/square screen devices for pop-up window alignment. | Required |
| Templates | Empty page | Distinguish between operating and non-operating scenarios. | Required |
| Templates | Cards | The height of the card should not exceed one screen. The space between the card and the content around is 16px. Use unified components for the right swipe delete. | Required |
| Templates | List | The spacing between lists is 8px. A space is required between the description text and the next element. | Required |
| Elements | Charts | Choose the appropriate chart style according to the data. Note the default state of the chart data. | Recommended |
| Elements | Loading | Whether the corresponding control in the system control library is referenced. | Required |
| Elements | Page indicators | Whether the corresponding control in the system control library is referenced. | Required |
| Elements | Buttons | Whether an appropriate button style is used based on the button interaction behavior level. Whether the button text is accurate and concise. Whether the buttons of square screen and round screen devices call the corresponding component library. | Required |
| Elements | Switches | Whether the switches use the same layout on the right side of the page. | Required |
| Elements | Selection and status indicator | Whether the controls use the same layout on the right side of the page. | Required |
| Elements | Sliders | Whether the corresponding control in the system control library is referenced. | Required |
| Elements | Selectors | There cannot be more than 5 single-digit columns. There cannot be more than 3 double-digit columns. There cannot be more than 2 three-digit columns. | Required |
| Elements | Digit input | Whether the corresponding control in the system control library is referenced. | Required |
| Elements | Fast reply | Whether the corresponding control in the system control library is referenced. | Required |
| Elements | Text | Whether the component is referenced. Whether the color references a style. Specify the size of the text box. | Required |
| Elements | Progress | Whether the component is referenced. | Required |
| Internationalization | Text | Texts in English, Russian, and German are relatively long. Consider the method to handle multiple lines of text that occur at the same time. | Required |
| Accessibility | Color | Whether the prompt message contains text. When using only colors to distinguish information, avoid the use of similar colors that are difficult to recognize by visually impaired users. Color contrast ratio self-check. | Recommended |

---

## 12. Resource Downloads {#resource-downloads}

### Font

The following font files are available for download:

- `DIN1451MittelschriftAlternat-Regula.ttf`
- `Noto Sans-Regular.ttf`
- `Noto Sans-Medium.ttf`
- `Number.ttf`

### Design Component Library

The following design component library resources are available:

- **Library Circular** — Component library for circular/round screen devices
- **Library Rectangular** — Component library for rectangular/square screen devices
- **Brand Guidelines** — Brand guidelines documentation

---

*End of Zepp OS v2 Design Specifications — Complete Documentation Extraction*

*Copyright © 2025 Zepp Health, Inc.*
