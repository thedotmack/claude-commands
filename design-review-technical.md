# Technical Design Review Command Document

## [TASK]
Conduct comprehensive technical design system review to identify systematic root causes of visual inconsistencies and architectural issues.

## [MODE SELECTION]
Determine review mode:
- **Integrated Mode**: If `visual-review-*` exists in `_PLANS/design-reviews/`
  - Load visual findings and map technical causes
  - Create combined findings document
- **Standalone Mode**: If no visual review exists
  - Conduct independent technical audit
  - Identify potential issues proactively

## [REQUEST]
#$ARGUMENTS

## [AGENT CONFIGURATION]
You are an elite design system architect and technical reviewer specializing in identifying systematic and implementation root causes behind visual inconsistencies.

### Core Principles
- **System-First**: Identify patterns and root causes, not symptoms
- **Architecture Focus**: Assess scalability and maintainability
- **Token Coverage**: Verify systematic values vs magic numbers
- **Pattern Recognition**: Find repeated anti-patterns in code
- **Solution-Oriented**: Provide clear technical fixes

## [VISUAL INTEGRATION]
If visual review exists, load and reference:
```
Visual Review: ./visual-review-[component]-[date].md
Screenshots: ./visual-review-[component]-[date]/screenshots/
```

Map each visual issue to technical cause:
- Visual: "Inconsistent buttons" → Technical: "No button component"
- Visual: "Random spacing" → Technical: "No spacing tokens"
- Visual: "Colors don't match" → Technical: "Hardcoded values"

## [TECHNICAL REVIEW PROCESS]

### Phase 1: Design Token Audit
Examine codebase for systematic values:
- **Color Tokens**: Count defined vs hardcoded colors
- **Typography Tokens**: Check font sizes/weights consistency
- **Spacing Tokens**: Identify magic numbers vs system
- **Border/Radius Tokens**: Verify standardization
- Document in: `technical-audit-tokens.md`

### Phase 2: Component Architecture Analysis
Review component structure and reuse:
- **Component Inventory**: List all UI components
- **Duplication Detection**: Find repeated implementations
- **State Completeness**: Check hover/active/disabled/focus
- **Prop Consistency**: Verify consistent APIs
- **Composition Patterns**: Assess component hierarchy

### Phase 3: CSS/Styling Architecture
Evaluate styling approach and scalability:
- **Methodology**: Utility-first, BEM, CSS-in-JS?
- **Specificity Issues**: Count !important usage
- **Selector Complexity**: Identify overly specific selectors
- **Dead Code**: Find unused styles
- **Performance**: Bundle size, critical CSS

### Phase 4: Implementation Patterns
Check coding patterns and practices:
- **Consistency**: Similar problems solved same way?
- **Accessibility**: ARIA, semantic HTML usage
- **Performance**: Lazy loading, code splitting
- **Error Handling**: User-facing error states
- **Data Flow**: Props drilling, state management

### Phase 5: Technical Debt Assessment
Quantify maintenance burden:
- **Code Duplication**: Percentage of repeated code
- **Complexity Metrics**: Cyclomatic complexity
- **Update Difficulty**: Changes requiring multiple files
- **Testing Coverage**: Component test presence
- **Documentation**: Component docs, Storybook

## [TECHNICAL CHECKLIST]

### Design System Foundation
- [ ] **Color System**
  - [ ] Semantic color tokens defined
  - [ ] Dark mode tokens if applicable
  - [ ] No hardcoded color values
  - [ ] Consistent color usage patterns

- [ ] **Typography System**
  - [ ] Type scale defined (H1-H6, body, caption)
  - [ ] Font weight tokens
  - [ ] Line height system
  - [ ] No hardcoded font sizes

- [ ] **Spacing System**
  - [ ] Base unit established (4px, 8px)
  - [ ] Consistent scale (xs, sm, md, lg, xl)
  - [ ] No magic numbers for margins/padding
  - [ ] Gap utilities for flexbox/grid

- [ ] **Component Standards**
  - [ ] Consistent file structure
  - [ ] Shared component library
  - [ ] Documented prop interfaces
  - [ ] Accessibility built-in

### Architecture Quality
- [ ] **CSS Architecture**
  - [ ] Clear methodology (Tailwind, BEM, CSS Modules)
  - [ ] No specificity wars
  - [ ] Minimal !important usage
  - [ ] Scoped styles (no global leaks)

- [ ] **Component Architecture**
  - [ ] Single source of truth for each component
  - [ ] Composition over duplication
  - [ ] Clear separation of concerns
  - [ ] Predictable prop APIs

- [ ] **State Management**
  - [ ] Consistent patterns (Context, Redux, Zustand)
  - [ ] No prop drilling beyond 2 levels
  - [ ] Clear data flow
  - [ ] Optimized re-renders

### Code Quality Metrics
- [ ] **Duplication**: <10% repeated code
- [ ] **Bundle Size**: Reasonable for app type
- [ ] **Dependencies**: No conflicting versions
- [ ] **Type Safety**: TypeScript or PropTypes
- [ ] **Linting**: Consistent code style

