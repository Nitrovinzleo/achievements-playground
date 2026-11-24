<p align="center">
  <img src="./assets/banner.svg" alt="Bannière GitHub Achievements Toolkit" width="100%" />
</p>

<p align="center">
  <a href="https://github.com/Nitrovinzleo/achievements-playground/stargazers">
    <img src="https://img.shields.io/github/stars/Nitrovinzleo/achievements-playground?style=for-the-badge&color=f2cc60&logo=github" alt="Étoiles" />
  </a>
  <a href="https://github.com/Nitrovinzleo/achievements-playground/network/members">
    <img src="https://img.shields.io/github/forks/Nitrovinzleo/achievements-playground?style=for-the-badge&color=58a6ff&logo=git" alt="Forks" />
  </a>
  <a href="./LICENSE">
    <img src="https://img.shields.io/badge/Licence-MIT-3fb950?style=for-the-badge" alt="Licence MIT" />
  </a>
  <a href="./CONTRIBUTING.md">
    <img src="https://img.shields.io/badge/Contributions-Bienvenues-a371f7?style=for-the-badge" alt="Contributions bienvenues" />
  </a>
  <img src="https://img.shields.io/badge/Shell-PowerShell%20%7C%20Bash-2ea043?style=for-the-badge&logo=gnubash&logoColor=white" alt="PowerShell et Bash" />
</p>

<p align="center">
  <a href="./README.md">English Version</a> | <strong>Français</strong>
</p>

---

Un guide pratique et une boîte à outils complète pour comprendre le fonctionnement des succès de profil GitHub, avec des scripts **PowerShell** et **Bash** prêts à l'emploi exploitant les APIs REST et GraphQL de GitHub.

> **Petit mot :** Si ce guide ou ces scripts vous aident à débloquer vos badges, laissez une petite ⭐ sur le dépôt ! Cela aide d'autres développeurs à le trouver et contribue à débloquer le badge **Starstruck**.

---

## Tableau des badges obtenables et paliers

