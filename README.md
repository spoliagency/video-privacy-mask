# Video Privacy Mask

Free, reusable instructions for protecting sensitive information in screen-recorded videos without hiding useful context.

It helps an agent create a separate, publishable copy, limit masks to the precise scene and on-screen region that need protection, and check the frames around every cut or layout change.

## What it covers

- Browser domains, email identifiers, aliases, credentials, and other private on-screen data.
- Light blur when it is sufficient, stronger masking only when necessary.
- Scene boundaries and scrolling dashboards, so a mask does not appear too early, linger too long, or drift away from the protected item.
- Final video, audio, duration, and frame-based privacy checks.

## Requirements

- A local video tool such as FFmpeg.
- Videos stay on the user's own computer unless they explicitly choose another workflow.

## What happens after installation

The student does not need to understand FFmpeg before asking for help. They can invoke the skill and write a normal request, for example:

```text
I need to hide the domains and email identifiers in this screen recording. Keep the workflow visible and use a light blur.
```

The skill will explain the next step, check whether a local video renderer is ready, and proceed if it is. If it is not ready, it explains why a renderer is needed and offers installation guidance for the student's operating system; it never installs software without their approval. Once the renderer is available, the conversation continues from the same request.

## Install in Claude Code

After this repository is published, run these commands in Claude Code:

```text
/plugin marketplace add spoliagency/video-privacy-mask
/plugin install video-privacy-mask@video-privacy-mask
```

Then invoke it with:

```text
/video-privacy-mask:video-privacy-mask
```

## Install in Codex

Ask Codex to use its `skill-installer` skill to install this GitHub repository's skill at:

```text
plugins/video-privacy-mask/skills/video-privacy-mask
```

After installation, invoke it explicitly as `$video-privacy-mask` or let Codex select it for a relevant video-privacy task.

## Privacy

This repository contains reusable guidance only. It intentionally excludes source videos, outputs, personal paths, domains, email addresses, credentials, and keys. Do not commit media or private configuration.

## License

[MIT](LICENSE)
