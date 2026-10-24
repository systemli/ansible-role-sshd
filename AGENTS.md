# AGENTS.md

Ansible role that installs and configures the OpenSSH daemon on Debian, with optional central authorized key management.

## Layout

- `defaults/main.yml`: all role variables with defaults; document new ones in the README
- `tasks/`: `main.yml`, `authorized_keys.yml` (central key management), `goss.yml` (optional goss tests)
- `templates/`: `sshd_config.j2` and the goss test template
- `meta/main.yml`: Galaxy metadata and supported platforms
- `molecule/default/`: local integration test (Docker, Debian 13) with a `prepare.yml` and `converge.yml`
- `requirements.yml`: collections needed by the role (`ansible.posix`)

## Checks

- `ansible-lint .` must pass (config in `.ansible-lint`); it creates `.ansible/`, which is git ignored, never commit it
- `yamllint .` uses `.yamllint`
- `molecule test` runs the role in a container; CI runs it on Debian 12 and 13 via `systemli/github-ansible-workflow`

## Conventions

- Prefer fully qualified module names, quoted octal `mode` values and `true`/`false` booleans in new code
- Give every task a `name`
- Pin GitHub Actions to commit SHAs with a trailing `# vX.Y.Z` comment

## Commits and PRs

- Write in English, use conventional commit titles (`feat:`, `fix:`, `chore:`, `ci:`; `!` for breaking changes)
- The PR title sets the release-drafter label (`enhancement`, `bug`, `chore`, `breaking`); a breaking change bumps the major version
- Open PRs as draft and fill in `.github/pull_request_template.md`: what changed and why, plus a breaking changes section if needed
- Do not list changed files or claim test results in the description; CI covers that
