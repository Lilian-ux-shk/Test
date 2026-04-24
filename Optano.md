# Optano Design Rules

These rules are derived from the provided Optano/Density guideline assets:
- `Density-DesignTokens 1.xlsx`
- `Guidelines.pdf`
- `Charts colors.pdf`
- `Chart Anatomy.pdf`
- `Secondary-colors.png`
- `Tertiary colors.png`
- `Screenshot 2026-02-26 132307.png`
- `Screenshot 2026-02-26 132434.png`

## 1) Token Naming And Scale

- Use color tokens in this exact shape: `--ds-color-<family>-<step>`.
- Use only these steps: `100, 200, 300, 400, 500, 600, 700, 800, 900, 950`.
- Do not introduce custom steps (for example `650` or `1000`) unless the design system is formally extended.
- Favor tokens over raw hex values in code, charts, and documentation.

## 2) Approved Color Families

### Theme colors (foundation)
- `ocean`
- `grey`
- `cool-grey`

### Signal colors (status and severity)
- `blue` (informational)
- `green` (success/positive)
- `yellow` (warning/caution)
- `red` (error/critical)

### Secondary colors (extended/categorical)
- `violet`
- `viridian`
- `gamboge`
- `olive`
- `fuschia`
- `bondiblue`

### Tertiary colors (overflow/extended categorical)
- `heliotrope`
- `jade`
- `persimmon`
- `avocado`
- `rose`

## 3) Color Usage Rules

- Theme colors are the default for UI structure, surfaces, text hierarchy, and neutral states.
- Signal colors are reserved for semantic meaning (info/success/warning/error). Do not repurpose them as decorative category colors.
- Secondary colors are the first choice for data-category palettes in charts and information visualization.
- Tertiary colors are used only when the secondary set is exhausted or additional differentiation is required.
- Keep semantic consistency across screens: the same meaning must keep the same signal color family.
- Avoid mixing many families within one component unless the component is a chart/visualization that requires category contrast.

## 4) Shade Selection Rules

- Use `100-500` for lighter fills/backgrounds.
- Use `600-950` for strong accents, strokes, and high-contrast foreground use.
- Prefer wider shade distance between adjacent chart series when they appear side-by-side.
- For text over colored backgrounds, use combinations that pass WCAG contrast requirements.
- If a chosen token pair fails contrast, adjust by changing shade depth before switching family.

## 5) Chart-Specific Rules

- Build chart category palettes from secondary colors first.
- Add tertiary colors only when category count exceeds the secondary palette capacity.
- Reserve signal colors for thresholds, alerts, exceptions, and KPI health states.
- Do not encode both category identity and alert severity with the same color channel; use shape/marker/annotation for one of them.
- Keep chart color assignment stable across dashboards so the same category keeps the same color.
- Use neutral greys (`grey` or `cool-grey`) for grid lines, axes, labels, and non-focus context.

## 6) Chart Anatomy And Visual Hierarchy

- Prioritize data marks first, then labels, then scaffolding (grid/axes/background).
- Keep chart scaffolding low-emphasis using neutral tokens.
- Highlight only the intended focus series/point; de-emphasize the rest with lighter neutral shades.
- Do not rely on color alone for critical distinctions: include legends, labels, markers, or patterns where needed.

## 7) Accessibility Rules

- Ensure all text and key UI states meet WCAG contrast minimums.
- Never communicate critical meaning with color only; pair with iconography, labels, or text.
- Validate charts for color-vision accessibility by using distinct hue and luminance differences.
- Keep interactive states (hover/focus/selected/disabled) visibly distinct and token-based.

## 8) Implementation Rules

- Use only design-token references in CSS, JS/TS, and chart config.
- Do not hardcode hex values in product code unless explicitly approved as an exception.
- Keep token names lowercase and hyphenated exactly as specified.
- When adding new visuals, reuse existing palette families and step values before proposing new tokens.

## 9) Governance

- Any new family, new step, or semantic remapping requires design-system approval.
- Document approved exceptions inline in PR descriptions and in design-system changelog notes.
- During review, reject UI/chart changes that bypass tokens or violate semantic color mapping.

## 10) Quick Mapping Summary

- UI foundation: `ocean`, `grey`, `cool-grey`
- Status semantics: `blue`, `green`, `yellow`, `red`
- Category data (default): `violet`, `viridian`, `gamboge`, `olive`, `fuschia`, `bondiblue`
- Category data (overflow): `heliotrope`, `jade`, `persimmon`, `avocado`, `rose`
