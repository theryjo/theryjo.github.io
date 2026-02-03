---
title: Omnitool
date: 2023-11-13
tags: ['chrome Extension', 'vue', 'featured']
---
<b><u>[Omnitool](https://github.com/theryjo/omnitool)</u></b> is a prototype Chrome extension allowing fast access to custom utilities.

<div style="text-align: center">
<video controls autoplay loop muted width="375" style="text-align: center">
  <source src="/images/2-omnitool/extension-seq.mp4" type="video/mp4">
  This browser does not display the video tag.
</video>
</div>
<br />

Omnitool was inspired by my developer experience on a small team supporting a suite of web applications for a Fortune 50 client. Day-to-day operations included tedious, repeated tasks such as:
- _Navigating complicated environments_.
- _Making frequent API calls to trigger cache clears and other operations_.
- _Inspecting and reproducing web application state_.
- _Debugging client-initiated service calls_.

Team members had previously written a handful of small and useful one-off browser extensions. I designed Omnitool as a way to consolidate these one-off tools in an efficient, flexible interface.

Omnitool has an omnibox-style interface for utility search and invocation. It offers speed, simplicity, and flexibility for tasks lacking support from built-in browser tools.

Some noteworthy features:

1. SIMPLICITY
   - _A unified tool search interface_.
   - _A consistent command-based model for tool invocation_.
   - _A pattern for wrapping pre-existing pages as tools with an 'iframe'_.

<div style="white-space: nowrap">
<img src="/images/2-omnitool/extension-help.png"  width="300" alt="help screenshot" style="display: inline-block; vertical-align: top">
<img src="/images/2-omnitool/extension-autocomplete.png"  width="300" alt="autocomplete screenshot" style="display: inline-block; vertical-align: top">
</div>
<br />

2. FAST
    - _Opens with a configurable keyboard shortcut (rec. <kbd>CMD</kbd> + <kbd>K</kbd>)_.
    - _Autocomplete for tool search_.
    - _An invocation history with shortcuts for tool selection and re-invocation_.
 
<br />
<div style="white-space: nowrap">
<img src="/images/2-omnitool/extension-lorem-history.png"  width="300" alt="execution history screenshot" style="display: inline-block; vertical-align: top">
<img src="/images/2-omnitool/extension-lorem-param.png"  width="300" alt="lorem command screenshot" style="display: inline-block; vertical-align: top">
</div>
<br />

3. FLEXIBLE
    - _Tool definitions that support a wide range of custom tools_.
    - _Optional tool implementations patterns for tool panes, tool execution output, and hybrid text/GUI tool interfaces_.
    - _Tool 'pinning' to allow for multiple tool selection_.

<br />
<div style="white-space: nowrap">
<img src="/images/2-omnitool/extension-links-pop.png"  width="250" alt="links tool screenshot" style="display: inline-block; vertical-align: top">
<img src="/images/2-omnitool/extension-color.png"  width="250" alt="color tool screenshot" style="display: inline-block; vertical-align: top">
<img src="/images/2-omnitool/extension-env-tab.png"  width="250" alt="pinned tool screenshot" style="display: inline-block; vertical-align: top">
</div>
<br />

The Omnitool 'demo-tools' branch includes tool samples that showcase these features (as shown in the above screenshots).

The tool development pattern is very straightforward. A tool definition consists of a small package of files.

<img src="/images/2-omnitool/tool-files.png"  width="225" alt="tool definition files screenshot" style="display: inline-block; vertical-align: top">
<br />

The tool logic and metadata are defined in a JS/TS module.

<img src="/images/2-omnitool/tool-code.png"  width="450" alt="sample tool logic screenshot" style="display: inline-block; vertical-align: top">
<br />

The optional tool UI is defined in a linked Vue component.

<img src="/images/2-omnitool/tool-pane.png"  width="450" alt="tool Vue component screenshot" style="display: inline-block; vertical-align: top">
<br />
<br />

See <u>[source](https://github.com/theryjo/omnitool/tree/demo-tools)</u> on GitHub.

Some outstanding items:
- Omnitool is not listed in the Chrome Web Store. Although I haven't tried yet, this may be impossible due to the store's "single purpose" policy for extensions, which has been in effect since 2013. This [policy](https://developer.chrome.com/docs/webstore/program-policies/quality-guidelines-faq/#:~:text=To%20maintain%20the%20quality%20of,in%20the%20Chrome%20Web%20Store.) requires "extensions to have only a single purpose with respect to its subject matter or browser function". In the meantime, the extension may be loaded in developer mode as an "unpacked extension" without impacting functionality.
- Adding a new tool currently requires a rebuild and reload. Hot-swappable tools would enhance ease of tool sharing and developer synchronization.
- Omnitool lacks global and tool-specific configuration options. It does save a small amount of state on close, but adding configuration or customization would require an update.

Thank you for reading!
