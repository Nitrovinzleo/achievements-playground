<p align="center">
  <img src="./assets/banner.svg" alt="GitHub Achievements Toolkit Banner" width="100%" />
</p>

<p align="center">
  <a href="https://github.com/Nitrovinzleo/achievements-playground/stargazers">
    <img src="https://img.shields.io/github/stars/Nitrovinzleo/achievements-playground?style=for-the-badge&color=f2cc60&logo=github" alt="Stars" />
  </a>
  <a href="https://github.com/Nitrovinzleo/achievements-playground/network/members">
    <img src="https://img.shields.io/github/forks/Nitrovinzleo/achievements-playground?style=for-the-badge&color=58a6ff&logo=git" alt="Forks" />
  </a>
  <a href="./LICENSE">
    <img src="https://img.shields.io/badge/License-MIT-3fb950?style=for-the-badge" alt="MIT License" />
  </a>
  <a href="./CONTRIBUTING.md">
    <img src="https://img.shields.io/badge/PRs-Welcome-a371f7?style=for-the-badge" alt="Contributions Welcome" />
  </a>
  <img src="https://img.shields.io/badge/Shell-PowerShell%20%7C%20Bash-2ea043?style=for-the-badge&logo=gnubash&logoColor=white" alt="PowerShell and Bash" />
</p>

<p align="center">
  <strong>English</strong> | <a href="./README_FR.md">Version Française</a>
</p>

---

A hands-on toolkit and reference sandbox explaining how GitHub Profile Achievements work under the hood, with ready-to-run **PowerShell** and **Bash** scripts using the GitHub REST and GraphQL APIs.

> **Quick note:** If this guide or any script helps you unlock your profile badges, consider dropping a ⭐ on the repository — it helps others discover it and helps unlock the **Starstruck** badge!

---

## Obtainable Badges & Tiers

