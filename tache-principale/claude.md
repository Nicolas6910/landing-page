# 🎯 TÂCHE PRINCIPALE - Agent frontend-developer

## 🤖 INVOCATION AGENT OBLIGATOIRE
```
INVOKE immédiatement : frontend-developer
```

## 📋 MISSION PRÉCISE
Créer une landing page moderne et performante avec Next.js 14, intégrant des animations Framer Motion déclenchées au scroll, un mode sombre/clair élégant, et des tests visuels automatisés via Playwright MCP. L'objectif est d'atteindre un score Lighthouse parfait (100/100) avec une expérience utilisateur captivante.

## 📊 SPÉCIFICATIONS DÉTAILLÉES
Les spécifications enrichies du projet révèlent une landing page moderne avec des exigences techniques et visuelles élevées.

### Spécifications Techniques
- **Stack principal**: Next.js 14 + TypeScript + Tailwind CSS + Framer Motion
- **Performance cible**: Score Lighthouse 100/100 via SSG (Static Site Generation)
- **Tests automatisés**: Tests visuels avec Playwright MCP sur tous les appareils
- **Animations**: Animations fluides au scroll avec Framer Motion
- **Mode d'affichage**: Support dark/light mode avec transitions élégantes

### Spécifications Métier
- **Type de projet**: Landing page moderne et captivante
- **Objectif principal**: Non spécifié (à clarifier - présentation produit probable)
- **Audience cible**: "✨ Caractéristiques uniques" (réponse incomplète - prévoir flexibilité)
- **Intégrations**: Animations Framer Motion mentionnées spécifiquement

### Spécifications Utilisateur
- **Sections interactives requises**:
  - Hero section dynamique
  - Section témoignages avec animations
  - Cartes pricing avec effets 3D
- **Design**: Mode sombre/clair avec transitions élégantes
- **Performance**: Optimisation maximale pour score Lighthouse parfait
- **Responsive**: Tests visuels garantissant expérience parfaite sur tous appareils

## 🛠️ MCPs À UTILISER EN PRIORITÉ
```yaml
filesystem-local:
  - Création de la structure de fichiers Next.js
  - Gestion des composants et assets
  - Organisation du code TypeScript

memory-local:
  - Sauvegarde des décisions d'architecture
  - Tracking des composants créés
  - Documentation des patterns utilisés

github-local:
  - Commits réguliers des progrès
  - Push vers la branche feature/tache-principale
  - Création de PR quand prêt

playwright (si installé):
  - Configuration des tests visuels
  - Scénarios de test responsive
  - Validation des animations

web-fetch (pour inspiration):
  - Recherche de références design
  - Best practices Next.js 14
  - Exemples d'animations Framer Motion
```

## 🎯 OBJECTIFS SPÉCIFIQUES
1. **Structure Next.js 14 optimale**:
   - Configuration TypeScript stricte
   - Setup Tailwind CSS avec thème dark/light
   - Installation et config Framer Motion
   - Setup Playwright pour tests visuels

2. **Composants à créer**:
   - `Hero.tsx`: Section hero dynamique avec animations
   - `Testimonials.tsx`: Témoignages animés au scroll
   - `PricingCards.tsx`: Cartes pricing avec effets 3D
   - `ThemeToggle.tsx`: Switch dark/light mode élégant
   - `Navigation.tsx`: Navigation responsive avec animations

3. **Optimisations performance**:
   - Images optimisées avec next/image
   - Fonts optimisées avec next/font
   - Code splitting automatique
   - Prefetch intelligent des ressources
   - Minification et compression

4. **Tests Playwright**:
   - Tests visuels multi-devices
   - Validation des animations
   - Tests de performance
   - Tests d'accessibilité

## ⚡ WORKFLOW EXÉCUTION

### Phase 1: Setup initial (30 min)
```bash
# 1. Initialiser le projet Next.js avec TypeScript et Tailwind
npx create-next-app@latest . --typescript --tailwind --app --src-dir --import-alias "@/*"

# 2. Installer les dépendances essentielles
npm install framer-motion @vercel/analytics react-hook-form
npm install -D @playwright/test

# 3. Configurer le thème Tailwind pour dark mode
# Éditer tailwind.config.ts avec darkMode: 'class'
```

### Phase 2: Architecture de base (45 min)
1. Créer la structure de dossiers:
   ```
   src/
   ├── app/
   │   ├── layout.tsx (avec providers theme)
   │   └── page.tsx (landing page principale)
   ├── components/
   │   ├── sections/
   │   │   ├── Hero.tsx
   │   │   ├── Testimonials.tsx
   │   │   └── PricingCards.tsx
   │   ├── ui/
   │   │   ├── ThemeToggle.tsx
   │   │   └── AnimatedButton.tsx
   │   └── layout/
   │       └── Navigation.tsx
   ├── hooks/
   │   └── useScrollAnimation.ts
   └── lib/
       └── animations.ts
   ```

2. Configurer les providers (Theme, Analytics)
3. Setup les animations de base Framer Motion

### Phase 3: Développement des composants (2h)
1. **Hero Section**:
   - Animation d'entrée spectaculaire
   - Texte animé au typing
   - CTA avec hover effects

2. **Testimonials**:
   - Carousel animé
   - Apparition au scroll
   - Transitions fluides

3. **Pricing Cards**:
   - Effet 3D au hover
   - Animation de flip
   - Highlighting du plan recommandé

### Phase 4: Optimisations (1h)
1. Audit Lighthouse et corrections
2. Optimisation des images et assets
3. Lazy loading des sections
4. Préchargement des fonts critiques

### Phase 5: Tests Playwright (1h)
1. Configuration des tests visuels
2. Scénarios de test:
   - Responsive design (mobile, tablet, desktop)
   - Animations au scroll
   - Switch dark/light mode
   - Performance metrics

## 🐙 **PUSH VERS GITHUB PR**
Quand les fichiers sont créés:
1. **INVOQUER github-automation-manager** pour pusher vers la PR
2. **UTILISER** `mcp__github__push_files` ou `mcp__github__create_or_update_file`
3. **BRANCH**: feature/tache-principale
4. **COMMIT MESSAGE**: "✅ Landing page Next.js avec animations et tests Playwright"
5. **METTRE À JOUR** le statut de l'issue avec `mcp__github__update_issue`

## 🚀 SIGNAL DE FIN OBLIGATOIRE
```python
mcp__filesystem-local__write_file("./.task_completed", "TACHE_PRINCIPALE_SUCCESS")
```

## 🛑 **SIGNAL FIN OBLIGATOIRE ET ARRÊT**
**ARRÊTER IMMÉDIATEMENT** après signal - Ne pas continuer, signal de fin envoyé au workflow Python

**COMMENCE IMMÉDIATEMENT avec frontend-developer et les spécifications complètes !**