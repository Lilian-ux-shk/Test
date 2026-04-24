# Figma implementation rules

## Source of truth
- Treat the linked Figma file or node as the visual source of truth.
- Use Figma MCP/design context when available before writing UI code.
- Do not infer spacing, typography, colors, icons, or responsive behavior if they are available from Figma.
- If design context is incomplete, call out the missing information instead of guessing silently.

## Design system mapping
- Prefer existing components from the local codebase over creating new components.
- Search the repo for matching components before implementing new UI.
- Map Figma components to existing React components where possible.
- Preserve component names, variants, states, and hierarchy from Figma when they correspond to code components.

## Styling
- Use design tokens from the repo instead of hard-coded values.
- Do not introduce new colors, font sizes, shadows, border radii, or spacing scales unless the design requires them.
- If the repo uses Tailwind, use existing Tailwind tokens/classes.
- If the repo uses CSS variables or theme tokens, use those first.

## Assets
- Use exported SVGs/icons/images only when the repo does not already contain the asset.
- Keep assets organized in the existing asset directory structure.
- Do not rasterize vector icons unless explicitly required.
- Add meaningful alt text for informative images.

## Layout and responsiveness
- Match Figma auto-layout behavior using flex/grid.
- Preserve padding, gaps, alignment, and constraints.
- Implement responsive behavior according to the design or nearby existing patterns.
- Do not make desktop-only assumptions unless the Figma node is explicitly desktop-only.

## Accessibility
- Use semantic HTML.
- Ensure buttons, links, inputs, and dialogs are keyboard accessible.
- Preserve visible labels and accessible names.
- Maintain sufficient contrast; flag any contrast issue found in the design.

## Validation
- Run the repo’s formatter, linter, typecheck, and relevant tests after changes.
- Include a brief summary of design-to-code mappings in the final response.
- Mention any Figma details that could not be verified.