| Visual | Achievement | Tiers | How to Trigger | Scripts |
| :---: | :--- | :--- | :--- | :--- |
| <img src="https://github.githubassets.com/assets/quickdraw-default-39c6aec8ff89.png" width="52" alt="Quickdraw" /> | **Quickdraw** | Single | Close an Issue or PR within 5 minutes of opening it. | [`quickdraw.ps1`](./scripts/quickdraw.ps1) / [`quickdraw.sh`](./scripts/quickdraw.sh) |
| <img src="https://github.githubassets.com/assets/yolo-default-be0bbff04951.png" width="52" alt="YOLO" /> | **YOLO** | Single | Merge a Pull Request without a code review. | Standard Git workflow |
| <img src="https://github.githubassets.com/assets/pair-extraordinaire-default-579438a20e01.png" width="52" alt="Pair Extraordinaire" /> | **Pair Extraordinaire** | Base: 1 · Bronze: 10 · Silver: 24 · Gold: 48 | Merge a PR containing a commit with a valid `Co-authored-by:` Git trailer. | [`pair-extraordinaire.ps1`](./scripts/pair-extraordinaire.ps1) / [`pair-extraordinaire.sh`](./scripts/pair-extraordinaire.sh) |
| <img src="https://github.githubassets.com/assets/galaxy-brain-gold-9c2c03fd1acf.png" width="52" alt="Galaxy Brain" /> | **Galaxy Brain** | Base: 2 · Bronze: 8 · Silver: 16 · Gold: 32 | Have your replies marked as **Accepted Answer** in Q&A Discussions. | [`galaxy-brain.ps1`](./scripts/galaxy-brain.ps1) |
| <img src="https://github.githubassets.com/assets/pull-shark-default-498c279a747d.png" width="52" alt="Pull Shark" /> | **Pull Shark** | Base: 2 · Bronze: 16 · Silver: 128 · Gold: 1024 | Merge Pull Requests into a repository's default branch. | [`pull-shark.ps1`](./scripts/pull-shark.ps1) / [`pull-shark.sh`](./scripts/pull-shark.sh) |
| <img src="https://github.githubassets.com/assets/public-sponsor-default-9fa68986b057.png" width="52" alt="Public Sponsor" /> | **Public Sponsor** | Single | Sponsor any open-source developer or organization via [GitHub Sponsors](https://github.com/sponsors). | Manual (from $1) |
| <img src="https://github.githubassets.com/assets/starstruck-gold-a35e077693cc.png" width="52" alt="Starstruck" /> | **Starstruck** | Base: 16 · Bronze: 128 · Silver: 512 · Gold: 4096 | Earn stars on one of your public repositories from unique users. | Community |

---

## Quick Usage

### 1. Quickdraw
Opens an issue and closes it 3 seconds later via the GitHub REST API.

```powershell
# PowerShell (Windows)
./scripts/quickdraw.ps1 -RepoOwner "YOUR_USER" -RepoName "YOUR_REPO" -Token "ghp_xxx"
```

```bash
# Bash (Linux / macOS)
chmod +x ./scripts/quickdraw.sh
./scripts/quickdraw.sh "YOUR_USER" "YOUR_REPO" "ghp_xxx"
```

---

### 2. Pair Extraordinaire
Creates a branch and a properly formatted co-authored commit (`Co-authored-by: Name <email>`), then pushes it so you can merge the PR. Both the author and co-author receive credit.

```powershell
# PowerShell
./scripts/pair-extraordinaire.ps1 -CoAuthorName "FriendHandle" -CoAuthorEmail "friend@example.com"
```

```bash
# Bash
chmod +x ./scripts/pair-extraordinaire.sh
./scripts/pair-extraordinaire.sh "FriendHandle" "friend@example.com"
```

---

### 3. Pull Shark
Creates and merges a small batch of lightweight Pull Requests into `main` while respecting API pacing.

```powershell
# PowerShell
./scripts/pull-shark.ps1 -RepoOwner "YOUR_USER" -RepoName "YOUR_REPO" -Token "ghp_xxx" -Count 5
```

```bash
# Bash (requires curl and jq)
chmod +x ./scripts/pull-shark.sh
./scripts/pull-shark.sh "YOUR_USER" "YOUR_REPO" "ghp_xxx" 5
```

---

### 4. Galaxy Brain
Automates Q&A Discussion creation, answering, and marking answers as accepted via the GitHub GraphQL API. Make sure **Discussions** are enabled in your repository settings first.

```powershell
./scripts/galaxy-brain.ps1 -RepoOwner "YOUR_USER" -RepoName "YOUR_REPO" `
  -QuestionerToken "TOKEN_USER_A" -AnswererToken "TOKEN_USER_B" -Count 2
```

---

### 5. YOLO & Public Sponsor
- **YOLO:** Push any branch, open a Pull Request, and merge it directly into `main` without requesting a review.
- **Public Sponsor:** Visit [github.com/sponsors](https://github.com/sponsors) and support any open-source maintainer (one-time or monthly).

---

## Bonus Profile Highlights

In addition to Achievements, you can unlock two free official badges displayed in the **Highlights** section of your GitHub profile:

| Badge | How to Unlock | Cost |
| :--- | :--- | :---: |
| **Developer Program Member** | Register in one click at [github.com/developer/register](https://github.com/developer/register) (instant). | Free |
| **GitHub PRO** | Available for free to students via the [GitHub Student Developer Pack](https://education.github.com/pack) using your school email and enrollment proof (also includes GitHub Copilot Pro). | Free (Students) |

---

## Good Practices & Rate Limits
- Always pace API calls and avoid running huge batches on brand-new accounts to stay within GitHub's acceptable use policies.
- Achievement updates are processed asynchronously by GitHub and may take from a few minutes up to 24 hours to appear on your profile.

---

## Repository Structure

```text
├── assets/
│   └── banner.svg
├── scripts/
│   ├── quickdraw.ps1 / quickdraw.sh
│   ├── pair-extraordinaire.ps1 / pair-extraordinaire.sh
│   ├── pull-shark.ps1 / pull-shark.sh
│   └── galaxy-brain.ps1
├── AI_INSTRUCTIONS.md
├── CONTRIBUTING.md
├── LICENSE
├── README.md
└── README_FR.md
```

---

<p align="center">
  If this repository helped you out, please consider leaving a <strong>⭐ Star</strong>!
  <br />
  Licensed under the <a href="./LICENSE">MIT License</a>.
</p>
