# Product Design Contract

Use this document for durable visual and interaction decisions in UI projects.
It is not a system architecture document or a task-specific implementation
design. Replace bracketed prompts and obtain approval before material interface
implementation. If the project has no user interface, record that here.

## Experience Goals

- **Primary users:** [Who uses the product and in what context]
- **Primary outcome:** [What users should accomplish]
- **Experience qualities:** [For example: calm, fast, trustworthy, expressive]
- **Non-goals:** [Experiences the interface should not optimize for]

## Design Principles

Define three to five testable principles that guide trade-offs.

1. [Principle and its practical consequence]
2. [Principle and its practical consequence]
3. [Principle and its practical consequence]

## Brand Personality And Visual Direction

- **Personality:** [Three to five adjectives]
- **Visual Direction:** [Composition, density, contrast, and distinguishing traits]
- **Reference products:** [References and the specific quality to borrow]
- **Audience and context:** [Professional, consumer, accessibility, or environment constraints]

## Rejected Styles

List visual choices that are explicitly out of scope and why.

- [Rejected style]: [Reason]

## Design Tokens

Define semantic tokens; do not introduce page-local values when an existing
token fits.

### Color

- **Surfaces:** [canvas, raised, overlay]
- **Text:** [primary, secondary, muted, inverse]
- **Borders:** [subtle, default, strong]
- **Actions:** [primary, secondary, destructive]
- **Feedback:** [info, success, warning, error]
- **Contrast targets:** [Required ratios or standard]

### Typography

- **Font families:** [UI, display, monospace]
- **Type scale:** [Sizes and line heights]
- **Weights:** [Permitted weights and usage]
- **Content rules:** [Line length, wrapping, numeric treatment]

### Spacing, Radius, Shadow, And Layering

- **Spacing scale:** [Base unit and scale]
- **Radius scale:** [Values and component usage]
- **Shadow scale:** [Elevation meanings]
- **Layering:** [Stacking levels for content, navigation, overlays, and alerts]

## Layout And Responsive Behavior

- **Content widths:** [Reading, application, and full-bleed limits]
- **Grid:** [Columns, gutters, and alignment]
- **Breakpoints:** [Behavioral breakpoints rather than device labels]
- **Navigation:** [Desktop and compact behavior]
- **Responsive priorities:** [What reflows, hides, or remains fixed]

## Components

Describe the shared appearance, anatomy, density, and variants for core
components. Reuse existing components before creating a new pattern.

- **Buttons and links:** [Hierarchy and treatment]
- **Inputs and forms:** [Labels, help, validation, and density]
- **Navigation:** [Active indication and hierarchy]
- **Containers:** [Cards, panels, tables, and lists]
- **Overlays:** [Dialogs, drawers, menus, and tooltips]

## Interaction States

Define visible and consistent behavior for:

- Loading and progress
- Empty results and first-use guidance
- Errors, warnings, and recovery
- Success and confirmation
- Hover, focus, active, selected, and disabled states

Never communicate status by color alone. Preserve user input when an operation
fails whenever it is safe to do so.

## Accessibility

- Meet [WCAG version and conformance level].
- Support keyboard-only operation with visible, ordered focus.
- Use semantic structure, names, labels, and announcements for assistive technology.
- Meet documented color-contrast and target-size requirements.
- Support zoom, text resizing, reflow, and user display preferences.
- Include accessible alternatives for non-text content and complex gestures.

## Motion

- **Purpose:** [What motion communicates]
- **Durations:** [Fast, standard, and deliberate ranges]
- **Easing:** [Approved curves]
- **Reduced motion:** Remove non-essential movement and provide equivalent state cues.
- **Prohibited motion:** [Distracting, blocking, or vestibular-risk patterns]

## Imagery And Icons

- **Icons:** [Family, stroke/fill, sizing, and label rules]
- **Illustration:** [Style, palette, and usage]
- **Photography:** [Subject, lighting, cropping, and representation]
- **Generated images:** [Permitted use, review, provenance, and prohibited content]

## Design QA

Before accepting a UI change:

- Compare the browser result with this contract and the approved design.
- Test supported browsers and representative responsive widths.
- Capture screenshots for materially changed states and breakpoints.
- Exercise loading, empty, error, success, hover, focus, active, and disabled states.
- Check keyboard navigation, focus visibility, semantics, contrast, zoom, and reduced motion.
- Record deviations, skipped checks, and residual visual or accessibility risks.
