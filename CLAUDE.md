# CLAUDE.md — Animo Turnkey site

This repo is the public website for **Animo Turnkey**, the small-apps branch of Animo Investments, a division of Animo Network Strategies LLC (ANS). It hosts each app's privacy policy and support page, which the App Store and Google Play link to. The owner is Juan, a network engineer who is new to web publishing and Git. Explain Git, GitHub Pages and DNS steps in plain terms.

## Environment

- Developer workstation: **Kali Linux**, running as a normal user (never use `sudo`).
- Hosting: **GitHub Pages**, deploying the `main` branch root to <https://turnkey.animonetworkstrategies.com>. Merging to `main` publishes the site within a minute or two.
- Plain HTML and one shared `style.css`. No build tools, frameworks, package managers or JavaScript unless Juan asks.
- Each page is a folder with an `index.html` (`support/`, `privacy/<app>/`) so URLs end in a slash. Use relative links (`../style.css`), and keep every page's header, nav and footer the same.
- `CNAME` holds the custom domain and `.nojekyll` turns off Jekyll processing. Don't remove or edit either without asking.

## Git workflow (required)

1. **Never commit or push directly to `main`.** `main` is the live site.
2. Start every task with `git switch main && git pull`, then create a branch named for the work: `add-support-faq`, `update-caninecue-privacy`, `fix-footer-links`.
3. Make small, focused commits with clear messages.
4. Before opening a pull request, check that every relative link points to a file that exists, that every page has a `<title>` and a viewport meta tag, and that no placeholder text (`example.com`, `TODO`) is left in.
5. Push the branch and open a pull request with `gh pr create`. The description should cover what changed, why, and which URLs to check after merging.
6. **Do not merge pull requests.** Juan reviews and merges them himself on GitHub.

## Secrets

- This repo is **public**. Everything in it, including Git history, can be read by anyone.
- Never commit API keys, tokens, passwords, `.env` files, analytics IDs that should stay private, or personal contact details other than the published support address.
- If a task needs a secret, stop and ask Juan how he wants it handled.
- Never put the company's tax IDs or other identifying numbers in pages, commits or docs.

## Content rules

- Privacy policies must match what each app actually does. Before changing one, check the app's code and say which version of the app the change applies to. Update the "Last updated" date with any change to a policy's content.
- Never move or rename a page that is linked from a store listing without flagging it, because the old URL will break. Tell Juan which store links to update.
- No tracking scripts, cookies, ads or third-party embeds on the site.
- Legal wording questions go to Juan's lawyer or CPA; don't present policy text as legal advice.
