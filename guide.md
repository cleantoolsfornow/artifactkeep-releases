# ArtifactKeep User Guide

**A local-first desktop app for organizing AI prompts, images, conversations, and model libraries.**

---

## Table of Contents

1. [What is ArtifactKeep?](#what-is-artifactkeep)
2. [Why Use ArtifactKeep?](#why-use-artifactkeep)
3. [Getting Started](#getting-started)
4. [Navigation and Layout](#navigation-and-layout)
5. [Libraries and Views](#libraries-and-views)
   - [Image Prompts](#image-prompts)
   - [System Prompts](#system-prompts)
   - [Images](#images)
   - [Conversations](#conversations)
   - [Model Library](#model-library)
   - [Help](#help)
   - [Settings](#settings)
6. [Core Features and Workflows](#core-features-and-workflows)
   - [Unified Folder Behavior](#unified-folder-behavior)
   - [Search, Filters, and View Modes](#search-filters-and-view-modes)
   - [Bulk Actions and Undo Delete](#bulk-actions-and-undo-delete)
   - [Prompt Export and Import](#prompt-export-and-import)
   - [Image Metadata and Prompt Creation](#image-metadata-and-prompt-creation)
   - [Linked Image Folders](#linked-image-folders)
   - [Performance and Scalability](#performance-and-scalability)
7. [Keyboard Shortcuts](#keyboard-shortcuts)
8. [Data Storage and Privacy](#data-storage-and-privacy)
9. [Technical Architecture](#technical-architecture)

---

## What is ArtifactKeep?

ArtifactKeep is a local-first desktop application built with [Tauri](https://tauri.app/) that helps you organize and reuse AI assets: prompts, generated images, conversation files, and local model indexes.

Everything runs on your machine. Data is stored in local files and folders.

**Current Version**: 2.0.5

---

## Why Use ArtifactKeep?

### Centralized Asset Management

Manage image prompts, system prompts, images with metadata, conversations, and model references in one app.

### Local and Private

Data is stored in local JSON files and folders in your app data directory.

### Built for Large Libraries

Windowed rendering, lazy loading, and background processing help maintain responsiveness with large datasets.

### Metadata-Aware Workflows

Import PNG files, extract generation metadata, and turn that metadata into reusable prompt cards.

### Cross-Platform

ArtifactKeep is built with Tauri and targets macOS, Windows, and Linux.

---

## Getting Started

1. Install and launch ArtifactKeep.
2. On first run, ArtifactKeep creates required data files in your app data directory.
3. Open each library from the sidebar and use the welcome cards for orientation.
4. Start building your library:
   - Create prompts and tags.
   - Import PNG images.
   - Import conversation files.
   - Add model folders for indexing.

---

## Navigation and Layout

- **Sidebar**: Navigate between libraries, Help, and Settings.
- **Folder Subnav**: Library folders appear under sidebar entries for quick navigation.
- **Sticky Headers**: Search, filters, and actions stay visible while scrolling.
- **Folder Detail Headers**: In-folder mode shows folder name, item count, and folder-level actions.
- **View Modes**: Card/list toggles are available where supported.

---

## Libraries and Views

### Image Prompts

Store and organize prompts for image generation.

- Prompt editor supports positive prompt, negative prompt, notes, base models, LoRAs, and tags.
- Live stats show characters, words, and an estimated token count.
- Auto title generation uses a local title generator.
- Favorites are pinned to the top.
- Supports folders, drag and drop, search, filters, and card/list modes.
- Filters include base models, LoRAs, tags, and "Has Negative Prompt".
- Bulk actions include copy, duplicate, move, export, and delete.
- Import supports JSON templates and app backup JSON with preflight validation.
- Export uses a guided flow:
  - Backup JSON for restore/merge in ArtifactKeep.
  - Portable Markdown/Text/CSV files for outside use.

### System Prompts

Manage reusable system instructions and personas.

- Prompt editor supports prompt text, notes, LLM models, and tags.
- Supports profile image and multi-image gallery references.
- Favorites are pinned to the top.
- Supports folders, drag and drop, search, filters, and card/list modes.
- Filters include LLM models and tags.
- Bulk actions include copy, duplicate, move, export, and delete.
- Import supports:
  - JSON templates and backup JSON.
  - Markdown files (`.md`, `.markdown`) as prompt bodies.
- Export supports backup JSON and portable files, with system-specific formatting:
  - Body only
  - Title + body
  - Metadata header + body

### Images

A gallery for imported images and extracted metadata.

- Image library import is PNG-focused (`.png`).
- Import modal can optionally create image prompts from imported image metadata.
- Supports standard folders and linked folders.
- Linked folders can scan for new PNG files and import only unseen files.
- Search scopes: Everything, Prompt, Model, Filename.
- Filters include models, tool hints, and prompt-status flags.
- Detail modal shows:
  - File info
  - Prompts
  - Models
  - Generation settings
  - Raw metadata
- Detail modal actions include copying prompt blocks and creating an image prompt from metadata.
- Utilities include metadata rescan and thumbnail regeneration.
- Rescan settings include a top-level toggle for prompt creation on rescan.
- Bulk actions include move and delete.
- Favorites and quick copy-positive-prompt actions are supported.

### Conversations

Archive exported chat logs from LLM tools.

- Supported import formats: `.json`, `.txt`, `.md`, `.markdown`, `.log`, `.yaml`, `.yml`, `.html`.
- Detail modal supports editing title, notes, LLM models, and tags.
- Markdown and text files show formatted preview in the detail modal.
- Other formats use raw preview, with load-more behavior for large files.
- Export original file from the detail modal.
- Bulk export selected conversations to a chosen folder.
- Supports folders, drag and drop, search, filters, and card/list modes.
- Filters include LLM models and tags.
- Favorites are pinned to the top.

### Model Library

Index and organize local model files without moving them.

- Add model folders and scan for: `.safetensors`, `.ckpt`, `.pt`, `.gguf`.
- Folder settings include category and include-subfolders option.
- Type categories: Auto, LoRAs, Checkpoints, UNet, VAE, Embeddings, LLM, Other.
- Folder status tracks linked/scanning/unavailable states.
- Missing entries are tracked and can be shown with a folder-level toggle.
- Relink workflow supports smart matching to preserve existing metadata when paths change.
- Entry details include type, tags, notes, file size, modified date, and copy-path.
- Supports folder/entry card and list modes, search, filtering, and bulk delete.
- Deleting folders or entries removes index records only, not the original files on disk.

### Help

The Help page includes:

- An **Open User Guide** button that loads this guide in-app.
- A feedback email action (copy to clipboard).
- A support link (Ko-fi).

### Settings

Settings includes:

- Theme toggle (light/dark).
- Image prompt model lists (base models and LoRAs).
- System prompt model list (LLM models).
- Reset welcome cards for all views.
- About card with current app version.

---

## Core Features and Workflows

### Unified Folder Behavior

- Image Prompts, System Prompts, Images, Conversations, and Model Library all support folder organization.
- Root view can show unfiled items and folders together.
- Drag and drop supports moving selected items into folders (where supported).
- Sidebar folder subnav provides quick jump into specific folders.

### Search, Filters, and View Modes

- Each library has search.
- Filters are library-specific:
  - Image Prompts: base models, LoRAs, tags, negative prompt flag.
  - System Prompts: LLM models and tags.
  - Images: models, tools, prompt status, plus search scopes.
  - Conversations: LLM models and tags.
  - Model Library: type and missing status (inside folder detail).
- Card/list mode toggles are available in prompt, conversation, and model views.

### Bulk Actions and Undo Delete

- Multi-select supports checkbox selection and shift-click ranges.
- Bulk actions vary by library (move, export, delete, and more where applicable).
- Delete flows use an undo window when available.

### Prompt Export and Import

Prompt libraries use a guided export/import workflow.

- **Backup JSON**:
  - Includes `version`, `exportedAt`, `type`, and `items`.
  - Intended for ArtifactKeep restore/merge.
  - Backup type mismatch is blocked.
- **Portable Export**:
  - Markdown/Text/CSV output.
  - Markdown/Text can be single-file or ZIP of separate files.
  - CSV is single-file only.
- **Import Preflight**:
  - Shows total/valid/invalid counts.
  - Shows missing prompt and unknown-field counts.
  - Lists validation issues before confirmation.
- **Backup conflict handling**:
  - Existing IDs are skipped.
  - Duplicate IDs within the import keep the first occurrence.
  - Missing IDs are generated.
  - `folderId` from backups is not restored (backup items import unfiled).
- **System prompt backup media handling**:
  - Missing image/gallery references are removed during import.

### Image Metadata and Prompt Creation

- Metadata extraction is optimized for PNG metadata chunks.
- Tool hint detection includes ComfyUI and A1111-style metadata patterns.
- Image prompt creation from metadata is available through:
  - Import option toggle
  - Linked-folder import setting
  - Metadata rescans (folder and top-level settings)
  - Image detail modal "Create Prompt From Image"
- Prompt fingerprinting is used to skip duplicates.
- Auto-created prompts can receive a local generated title.

### Linked Image Folders

- Linked folders point to a local directory and scan for new PNG files.
- Scan dedupe uses source path + source modified time + source file size.
- Linked folders support per-folder auto-create-prompt behavior.
- Folder-level rescan metadata action can scan linked folder content and then refresh metadata.

### Performance and Scalability

- Windowed rendering with incremental loading for large lists.
- Lazy thumbnail loading in image grids.
- Background thumbnail generation and metadata extraction.
- Debounced write queue for JSON persistence.

---

## Keyboard Shortcuts

| Context | Shortcut | Action |
|---------|----------|--------|
| Modals | `Esc` | Close open modal |
| Prompt / Conversation modals | `Cmd/Ctrl + Enter` | Save |
| Selectable lists | `Shift + Click` | Range selection |

---

## Data Storage and Privacy

### Location

ArtifactKeep stores data in your local app data directory.

- **macOS**: `~/Library/Application Support/com.artifactkeep.app/`
- **Windows**: `%APPDATA%\\com.artifactkeep.app\\`
- **Linux**: `~/.local/share/com.artifactkeep.app/`

### File Structure

Core JSON files:

- `image-prompts.json`
- `system-prompts.json`
- `images.json`
- `conversations.json`
- `models-library.json`
- `image-models.json`
- `llm-models.json`
- `image-tags.json`
- `system-tags.json`
- `conversation-tags.json`
- `settings.json`

Asset folders:

- `images/` imported images
- `thumbnails/` generated thumbnails
- `raw/` externalized large raw metadata blobs
- `conversations/original/` imported conversation source files
- `system-prompt-images/` system prompt profile images
- `system-prompt-gallery/` system prompt gallery images

To back up everything, copy or zip the full app data directory.

---

## Technical Architecture

ArtifactKeep is a Tauri desktop app with a JavaScript frontend and Rust backend.

- **Frontend**: Vanilla ES modules and modular CSS.
- **Backend (Rust)**: File I/O, folder scanning, metadata extraction, thumbnail generation, and title generation.
- **Data Layer**: JSON schema validation/repair plus debounced persistence via write queue (`src/data.js`).
- **Shared Utilities**: Selection manager, filter manager, drag manager, reusable modals, import/export helpers.