| Visuel | Succès | Paliers | Condition d'obtention | Scripts |
| :---: | :--- | :--- | :--- | :--- |
| <img src="https://github.githubassets.com/assets/quickdraw-default-39c6aec8ff89.png" width="52" alt="Quickdraw" /> | **Quickdraw** | Unique | Fermer une Issue ou une PR en moins de 5 minutes après son ouverture. | [`quickdraw.ps1`](./scripts/quickdraw.ps1) / [`quickdraw.sh`](./scripts/quickdraw.sh) |
| <img src="https://github.githubassets.com/assets/yolo-default-be0bbff04951.png" width="52" alt="YOLO" /> | **YOLO** | Unique | Fusionner une Pull Request sans revue de code préalable. | Workflow Git classique |
| <img src="https://github.githubassets.com/assets/pair-extraordinaire-default-579438a20e01.png" width="52" alt="Pair Extraordinaire" /> | **Pair Extraordinaire** | Base : 1 · Bronze : 10 · Argent : 24 · Or : 48 | Fusionner une PR contenant un commit avec le trailer `Co-authored-by:`. | [`pair-extraordinaire.ps1`](./scripts/pair-extraordinaire.ps1) / [`pair-extraordinaire.sh`](./scripts/pair-extraordinaire.sh) |
| <img src="https://github.githubassets.com/assets/galaxy-brain-gold-9c2c03fd1acf.png" width="52" alt="Galaxy Brain" /> | **Galaxy Brain** | Base : 2 · Bronze : 8 · Argent : 16 · Or : 32 | Voir ses réponses marquées comme **Réponse acceptée** dans des Discussions Q&A. | [`galaxy-brain.ps1`](./scripts/galaxy-brain.ps1) |
| <img src="https://github.githubassets.com/assets/pull-shark-default-498c279a747d.png" width="52" alt="Pull Shark" /> | **Pull Shark** | Base : 2 · Bronze : 16 · Argent : 128 · Or : 1024 | Fusionner des Pull Requests sur la branche par défaut. | [`pull-shark.ps1`](./scripts/pull-shark.ps1) / [`pull-shark.sh`](./scripts/pull-shark.sh) |
| <img src="https://github.githubassets.com/assets/public-sponsor-default-9fa68986b057.png" width="52" alt="Public Sponsor" /> | **Public Sponsor** | Unique | Sponsoriser un développeur ou une organisation open-source via [GitHub Sponsors](https://github.com/sponsors). | Manuel (dès 1 $) |
| <img src="https://github.githubassets.com/assets/starstruck-gold-a35e077693cc.png" width="52" alt="Starstruck" /> | **Starstruck** | Base : 16 · Bronze : 128 · Argent : 512 · Or : 4096 | Recevoir des étoiles sur l'un de vos dépôts publics. | Communauté |

---

## Utilisation rapide

### 1. Quickdraw
Ouvre une issue et la referme 3 secondes plus tard via l'API REST GitHub.

```powershell
# PowerShell (Windows)
./scripts/quickdraw.ps1 -RepoOwner "VOTRE_PSEUDO" -RepoName "VOTRE_REPO" -Token "ghp_xxx"
```

```bash
# Bash (Linux / macOS)
chmod +x ./scripts/quickdraw.sh
./scripts/quickdraw.sh "VOTRE_PSEUDO" "VOTRE_REPO" "ghp_xxx"
```

---

### 2. Pair Extraordinaire
Crée une branche et un commit correctement formaté avec le trailer Git (`Co-authored-by: Nom <email>`), puis pousse la branche pour fusionner la PR. L'auteur et le co-auteur reçoivent tous les deux le badge.

```powershell
# PowerShell
./scripts/pair-extraordinaire.ps1 -CoAuthorName "PseudoAmi" -CoAuthorEmail "ami@example.com"
```

```bash
# Bash
chmod +x ./scripts/pair-extraordinaire.sh
./scripts/pair-extraordinaire.sh "PseudoAmi" "ami@example.com"
```

---

### 3. Pull Shark
Crée et fusionne un petit lot de Pull Requests sur `main` en respectant un délai entre chaque appel API.

```powershell
# PowerShell
./scripts/pull-shark.ps1 -RepoOwner "VOTRE_PSEUDO" -RepoName "VOTRE_REPO" -Token "ghp_xxx" -Count 5
```

```bash
# Bash (nécessite curl et jq)
chmod +x ./scripts/pull-shark.sh
./scripts/pull-shark.sh "VOTRE_PSEUDO" "VOTRE_REPO" "ghp_xxx" 5
```

---

### 4. Galaxy Brain
Automatise la création de discussions Q&A, l'envoi des réponses et la validation comme réponse acceptée via l'API GraphQL. Pensez à activer l'onglet **Discussions** dans les paramètres de votre dépôt.

```powershell
./scripts/galaxy-brain.ps1 -RepoOwner "VOTRE_PSEUDO" -RepoName "VOTRE_REPO" `
  -QuestionerToken "TOKEN_COMPTE_A" -AnswererToken "TOKEN_COMPTE_B" -Count 2
```

---

### 5. YOLO & Public Sponsor
- **YOLO :** Poussez une branche, ouvrez une PR et cliquez sur *Merge* sans demander de revue de code.
- **Public Sponsor :** Rendez-vous sur [github.com/sponsors](https://github.com/sponsors) et soutenez un mainteneur open-source (don ponctuel ou mensuel).

---

## Badges Bonus (Section Highlights)

En plus des Achievements, vous pouvez débloquer gratuitement deux badges officiels affichés dans la section **Highlights** de votre profil GitHub :

| Badge | Comment le débloquer | Coût |
| :--- | :--- | :---: |
| **Developer Program Member** | Inscrivez-vous en un clic sur [github.com/developer/register](https://github.com/developer/register) (instantané). | Gratuit |
| **GitHub PRO** | Gratuit pour les étudiants via le [GitHub Student Developer Pack](https://education.github.com/pack) avec votre adresse mail scolaire et votre justificatif d'inscription (inclut aussi GitHub Copilot Pro). | Gratuit (Étudiants) |

---

## Badges Retirés, Désactivés & Internes

Pour être exhaustif, d'autres badges existent dans l'historique ou en interne chez GitHub mais **ne peuvent pas être obtenus via une activité publique classique** :

| Badge | Catégorie | Raison |
| :--- | :---: | :--- |
| **Arctic Code Vault Contributor** | Retiré | Attribué uniquement pour les dépôts archivés lors du programme 2020. |
| **Mars 2020 Contributor** | Retiré | Attribué aux contributeurs des dépôts utilisés par l'hélicoptère Ingenuity (mission Mars 2020). |
| **Finishing Touch** | UI GitHub / Staff | Attribué pour des PRs améliorant directement la qualité de l'interface GitHub (Bronze : 4 · Argent : 16 · Or : 32). |
| **Proxima Pioneer / Staffshipper / Staffuser** | Interne | Réservés exclusivement aux employés GitHub sur l'infrastructure interne Proxima. |
| **Heart On Your Sleeve** | Désactivé | Badge expérimental lié aux réactions (actuellement désactivé). |
| **Open Sourcerer** | Désactivé | Badge expérimental multi-dépôts (actuellement désactivé). |

---

## FAQ & Dépannage

- **Pourquoi Galaxy Brain ne se débloque-t-il pas quand j'accepte ma propre réponse ?**
  GitHub ignore les réponses auto-validées : la personne qui clique sur *Mark as answer* doit être différente de l'auteur de la réponse. Notez aussi que les discussions de `github/community` ne comptent plus pour les succès.
- **Pourquoi Pair Extraordinaire ne s'affiche-t-il pas pour l'auteur principal du commit ?**
  Pour un commit donné, GitHub attribue le badge à la personne citée dans `Co-authored-by:`, pas à l'auteur principal. Il faut inverser les rôles pour que les deux collaborateurs l'obtiennent.
- **Peut-on changer la couleur de peau sur Quickdraw et Starstruck ?**
  Oui, directement via votre préférence d'émojis dans [github.com/settings/appearance](https://github.com/settings/appearance).
- **Pourquoi mon badge n'apparaît-il pas instantanément ?**
  GitHub calcule certains paliers (`Pair Extraordinaire`, upgrades `Pull Shark`) de façon asynchrone : le délai varie de quelques minutes à **24–72 heures**.

---

## Bonnes pratiques
- Respectez toujours les limites de requêtes de l'API GitHub et évitez les rafales sur des comptes nouvellement créés.
- GitHub actualise les badges de profil de manière asynchrone : l'affichage peut prendre de quelques minutes à 24 heures.

---

<p align="center">
  Si ce guide vous a aidé à débloquer vos badges, laissez une <strong>⭐ Étoile</strong> pour soutenir le projet !
  <br />
  Distribué sous <a href="./LICENSE">Licence MIT</a>.
</p>
