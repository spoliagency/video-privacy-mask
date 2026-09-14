---
name: video-privacy-mask
description: "Protect sensitive information in screen-recorded videos with precise, non-destructive masks. Use for domains, email identifiers, aliases, credentials, and other private on-screen data."
---

# Video Privacy Mask

Create a publishable copy of a video while preserving the requested visible context.

## Delivery

Deliver completed copies to a user-specified folder. If no folder is specified, use an `outputs` folder next to the working files. Keep intermediate renders separate and do not overwrite an existing delivery file unless the user asks.

## First use and local video tool

When a user invokes this skill, begin with a short, approachable preflight:

1. Explain that you will make a separate, publishable copy and ask them to identify the source video and the items to protect.
2. Check whether FFmpeg or another compatible local video renderer is available, without changing their system.
3. If a renderer is ready, say so briefly and continue with the edit.
4. If no renderer is available, explain in plain language that this skill plans and verifies the edit, while the local renderer produces the new video file. Offer platform-appropriate installation guidance or a compatible existing tool; do not install software without the user's explicit approval.
5. Keep the same conversation open after the tool is ready. The user should not have to repeat the request or relocate their media.

## Workflow

1. Identify the source video and create a separately named output. Never modify the original.
2. Confirm exactly what must be hidden and what may remain visible. Examples: hide only a browser domain rather than the whole address bar; hide the local part of an email while retaining its provider; preserve a workflow canvas while masking only identifying aliases.
3. Build a scene map before choosing time ranges: inspect every visual cut or page switch near protected content, then check the first and last frames of each relevant scene. Scope a mask to the scene that actually contains the sensitive information; it must not appear early over a talking-head segment or linger after a switch to an unrelated app.
4. For a dashboard that scrolls or repositions a list, map each layout state separately and use overlapping protection only during the scroll itself. Do not reuse a broad dashboard interval merely because the browser is still open.
5. Use FFmpeg or another reproducible local workflow. Prefer the least intrusive treatment that still makes the protected text unreadable:
   - soft blur for text over textured or light backgrounds;
   - for workflow canvases, test a light blur on a representative label first; preserve the nodes and connections rather than defaulting to opaque rectangles;
   - use a color-matched, opaque patch only when a light blur cannot keep the protected text unreadable;
   - use a stronger mask for passwords, tokens, API keys, addresses, personal contacts, or credentials.
6. Render to a new file, retaining the original resolution, duration, and audio unless the user asks to change them.

## Quality checks

- Verify the final duration and video/audio streams.
- Inspect frames during every distinct masked scene, including immediately before and after every time boundary and after any long interval where a page may have moved.
- Review a boundary contact sheet (or equivalent frame set) after the final render. Confirm the mask begins with the protected scene, changes position with a scrolling layout, and is absent from all intervening scenes.
- Confirm that intentional visible details remain visible and protected information cannot be read at normal or enlarged viewing.
- Deliver the output path and state that the original was left unchanged.

Ask a focused clarification only when the sensitive items or time ranges cannot be safely inferred.
