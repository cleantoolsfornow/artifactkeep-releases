# ArtifactKeep v2.0.4 Release Notes

> Draft generated from git history. Review and edit before publishing.

Date: 2026-02-10
Previous release tag: v2.0.3
Commit range: `v2.0.3..HEAD`
Commit count: 19

## Breaking Changes

- No notable changes in this category.

## Added

- Add folder-level export actions using existing bulk export flow (`a667c97`)
- Refine modal styles for import/export functionality and enhance responsiveness (`ab401e5`)
- Update user guide to reflect new export/import functionality and improve clarity (`2822673`)
- Implement bulk export/import functionality with new modal flow (`34f798d`)
- Enhance prompt import functionality to support Markdown files and add corresponding tests (`5bf9c6c`)
- Implement Tauri-based file export with fallback and add tests for bulk export functionality (`4fbcc8f`)

## Improved

- Updated release process with release notes. (`39915d1`)
- Remove Playwright tests and configuration (`9fd524e`)
- Revise image prompts for clarity and detail; add Danbooru-style presets for anime illustrations (`dba9097`)
- Enhance prompt card preview lines and structure for image prompt cards (`8a8e596`)
- Update border-radius for various components to use new radius variable for consistency (`05c07f9`)
- Update badge styles and icons for improved visual consistency and accessibility (`381138e`)
- Replace theme toggle buttons with SVG icons for improved accessibility and visual consistency (`404362a`)
- Replace text icons with SVGs for improved visual consistency across components (`cc5cc4f`)
- Enhance sidebar and navigation styles with gradients and improved hover effects (`b1d60c1`)
- Update WelcomeCard component styles for improved layout and visual consistency (`16f07ff`)
- Refactor styles for consistency and visual coherence across components (`1ff880d`)

## Fixed

- No notable changes in this category.

## Internal

- Redid dev tools to present better showcase demo data (`c3f32b0`)
- Standardize markdown link anchors in UserGuide.md. (`2e2dc02`)

## Full Commit List

- `39915d1` Updated release process with release notes.
- `a667c97` feat(prompts): add folder-level export actions using existing bulk export flow
- `ab401e5` feat: refine modal styles for import/export functionality and enhance responsiveness
- `2822673` feat: update user guide to reflect new export/import functionality and improve clarity
- `34f798d` feat: implement bulk export/import functionality with new modal flow
- `5bf9c6c` feat: enhance prompt import functionality to support Markdown files and add corresponding tests
- `4fbcc8f` feat: implement Tauri-based file export with fallback and add tests for bulk export functionality
- `9fd524e` refactor: remove Playwright tests and configuration
- `dba9097` style: Revise image prompts for clarity and detail; add Danbooru-style presets for anime illustrations
- `8a8e596` style: Enhance prompt card preview lines and structure for image prompt cards
- `c3f32b0` redid dev tools to present better showcase demo data
- `05c07f9` style: Update border-radius for various components to use new radius variable for consistency
- `381138e` style: Update badge styles and icons for improved visual consistency and accessibility
- `404362a` style: Replace theme toggle buttons with SVG icons for improved accessibility and visual consistency
- `cc5cc4f` style: Replace text icons with SVGs for improved visual consistency across components
- `b1d60c1` style: Enhance sidebar and navigation styles with gradients and improved hover effects
- `16f07ff` style: Update WelcomeCard component styles for improved layout and visual consistency
- `1ff880d` Refactor styles for consistency and visual coherence across components
- `2e2dc02` docs: Standardize markdown link anchors in UserGuide.md.