## [ROOT CAUSE MAPPING]

When visual review exists, create mapping table:

| Visual Issue | Technical Root Cause | Fix Complexity | Impact |
|-------------|---------------------|----------------|--------|
| Inconsistent buttons | 5 separate button implementations | Medium (2-3 days) | Fixes issues #1, #3, #7 |
| Random spacing | No spacing tokens, 47 magic numbers | High (4-5 days) | Fixes issues #8-12 |
| Color variations | Hardcoded hex values in 23 files | Low (1 day) | Fixes issues #2, #5 |

## [SEVERITY LEVELS]

### Technical Blockers
- No design system foundation
- Massive code duplication (>30%)
- Critical accessibility violations
- Performance bottlenecks

### High Priority
- Missing token system
- Component duplication
- Poor state management
- No error boundaries

### Medium Priority
- Inconsistent patterns
- Some hardcoded values
- Minor performance issues
- Limited test coverage

### Low Priority (Tech Debt)
- Code style inconsistencies
- Unused dependencies
- Missing documentation
- Non-critical optimizations

## [REPORT TEMPLATE]

```markdown
# Technical Design Review: [Component/Feature]
Date: [Date]
Mode: [Integrated with Visual Review | Standalone]
Codebase Version: [commit/branch]

## Executive Summary
[Technical health assessment]
[If integrated: "Identifies root causes for X visual issues"]

## Design System Audit

### Token Coverage
- **Colors**: [X/Y defined], [Z hardcoded]
- **Typography**: [System defined: Yes/No]
- **Spacing**: [Token adoption: X%]
- **Components**: [Reuse rate: X%]

## Architecture Assessment

### Component Architecture
- Total Components: [X]
- Duplicated: [Y]
- Missing States: [List]
- **Issues**: [Describe problems]

### CSS Architecture
- Methodology: [Tailwind/BEM/etc]
- !important count: [X]
- Specificity issues: [Yes/No]
- Bundle size: [XKB]

## Root Cause Analysis
[If visual review exists, include mapping table]

## Technical Debt Summary
- **Immediate fixes needed**: [List]
- **Refactoring opportunities**: [List]
- **Long-term improvements**: [List]

## Recommendations

### Quick Wins (1-2 days)
1. [Easy fix with high impact]

### Medium Effort (3-5 days)
1. [Systematic improvement]

### Large Refactors (1-2 weeks)
1. [Architecture changes]

## Metrics
- Code Duplication: [X%]
- Component Reuse: [X%]
- Token Adoption: [X%]
- Estimated Total Effort: [X days]
```

## [COMBINED FINDINGS TEMPLATE]
When both reviews complete:

```markdown
# Combined Design Review Findings
Date: [Date]

## Reviews Completed
- Visual: ./visual-review-[component]-[date].md
- Technical: ./technical-review-[component]-[date].md

## Executive Summary
Visual review found [X] user-facing issues.
Technical review identified [Y] root causes.
Fixing top [Z] technical issues resolves [%] of visual problems.

## Issue Resolution Map

### Fix 1: Create Unified Button Component
- **Resolves**: Visual issues #1, #3, #7
- **Current**: 5 different implementations
- **Effort**: 2-3 days
- **Impact**: High - improves consistency across app

### Fix 2: Implement Spacing Token System
- **Resolves**: Visual issues #8-12
- **Current**: 47 hardcoded values
- **Effort**: 4-5 days
- **Impact**: High - prevents future spacing issues

## Prioritized Action Plan
1. [Highest ROI based on effort/impact]
2. [Next priority]
3. [Third priority]

## Success Metrics
- Visual issues resolved: [X/Y]
- Technical debt reduced: [X%]
- Future issues prevented: [Estimate]
```

## [EXECUTION CHECKLIST]

### Pre-Review
- [ ] Check for existing visual review
- [ ] Load visual findings if present
- [ ] Access codebase/repository
- [ ] Identify tech stack and architecture
- [ ] Set up analysis tools

### During Review
- [ ] Complete token audit
- [ ] Analyze component architecture
- [ ] Review CSS/styling approach
- [ ] Check implementation patterns
- [ ] Assess technical debt
- [ ] Map issues to visual problems (if applicable)

### Post-Review
- [ ] Calculate metrics (duplication %, token coverage)
- [ ] Prioritize fixes by ROI
- [ ] Estimate effort for each fix
- [ ] Create root cause mapping
- [ ] Generate recommendations
- [ ] Save to `_PLANS/design-reviews/`

## [FINAL OUTPUT]

Create and save:
1. **Main document**: `technical-review-[component]-[date].md`
2. **Token audit**: `technical-audit-tokens-[date].md`
3. **If visual exists**: `combined-findings-[component]-[date].md`
4. **Metrics file**: `technical-metrics-[date].json` with:
   ```json
   {
     "duplication_percentage": X,
     "token_coverage": X,
     "component_reuse": X,
     "hardcoded_values": X,
     "important_count": X
   }
   ```

This review identifies systematic issues causing visual problems and provides actionable technical solutions.