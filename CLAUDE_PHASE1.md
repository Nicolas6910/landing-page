# CLAUDE - PHASE 1 PROJECT STRUCTURATION

## 🏗️ **INVOCATION OBLIGATOIRE**
```
INVOKE immédiatement : StructureBuilder
```

## 📋 Contexte du Projet
**Nom**: landing-page
**Phase**: STRUCTURATION avec spécifications enrichies

## 🎯 **MISSION PHASE 1 CRITIQUE**

### **TON RÔLE StructureBuilder**
Tu dois lire les spécifications enrichies et créer la structure optimale du projet.

### **WORKFLOW PHASE 1**:

1. **LIRE** le fichier reponses.json avec toutes les spécifications enrichies
2. **ANALYSER** le projet avec contexte complet (PRE-PHASE + réponses utilisateur)
3. **CLASSIFIER** SIMPLE vs DÉVELOPPEMENT avec informations complètes
4. **CRÉER** la structure de dossiers optimale avec MCPs
5. **GÉNÉRER** claude.md spécialisés pour chaque tâche avec spécifications
6. **DISTRIBUER** les spécifications appropriées par tâche
7. **CRÉER** PROJECT_ROADMAP.md avec justification + contexte enrichi

### **RÈGLES CRITIQUES**:
- **UTILISER SPÉCIFICATIONS ENRICHIES**: reponses.json contient TOUT le contexte
- **OPTIMISATION TOKENS**: Solution la plus simple qui répond aux spécifications
- **DISTRIBUTION INTELLIGENTE**: Répartir specs par tâche appropriée
- **MCPs PRIORITAIRES**: filesystem-local, memory-local, github-local
- **AGENTS SPÉCIALISÉS**: Assigner le bon agent selon specs + type tâche

### **STRUCTURE PATTERNS**:

#### **SIMPLE PROJECT** (si spécifications le permettent):
```
projet/
├── CLAUDE.md (cette phase)
├── CLAUDE_PHASE1.md (cette phase)
├── tache-principale/
│   └── claude.md (agent spécialisé + specs)
├── PROJECT_ROADMAP.md
├── questions.json (PRE-PHASE)
└── reponses.json (spécifications enrichies)
```

#### **DEVELOPMENT PROJECT** (si spécifications le justifient):
```
projet/
├── CLAUDE.md (PRE-PHASE)
├── CLAUDE_PHASE1.md (cette phase)
├── tache-backend/ (si API/serveur nécessaire selon specs)
├── tache-frontend/ (si interface nécessaire selon specs)
├── tache-devops/ (si déploiement nécessaire selon specs)
├── tache-[autre]/ (si justifié par spécifications)
├── PROJECT_ROADMAP.md
├── questions.json (PRE-PHASE)
└── reponses.json (spécifications enrichies)
```

### **TEMPLATE claude.md POUR CHAQUE TÂCHE**:
```markdown
# 🎯 TÂCHE [NAME] - Agent [SPECIALIZED_AGENT]

## 🤖 INVOCATION AGENT OBLIGATOIRE
```
INVOKE immédiatement : [agent-spécialisé]
```

## 📋 MISSION PRÉCISE
[Description basée sur spécifications enrichies reponses.json]

## 📊 SPÉCIFICATIONS DÉTAILLÉES
[Intégrer les réponses pertinentes du reponses.json pour cette tâche]

### Spécifications Techniques
[Réponses techniques du PRE-PHASE]

### Spécifications Métier
[Réponses business du PRE-PHASE]

### Spécifications Utilisateur
[Réponses UX du PRE-PHASE]

## 🛠️ MCPs À UTILISER EN PRIORITÉ
[MCPs spécifiques pour cette tâche]

## 🎯 OBJECTIFS SPÉCIFIQUES
[Livrables basés sur spécifications enrichies]

## ⚡ WORKFLOW EXÉCUTION
[Étapes avec contexte des spécifications]

## 🐙 **PUSH VERS GITHUB PR**
Quand les fichiers sont créés:
1. **INVOQUER github-automation-manager** pour pusher vers la PR
2. **UTILISER** `mcp__github__push_files` ou `mcp__github__create_or_update_file`
3. **BRANCH**: feature/[TASK_NAME]
4. **COMMIT MESSAGE**: "✅ [TASK_NAME] - Livrables avec spécifications enrichies"
5. **METTRE À JOUR** le statut de l'issue avec `mcp__github__update_issue`

## 🚀 SIGNAL DE FIN OBLIGATOIRE
```python
mcp__filesystem-local__write_file("./.task_completed", "[TASK_NAME]_SUCCESS")
```

## 🛑 **SIGNAL FIN OBLIGATOIRE ET ARRÊT**
**ARRÊTER IMMÉDIATEMENT** après signal - Ne pas continuer, signal de fin envoyé au workflow Python

**COMMENCE IMMÉDIATEMENT avec [agent-spécialisé] et spécifications complètes !**
```

## 🚀 **EXÉCUTION IMMÉDIATE - 2 PHASES CRITIQUES**

### **PHASE A - STRUCTURATION:**
1. **INVOQUER StructureBuilder** immédiatement
2. **LIRE reponses.json** pour récupérer toutes les spécifications
3. **ANALYSER** avec contexte complet (nom + description + réponses)
4. **CRÉER** structure optimale selon spécifications enrichies
5. **GÉNÉRER** claude.md spécialisés avec specs distribuées
6. **SIGNAL** fin avec: `mcp__filesystem-local__write_file("./.structure_completed", "SUCCESS")`

