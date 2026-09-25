# Laws of UX: Cursor plugin

Applies the 30 Laws of UX (https://lawsofux.com/) when building web and mobile interfaces in Cursor.

## Contents

- `laws-of-ux/skills/laws-of-ux/SKILL.md`: the full skill (all 30 laws, workflow, tensions, review checklist). Agent decides when to use it, or call `/laws-of-ux`.
- `laws-of-ux/rules/laws-of-ux-ui-files.mdc`: auto-attached rule for UI files (tsx, jsx, vue, svelte, html, blade.php, css, scss, swift, kt, dart) with the minimum bar.
- `laws-of-ux/commands/ux-review.md`: `/ux-review` command to audit and fix a screen or diff.
- `.cursor-plugin/marketplace.json`: lets this repo be imported as a team marketplace.

## Install for yourself (local)

1. Copy the `laws-of-ux` folder to `~/.cursor/plugins/local/laws-of-ux`.
2. Run **Developer: Reload Window** in Cursor.
3. Check it appears under **Customize**.

On Teams or Enterprise, an admin must enable **Allow Local Plugin Imports** (Dashboard > Settings > Security & Identity > Marketplace and Plugins).

## Install for the team (team marketplace)

Cursor does not take zip uploads. Push the contents of this bundle (keeping `.cursor-plugin/` at the repo root) to a Git repo (GitHub, GitLab, Bitbucket or Azure DevOps), then:

1. Dashboard > Plugins & MCPs > Team Marketplaces > **Add Marketplace** > **Import from Repo**, and paste the repo URL.
2. Add `laws-of-ux` to the marketplace and set its install mode (Default Off, Default On or Required).
3. Set Marketplace Access and save.
