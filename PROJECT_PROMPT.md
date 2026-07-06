# Project Prompt

Use this prompt for the next portability pass on this fork:

```text
You are working on a fork of mudsort, a Decal plugin for Asheron's Call.

Current status:
- Item name filtering has been added and deployed locally.
- The project now builds on one machine by resolving Decal.Adapter, Decal .NET 4.0 PIA assemblies, and VirindiViewService from local install paths.
- The build supports optional overrides through mudsort.local.props and the DECAL_INSTALL_DIR, DECAL_PIA_DIR, and VIRINDI_INSTALL_DIR environment variables.

Your task is to finish the repository so it works cleanly for other developers without requiring hand edits to the project file.

Requirements:
1. Keep local builds working for the current machine layout.
2. Preserve the current plugin behavior and versioning approach.
3. Improve developer onboarding so a new contributor can build with minimal setup.
4. Prefer documented, overrideable configuration over hard-coded machine paths.
5. Do not remove the current local fallback paths unless you replace them with something equally reliable.

Concrete goals:
1. Review the build and packaging flow in mudsort.csproj and installer.nsi.
2. Decide whether Directory.Build.props, a better local props pattern, or clearer environment variable handling is the right long-term solution.
3. Add or update documentation so another Windows user can configure Decal, the PIAs, and VirindiViewService quickly.
4. If you change build configuration, validate with an actual Release build.
5. Keep the changes minimal and focused.

Useful local facts:
- Decal is installed under C:\Games\Decal on the current machine.
- VirindiViewService is installed under C:\Games\VirindiPlugins\VirindiViewService on the current machine.
- The plugin is registered in Decal under C:\Games\Decal Plugins\mudsort.

Output expectations:
- Summarize the portability changes.
- Note any residual build assumptions.
- Call out exactly what another developer still needs to configure, if anything.
```