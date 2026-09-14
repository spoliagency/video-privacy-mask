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