### **PHASE B - GITHUB (OBLIGATOIRE APRÈS STRUCTURE):**
7. **APRÈS LE SIGNAL DE FIN**, tu DOIS **INVOQUER github-automation-manager** pour créer TOUTE l'infrastructure GitHub:

   ```
   INVOKE OBLIGATOIREMENT: github-automation-manager
   ```

   **MISSION POUR github-automation-manager:**

   a) **D'abord, récupérer le username GitHub:**
   - Utiliser `gh api user` ou les MCPs appropriés pour obtenir le username
   - Ce username sera utilisé comme "owner" pour toutes les opérations

   b) **Initialiser Git et créer le repository GitHub:**
   - D'abord initialiser Git localement:
     ```bash
     git init
     git add .
     git commit -m "🎯 Initial structure with PRE-PHASE + PHASE 1"
     ```

   - Ensuite créer le repo GitHub:
   ```python
   mcp__github__create_repository(
       name="landing-page",
       private=True,
       autoInit=False,  # False car on a déjà un repo local
       description="Projet créé avec workflow enrichi PRE-PHASE + PHASE 1"
   )
   ```

   - Puis pusher le code:
     ```bash
     git remote add origin https://github.com/[USERNAME_RÉCUPÉRÉ]/landing-page.git
     git push -u origin main
     ```

   c) **Gestion des labels avant création des tâches:**
   - **Lister les labels existants du repository:**
     ```bash
     gh label list --repo landing-page
     ```
   - **Créer les labels manquants nécessaires:**
     ```bash
     # Labels standards pour le workflow
     gh label create "enhancement" --description "New feature or enhancement" --color "a2eeef" || true
     gh label create "enriched-specs" --description "Task with enriched specifications" --color "d876e3" || true
     gh label create "needs-verification" --description "Needs verification phase" --color "f9d0c4" || true
     gh label create "phase-1" --description "Phase 1: Structure" --color "0e8a16" || true
     gh label create "phase-2" --description "Phase 2: GitHub" --color "1d76db" || true
     gh label create "phase-3" --description "Phase 3: Development" --color "5319e7" || true
     gh label create "phase-5" --description "Phase 5: Verification" --color "b60205" || true
     gh label create "agent-assigned" --description "Agent assigned to task" --color "fbca04" || true
     gh label create "in-progress" --description "Work in progress" --color "ededed" || true
     gh label create "ready-for-review" --description "Ready for review" --color "0052cc" || true
     ```

   d) **Pour CHAQUE tâche trouvée dans les dossiers tache-*:**
   - Scanner le dossier actuel pour trouver tous les dossiers commençant par "tache-"
   - Pour chaque tâche, lire son README.md ou claude.md pour obtenir la description

   - **Créer une issue avec assignee:**
   ```python
   mcp__github__create_issue(
       owner="[USERNAME_RÉCUPÉRÉ]",
       repo="landing-page",
       title="Tâche: [NOM_TACHE]",
       body="[Description tirée du README.md de la tâche]",
       labels=["enhancement", "enriched-specs", "needs-verification"],
       assignees=["Niko6910"]  # TOUJOURS assigner à Niko6910
   )
   ```

   - **Créer une branche feature:**
   ```python
   mcp__github__create_branch(
       owner="[USERNAME_RÉCUPÉRÉ]",
       repo="landing-page",
       branch="feature/[TACHE_NAME]",
       from_branch="main"
   )
   ```

   - **IMPORTANT: Créer un commit sur la branche pour avoir une différence:**
     ```bash
     git checkout feature/[TACHE_NAME]
     # Créer un fichier .gitkeep dans le dossier de la tâche
     echo "# Placeholder pour [TACHE_NAME]" > [TACHE_NAME]/.gitkeep
     git add [TACHE_NAME]/.gitkeep
     git commit -m "🚧 Initial setup pour [TACHE_NAME]"
     git push -u origin feature/[TACHE_NAME]
     git checkout main
     ```

   - **Créer une Pull Request draft (APRÈS le commit):**
   ```python
   mcp__github__create_pull_request(
       owner="[USERNAME_RÉCUPÉRÉ]",
       repo="landing-page",
       title="🚧 [TACHE_NAME]",
       body="PR pour la tâche avec specs enrichies. Closes #[ISSUE_NUMBER]",
       head="feature/[TACHE_NAME]",
       base="main",
       draft=True
   )
   ```

   e) **NOTES IMPORTANTES pour github-automation-manager:**
   - Scanner TOUS les dossiers tache-* créés
   - TOUJOURS lister les labels existants avant d'en créer de nouveaux
   - Créer uniquement les labels manquants
   - TOUJOURS assigner les issues à "Niko6910"
   - Créer une issue + branch + PR pour CHAQUE tâche
   - Lier les PRs aux issues avec "Closes #X"
   - **PROJET BOARD**: Utiliser `gh project` CLI car pas de MCP disponible
   - **ORDRE**: D'abord labels, puis issues, puis branches, puis PRs
   - **SIGNAL FINAL OBLIGATOIRE**: Après TOUT le travail GitHub:
     ```python
     mcp__filesystem-local__write_file("./.github_completed", "SUCCESS")
     ```

## 🛑 **SIGNAL FIN OBLIGATOIRE ET ARRÊT**
8. **SIGNAL GITHUB**: Créer le fichier signal après tout le travail GitHub
9. **ARRÊTER IMMÉDIATEMENT** après le signal final
10. **FERMER SESSION** automatiquement

**COMMENCE MAINTENANT - Structure landing-page avec spécifications complètes ET création GitHub !**

---
*PHASE 1 - Structuration intelligente avec spécifications enrichies*
