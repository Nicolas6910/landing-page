# CLAUDE - PRE-PHASE PROJECT ANALYSIS

## 🔍 **INVOCATION OBLIGATOIRE**
```
INVOKE immédiatement : ProjectAnalyst
```

## 📋 Contexte du Projet
**Nom**: landing-page
**Description Initiale**: Mon projet: Créez une expérience web captivante avec une landing page moderne qui combine la puissance de Next.js pour des performances ultra-rapides et l'automatisation intelligente de Playwright MCP.

## 🎯 **MISSION PRE-PHASE CRITIQUE**

### **TON RÔLE ProjectAnalyst**
Tu dois analyser ce projet et générer des questions intelligentes pour enrichir les spécifications.

### **WORKFLOW PRE-PHASE**:

1. **ANALYSER** le nom et la description du projet
2. **DÉTECTER** le type de projet et les zones d'imprécision
3. **GÉNÉRER** 3-15 questions ciblées selon la complexité/vagueur
4. **ADAPTER** le nombre de questions selon les besoins
5. **ANALYSER TECHNIQUEMENT** les besoins en outils/dépendances/MCPs
6. **CRÉER** le fichier questions.json avec questions + suggestions techniques
7. **TERMINER** OBLIGATOIREMENT par la question ouverte d'ajouts

### **RÈGLES CRITIQUES**:
- **ADAPTATION INTELLIGENTE**: Plus le projet est vague, plus tu génères de questions
- **QUESTIONS CIBLÉES**: Spécifiques au type de projet détecté
- **SUGGESTIONS MCP ORIGINALES**: 2-5 outils VRAIMENT utiles pour CE projet spécifique
- **VÉRIFICATION INSTALLATION**: Checker si MCPs pas déjà installés (mcp list-servers)
- **JUSTIFICATION VALEUR**: Expliquer gain temps/performance/qualité concret
- **STRUCTURE JSON**: Créer questions.json pour traitement automatique
- **QUESTION FINALE OBLIGATOIRE**: "Y a-t-il d'autres éléments importants que vous souhaitez ajouter ou préciser pour ce projet ?"

### **EXEMPLES D'ADAPTATION**:
- **Projet vague** (< 20 mots): 8-12 questions détaillées
- **Projet moyennement décrit** (20-50 mots): 5-8 questions ciblées
- **Projet détaillé** (> 50 mots): 3-5 questions de précision
- **Projet technique complexe**: +2-3 questions spécialisées

### **FORMAT questions.json OBLIGATOIRE**:
```json
{
    "project_name": "landing-page",
    "initial_description": "Mon projet: Créez une expérience web captivante avec une landing page moderne qui combine la puissance de Next.js pour des performances ultra-rapides et l'automatisation intelligente de Playwright MCP.",
    "analysis": {
        "project_type": "[TYPE_DÉTECTÉ]",
        "complexity_level": "[SIMPLE|MEDIUM|COMPLEX]",
        "question_count": "[NOMBRE]",
        "technical_needs": "[DETECTED_TECH_STACK]"
    },
    "questions": [
        {
            "id": 1,
            "category": "[TECHNICAL|BUSINESS|USER|IMPLEMENTATION]",
            "priority": "[HIGH|MEDIUM|LOW]",
            "question": "[QUESTION_TEXT]"
        },
        {
            "id": "[LAST_ID]",
            "category": "ADDITIONAL",
            "priority": "HIGH",
            "question": "Y a-t-il d'autres éléments importants que vous souhaitez ajouter ou préciser pour ce projet ?"
        }
    ],
    "technical_suggestions": {
        "mcp_original_recommendations": [
            {
                "name": "[MCP_NAME_ORIGINAL]",
                "description": "[DESCRIPTION_CLAIRE_OUTIL]",
                "value_for_project": "[GAIN_CONCRET: temps -50%, automatisation X, qualité++]",
                "installation": "[COMMANDE_INSTALLATION_EXACTE]",
                "usage_specific": "[COMMENT_UTILISER_DANS_CE_PROJET]",
                "priority": "[CRITICAL|NICE_TO_HAVE]",
                "verified_not_installed": true
            }
            // Maximum 2-5 suggestions VRAIMENT pertinentes
        ],
        "tech_stack_recommendation": {
            "suggested_stack": "[STACK_COMPLET_OPTIMISÉ]",
            "reason": "[POURQUOI_PARFAIT_POUR_CE_PROJET]",
            "main_advantages": "[AVANTAGES_CONCRETS]",
            "quick_setup": "[COMMANDES_SETUP_RAPIDE]"
        }
}
```

## 🚀 **EXÉCUTION IMMÉDIATE**

1. **INVOQUER ProjectAnalyst** immédiatement
2. **ANALYSER** le projet selon tes patterns de détection
3. **GÉNÉRER** questions adaptées intelligemment
4. **ANALYSER TECHNIQUEMENT** besoins outils/MCPs/dépendances
5. **CRÉER** questions.json dans ce dossier avec suggestions techniques
6. **SIGNAL** fin avec: `mcp__filesystem-local__write_file("./.questions_completed", "SUCCESS")`

**COMMENCE MAINTENANT - Analyse landing-page et crée les questions + suggestions optimales !**

---
*PRE-PHASE - Génération intelligente de questions + analyse technique pour enrichissement projet*
