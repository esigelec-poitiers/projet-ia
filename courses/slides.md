---
theme: default
class: text-center
highlighter: shiki
lineNumbers: false
drawings:
  persist: false
transition: slide-left
title: 'Bloc 1: Fondations & Histoire'
mdc: true
---

# Projet IA & Big Data

ESIGELEC Poitiers - Dominante IA & Big Data

---
layout: two-cols-header
---

# Qui suis-je?

- 🧑🏾 **Nom**: Brice FOTZO
- 🌍 **Origine**: Bafoussam, Cameroun
- 🎓 **Formation**: Ingénieur Généraliste(BDTN) - ESIGELEC Rouen

> Parcours Data & AI
- Analytics Engineer - **Apprenti** @ Renault
- Data Engineer - CDI @ Starclay
- Tech Lead Data - CDI @ HephIA
- Tech Lead Data - CDI @ Servier
- Intervenant - CDD @ ESIGELEC Rouen/Poitiers

> Engagements Communautaires
- Data Engineer - **Volunteer** @ Validalab(DFG)
- MUG Leader Paris - **Volunteer** @ MongoDB
- Créateur de contenu @ LinkedIn, Medium
- Créateur de Serial Techos

---
layout: default
---

# Et vous?
## Faisons connaissance

<div class="text-xl mt-8">

- Votre nom et parcours?
- Vos expériences en IA/Data?
- Vos attentes pour ce cours?
- Projets personnels ou professionnels?

</div>

---
layout: two-cols-header
---

# Objectifs d'apprentissage

::left::

**Compétences techniques**
- Comprendre l'exécution des modèles LLM
- Construire et gérer un stockage vectoriel
- Maîtriser le RAG (Retrieval Augmented Generation)
- Optimiser l'inférence (Flash Attention, KV cache)
- Déployer les LLM (local, serveur, edge)
- Sécuriser les applications LLM

::right::

**Technologies et outils**
- API LLM et modèles open-source
- Bases de données vectorielles
- Modèles d'embedding
- Techniques de prompt engineering
- Frameworks de déploiement
- Mesures de sécurité et surveillance

---
layout: two-cols-header
---

# Structure du cours

::left::

**Volume horaire**
- 6h de cours magistraux
- 44h de travaux pratiques
- **Total**: 50h

**Évaluation**
- 1 Contrôle Continu (50%)
- 1 Contrôle Final (50%)

::right::

**Ressources**
- Support de cours - Slides
- Exercices pratiques - GitHub
- Environnement de développement
- Documentation en ligne
- Exemples de code

---
layout: center
---

# Plan (1h)

<div class="text-2xl mt-12 space-y-6">

**1.1** Un peu d'histoire

**1.2** Les Modèles 

**1.3** Évaluation 

</div>

---
layout: section
---

# 1.1
# Un peu d'histoire

---
layout: center
---

# Évolution de l'IA

<div class="text-3xl mt-16 space-y-8">

**1950s-1990s** → Systèmes experts

**2000s** → Machine Learning statistique

**2010s** → Deep Learning

**2017+** → `Era Transformer` ⚡ 

**2020s** → Generative AI

</div>

<style>
.space-y-8 > * + * {
  margin-top: 2rem !important;
}
</style>

---
layout: center
---

# 🔥 2017 : Moment Clé

<div class="mt-20">
<h2 class="text-5xl font-bold mb-8">"Attention Is All You Need"</h2>

<div class="text-2xl space-y-4">

**8 auteurs** · Google Brain/Research

**173,000+** citations (2025)

</div>
</div>

<div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 text-xl text-gray-500">
📝 Notez : Architecture Transformer
</div>


---
layout: center
---

# 3 Enablers Techniques

<div class="grid grid-cols-3 gap-16 mt-16 text-center">

<div>
<div class="text-6xl mb-4">📊</div>
<div class="text-2xl font-bold">Big Data</div>
<div class="text-lg mt-4 text-gray-600">Pétaoctets<br/>Common Crawl</div>
</div>

<div>
<div class="text-6xl mb-4">⚡</div>
<div class="text-2xl font-bold">Calcul<br/>Distribué</div>
<div class="text-lg mt-4 text-gray-600">Spark → Ray<br/>Parallelism</div>
</div>

<div>
<div class="text-6xl mb-4">🖥️</div>
<div class="text-2xl font-bold">Compute<br/>Power</div>
<div class="text-lg mt-4 text-gray-600">GPU → TPU<br/>H100 clusters</div>
</div>

</div>

---
layout: center
---

# Évolution des Cas d'Usage

<div class="flex justify-center items-center gap-12 mt-20 text-3xl">

**Prédiction**

<div class="text-5xl">→</div>

**Génération**

<div class="text-5xl">→</div>

**Raisonnement**

</div>

<div class="flex justify-center gap-12 mt-12 text-lg text-gray-600">

<div>Classification<br/>Scoring</div>

<div>GPT, DALL-E<br/>Creative AI</div>

<div>o3, DeepSeek R1<br/>Agents</div>

</div>

<div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 text-xl text-gray-500">
📝 Notez : les 3 eras
</div>

---
layout: section
---

# 1.2
# Les Modèles

---
layout: two-cols
---

# Innovation Transformer

<div class="text-xl mt-8 space-y-6">

✨ **Self-Attention**

⚡ **Parallélisation** massive

🚫 **Supprime** RNN/LSTM

📈 Performance supérieure

</div>

::right::

<div class="mt-8 ml-8">

### Résultat

<div class="text-6xl font-bold text-blue-600 mt-12">
28.4
</div>

<div class="text-xl mt-4">
BLEU score
<div class="text-sm  text-gray-500">
Bilingual Evaluation Understudy
</div>

English→German
</div>

<div class="text-sm m text-green-500">
+2 points vs état de l'art
</div>

</div>

---
layout: two-cols-header
---

# L'Attention : Quelle Innovation ?

::left::

### ❌ Avant (RNN/LSTM)

<div class="text-lg mt-6 space-y-4">

**Traitement séquentiel**
```
"Le chat" → "mange" → "la" → "souris"
   ↓         ↓        ↓        ↓
  h1  →    h2  →   h3  →    h4
```

**Problèmes:**
- Traite mot par mot 🐌
- Oublie le début de la phrase
- Pas de parallélisation
- "Le chat" → loin de "souris"

</div>


::right::

### ✅ Avec Attention

<div class="text-lg mt-6 space-y-4">

**Traitement parallèle**
```
"Le chat mange la souris"
  ↕️    ↕️    ↕️   ↕️    ↕️
Tous les mots se "voient"
```

**Avantages:**
- Accès direct à tous les mots ⚡
- Comprend les relations longue distance
- Parallélisable sur GPU
- "Le chat" ↔️ "souris" : lien direct

</div>

---
layout: center
---

# Exemple Concret : Traduction

<div class="mt-12 space-y-12">

<div class="text-2xl">
🇫🇷 "Le directeur de la banque qui est grand"
</div>

<div class="text-lg text-gray-600">
Qui est grand ? Le directeur ou la banque ?
</div>

<div class="mt-8 p-6 bg-blue-50 rounded-lg text-gray-600">
<div class="font-bold mb-4">💡 L'Attention résout ce problème :</div>
<div class="text-lg">
Elle calcule un <span class="font-bold text-blue-600">"score d'importance"</span> entre chaque paire de mots
<br/><br/>
→ "grand" regarde tous les mots et décide : <span class="font-bold">"directeur"</span> (score élevé) vs "banque" (score faible)
</div>
</div>

</div>

---
layout: center
---

# 2 Familles Principales

<div class="grid grid-cols-2 gap-20 mt-20 text-center">

<div>
<div class="text-8xl mb-6">🎯</div>
<h2 class="text-4xl font-bold mb-4">SLM</h2>
<div class="text-xl text-gray-600">Small Language<br/>Models</div>
<div class="mt-6 text-lg">1B - 14B params</div>
</div>

<div>
<div class="text-8xl mb-6">🌟</div>
<h2 class="text-4xl font-bold mb-4">LLM</h2>
<div class="text-xl text-gray-600">Large Language<br/>Models</div>
<div class="mt-6 text-lg">70B - 671B params</div>
</div>

</div>

---
layout: two-cols
---

# Small Language Models

<div class="text-xl mt-8 space-y-6">

### Principe

**Distillation**
Teacher → Student

### Exemple : Phi-4

📊 **14B** paramètres

🎓 **Spécialité** : Math

🏆 Surpasse modèles 5x plus gros

</div>

::right::

<div class="mt-8 ml-8">

### Avantages

<div class="text-2xl space-y-6 mt-12">

📱 **Edge / Local**

💰 **Coûts réduits**

⚡ **Latence faible**

🔒 **Privacy**

</div>

</div>

<div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 text-xl text-gray-500">
📝 Notez : Distillation teacher-student
</div>

<!--
La distillation (ou knowledge distillation) vient du Machine Learning classique.
C’est une technique pour transférer le savoir d’un grand modèle (“teacher”) vers un plus petit (“student”).

Teacher = un modèle très puissant, lent, coûteux

Student = un modèle plus petit, plus rapide, qu’on veut rendre presque aussi bon

💡 But : réduire la taille et le coût, sans perdre trop de performance.
-->

---
layout: center
---

# Phi-4 Performance

<div class="mt-16">

| Benchmark | Phi-4 (14B) | Llama 3.3 (70B) |
|-----------|-------------|-----------------|
| GPQA | **75.5%** | - |
| MATH-500 | **94%+** | ~85% |
| MMLU | **88.2%** | 86.3% |

</div>

<div class="text-center mt-12 text-2xl">
💡 5x plus petit, performances comparables
</div>

<!--
🧠 1. MMLU — Massive Multitask Language Understanding

👉 But : tester la culture générale et la compréhension d’un modèle.
57 domaines : math, médecine, droit, informatique, etc.
Niveau : collège → doctorat

2. GPQA — Graduate-Level Google-Proof Q&A

👉 But : évaluer la raisonnement scientifique de haut niveau.
Questions validées par des chercheurs (PhD)
Domaines : physique, biologie, chimie

🔢 3. MATH-500
But : évaluer la résolution d’exercices mathématiques (niveau lycée à université).
500 problèmes, souvent issus d’olympiades ou concours.
Vérifie le raisonnement pas à pas.
-->

---
layout: center
---

# LLM : 2 Catégories

<div class="grid grid-cols-2 gap-16 mt-20 text-center">

<div class="p-8 bg-gradient-to-br from-purple-500 to-pink-500 text-white rounded-xl">
<div class="text-3xl font-bold mb-4">Propriétaires</div>
<div class="text-xl space-y-3 mt-8">
<div>OpenAI GPT-4o, o3</div>
<div>Anthropic Claude 4</div>
<div>Google Gemini 2.5</div>
</div>
</div>

<div class="p-8 bg-gradient-to-br from-blue-500 to-cyan-500 text-white rounded-xl">
<div class="text-3xl font-bold mb-4">Open-Weight</div>
<div class="text-xl space-y-3 mt-8">
<div>Meta Llama 3.3</div>
<div>Mistral Large 2</div>
<div>Qwen 2.5</div>
</div>
</div>

</div>

---
layout: center
---

# OpenAI : 2 Lignes

<div class="grid grid-cols-2 gap-12 mt-16">

<div class="text-center">
<div class="text-5xl mb-6">🎨</div>
<h2 class="text-3xl font-bold mb-6">GPT-4o</h2>
<div class="text-xl space-y-4">
<div>Multimodal</div>
<div>Vision + Audio</div>
<div>232ms latency</div>
</div>
</div>

<div class="text-center">
<div class="text-5xl mb-6">🧠</div>
<h2 class="text-3xl font-bold mb-6">o3 / o4-mini</h2>
<div class="text-xl space-y-4">
<div>Reasoning</div>
<div>Chain-of-Thought</div>
<div>Math + Code</div>
</div>
</div>

</div>

---
layout: center
---

# Claude 4 : 3 Tailles

<div class="space-y-10 mt-12 text-2xl">

**Opus 4** → Meilleur coding au monde
<div class="text-lg text-gray-600">72.5% SWE-bench · 7h autonomie</div>

**Sonnet 4.5** → Meilleur équilibre
<div class="text-lg text-gray-600">30h+ autonomie · $3/$15</div>

**Haiku 4.5** → Ultra rapide
<div class="text-lg text-gray-600">2x+ rapide · 1/3 du coût · $1/$5</div>

</div>

<div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 text-xl text-gray-500">
📝 Notez : Opus/Sonnet/Haiku
</div>

---
layout: center
---

# 🧠 Modèles de Raisonnement

<div class="text-3xl mt-16 space-y-10">

**OpenAI o3**
<div class="text-xl text-gray-600">87.7% GPQA Diamond · PhD-level</div>

**DeepSeek R1**
<div class="text-xl text-gray-600">Open-source · 15-50% du coût · 671B params</div>

**Claude 4** (hybrid)
<div class="text-xl text-gray-600">Extended thinking + Tools</div>

</div>

---
layout: center
---

# DeepSeek R1 : Innovation

<div class="mt-16 space-y-12 text-2xl">

🔬 **Pure RL** (sans SFT initial)

🎯 **671B params** → 37B actifs (MoE)

💰 **Cost:** 15-50% d'OpenAI

📜 **Open-source** (MIT License)

</div>

<div class="text-center mt-16 text-3xl font-bold">
79.8% AIME 2024
</div>


<div class="absolute left-1/2 transform -translate-x-1/2 text-xl text-gray-500">
📝 Notez : RL pur + MoE
</div>

<!--
🔬 1. “Pure RL (sans SFT initial)”

👉 RL = Reinforcement Learning (apprentissage par renforcement).
👉 SFT = Supervised Fine-Tuning (apprentissage supervisé).

La plupart des LLM (ex : GPT-4, Claude 4) suivent ce pipeline :

Pré-entraînement sur du texte brut.

SFT → on les affine avec des exemples humains (“bonne réponse / mauvaise réponse”).

RLHF (Reinforcement Learning from Human Feedback) → on les aligne avec ce que les humains préfèrent.

💡 DeepSeek R1 saute l’étape SFT :
il apprend directement par renforcement, en explorant et en recevant une récompense selon la qualité de sa réponse.
→ C’est ce qu’on appelle un modèle “pure RL”.

Avantage : il découvre des stratégies originales.
Risque : apprentissage plus instable, car pas guidé au départ.

🎯 2. “671B params → 37B actifs (MoE)”

671B paramètres = taille totale du modèle.

Mais seulement 37 milliards sont activés à chaque requête.
→ C’est ce qu’on appelle un Mixture of Experts (MoE).

💡 MoE = au lieu d’utiliser tout le cerveau du modèle à chaque fois,
il active seulement les “experts” nécessaires pour une tâche donnée.
C’est comme un grand groupe d’experts, où seuls ceux concernés parlent.

👉 Résultat : énorme modèle, mais coût d’inférence réduit.
-->

---
layout: center
---

# Embeddings : Représentation Vectorielle

<div class="mt-16 text-center">

<div class="text-5xl mb-8">📊</div>

<div class="text-3xl mb-12">
Texte → Vecteur dense
</div>

<div class="text-2xl space-y-6">

**256 à 3072** dimensions

**Cosine similarity** pour comparer

**Usage:** RAG, Search, Clustering

</div>

</div>

---
layout: center
---

# Top Embedding Models (2025)

<div class="mt-12  text-2xl">

🏆 **Voyage AI voyage-3-large**
<div class="text-lg text-gray-600">#1 MTEB · 32K context · +9.74% vs OpenAI</div>

**OpenAI text-embedding-3**
<div class="text-lg text-gray-600">3072 dims · 8K context · Standard industrie</div>

**Cohere embed-v3**
<div class="text-lg text-gray-600">Multilingual · 100+ langues</div>

**Mistral-embed**
<div class="text-lg text-gray-600">77.8% accuracy · Cost-effective</div>

</div>

<div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 text-xl text-gray-500">
📝 Notez : MTEB leaderboard
</div>

---
layout: section
---

# 1.3
# Évaluation

---
layout: center
---

# 3 Types de Métriques

<div class="grid grid-cols-3 gap-12 mt-16 text-center text-xl">

<div>
<div class="text-5xl mb-6">📏</div>
<div class="font-bold text-2xl mb-4">Classiques</div>
<div class="space-y-3">
<div>ROUGE</div>
<div>BLEU</div>
<div>Perplexité</div>
</div>
</div>

<div>
<div class="text-5xl mb-6">🤖</div>
<div class="font-bold text-2xl mb-4">LLM-Judge</div>
<div class="space-y-3">
<div>Auto-évaluation</div>
<div>Grilles</div>
<div>Scalable</div>
</div>
</div>

<div>
<div class="text-5xl mb-6">🎯</div>
<div class="font-bold text-2xl mb-4">Benchmarks</div>
<div class="space-y-3">
<div>MMLU</div>
<div>GPQA</div>
<div>HumanEval</div>
</div>
</div>

</div>

<!--
📏 Classiques

ROUGE : overlap n-grams → résumés

BLEU : précision lexicale → traduction

Perplexité : prédictibilité du texte
→ ⚠️ Évalue la forme, pas le sens

🤖 LLM-as-a-Judge

Un LLM note un autre LLM

Critères : exactitude, clarté, utilité

✅ Scalable · ⚠️ Biais (position, longueur, auto-faveur)

🎯 Benchmarks

MMLU → culture & logique

GPQA → raisonnement scientifique

HumanEval → code / logique
→ ⚠️ Saturation (>90% top modèles)

💡 Évolution : syntaxe → sens → raisonnement
-->

---
layout: two-cols
---

# Métriques Classiques

<div class="text-xl mt-8 space-y-8">

### ROUGE
N-gram overlap

**Usage:** Summarization

### BLEU
Precision-based

**Usage:** Traduction

### Perplexité
Prédictibilité

</div>

::right::

<div class="mt-8 ml-8">

### Limite

<div class="text-2xl mt-16 space-y-8">

⚠️ **Syntaxique**
<div class="text-lg text-gray-600">Pas sémantique</div>

⚠️ **Ordre**
<div class="text-lg text-gray-600">Sensible position</div>

⚠️ **Sens**
<div class="text-lg text-gray-600">Ne capture pas</div>

</div>

</div>

---
layout: center
---

# LLM-as-a-Judge

<div class="mt-12">

```python {all|2|4-8|10|all}
# Utiliser un LLM pour juger un autre LLM
prompt = f"""
Évalue cette réponse sur 5 critères:
1. Exactitude
2. Pertinence  
3. Clarté
4. Complétude
5. Utilité

Score 1-10 pour chaque.

Question: {question}
Réponse: {output}
"""

scores = judge_llm(prompt)
```

</div>

<div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 text-xl text-gray-500">
📝 Notez : LLM-as-a-Judge
</div>

---
layout: center
---

# Limites LLM-Judge

<div class="mt-16 text-2xl space-y-10">

⚠️ **Position bias**
<div class="text-lg text-gray-600">Préfère certaines positions</div>

⚠️ **Self-enhancement**
<div class="text-lg text-gray-600">Favorise son propre output</div>

⚠️ **Verbosity bias**
<div class="text-lg text-gray-600">Préfère réponses longues</div>

</div>

<div class="text-center mt-12 text-xl">
💡 Solution : Multiple judges + Calibration humaine
</div>

---
layout: center
---

# MMLU

<div class="text-center mt-12">

<div class="text-2xl mb-8">
Massive Multitask Language Understanding
</div>

<div class="grid grid-cols-3 gap-12 text-xl">

<div>
<div class="text-5xl font-bold text-blue-600">10,000</div>
<div class="mt-2">questions</div>
</div>

<div>
<div class="text-5xl font-bold text-blue-600">57</div>
<div class="mt-2">sujets</div>
</div>

<div>
<div class="text-5xl font-bold text-blue-600">4</div>
<div class="mt-2">niveaux</div>
</div>

</div>

<div class="mt-16 text-lg text-gray-600">
Middle school → PhD
</div>

</div>

<div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 text-xl text-red-500">
⚠️ Saturé en 2025 (>90%)
</div>

---
layout: center
---

# GPQA Diamond

<div class="text-center mt-12 space-y-12">

<div class="text-3xl">
Graduate-Level Google-Proof Q&A
</div>

<div class="text-2xl space-y-6">

📚 **PhD-level** en sciences

🔬 Biology · Physics · Chemistry

✅ **Expert-validated**

🚫 Non publiquement disponible

</div>

<div class="mt-12 text-xl">
Top score : <span class="text-5xl font-bold text-blue-600">87.7%</span> (o3)
</div>

</div>

---
layout: center
---

# HumanEval

<div class="text-center mt-12 space-y-10">

<div class="text-3xl">
Évaluation du Code
</div>

<div class="text-2xl space-y-6">

**164** problèmes de programmation

Function + Docstring + Tests

Mesure **functional correctness**

</div>

<div class="mt-12">
<div class="text-xl mb-4">État 2025</div>
<div class="text-5xl font-bold text-blue-600">95%+</div>
<div class="text-lg text-gray-600 mt-2">pour top modèles</div>
</div>

</div>

<div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 text-xl text-red-500">
⚠️ Partiellement saturé
</div>

---
layout: center
---

# ⚠️ La Crise des Benchmarks

<div class="mt-16 text-2xl space-y-10">

**Problème : Saturation**
<div class="text-lg text-gray-600">MMLU >90% · HumanEval >95% · GSM8K résolu</div>

**Conséquence**
<div class="text-lg text-gray-600">Perte de pouvoir discriminant</div>

**Data contamination**
<div class="text-lg text-gray-600">Modèles entraînés sur benchmarks</div>

</div>

<div class="text-center mt-12 text-xl">
💡 Solution : Nouveaux benchmarks dynamiques
</div>

---
layout: center
---

# 🎓 Points Clés du Bloc 1

<div class="grid grid-cols-2 gap-12 mt-12 text-xl">

<div class="space-y-8">

✨ **Transformer (2017)**
<div class="text-base text-gray-600">Révolution architecture</div>

🚀 **3 Enablers**
<div class="text-base text-gray-600">Data · Compute · Distribution</div>

📈 **3 Eras**
<div class="text-base text-gray-600">Prédiction → Génération → Raisonnement</div>

</div>

<div class="space-y-8">

🎯 **SLM vs LLM**
<div class="text-base text-gray-600">Edge vs Capacités max</div>

🧠 **Reasoning Models**
<div class="text-base text-gray-600">o3 · DeepSeek R1 · Claude 4</div>

📊 **Évaluation**
<div class="text-base text-gray-600">Métriques · Benchmarks · Crise</div>

</div>

</div>

---
layout: center
class: text-center
---

# ⏸️ Pause
## 15 minutes

---
layout: end
class: text-center
---

# Questions ?

<div class="mt-12 text-xl">

**Prochaine session :**

RAG, CAG, Chain-of-Thought

</div>

<style>
h1 {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
</style>

---
layout: section
---

# Paradigmes d'utilisation

---
layout: center
---

<div class="text-2xl mt-12 space-y-6">

**2.1** RAG – Retrieval-Augmented Generation 

**2.2** CAG – Cache-Augmented Generation ⭐  

**2.3** Chain-of-Thought & Reasoning 

</div>

<div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 text-xl text-gray-500">
Objectif : mieux exploiter les LLM en contexte réel
</div>

---
layout: section
---

# 2.1
# Retrieval-Augmented Generation (RAG)

---
layout: center
---

# Pourquoi le RAG ? 🤔

<div class="mt-16 text-2xl space-y-8">

❌ Les LLM **oublient** les données récentes  

❌ Le contexte est limité (window de contexte)  

❌ Les données privées ne sont **pas** dans le modèle

</div>

<div class="mt-12 text-2xl">
✅ <span class="font-bold">RAG = LLM + Base de connaissances</span>  

<span class="text-lg text-gray-600">On "branche" le modèle sur vos docs, BDD, APIs…</span>
</div>

<div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 text-xl text-gray-500">
Idée clé : séparer "mémoire longue" (docs) et "raisonnement" (LLM)
</div>

---
layout: center
---

# Vue d’Ensemble

<div class="mt-16 grid grid-cols-3 gap-12 text-center text-xl">

<div>
<div class="text-5xl mb-4">🔎</div>
<div class="font-bold mb-2">1. Retrieve</div>
<div class="text-gray-600">On cherche les passages pertinents</div>
</div>

<div>
<div class="text-5xl mb-4">📎</div>
<div class="font-bold mb-2">2. Augment</div>
<div class="text-gray-600">On ajoute ces passages au prompt</div>
</div>

<div>
<div class="text-5xl mb-4">🧠</div>
<div class="font-bold mb-2">3. Generate</div>
<div class="text-gray-600">Le LLM répond en s’appuyant dessus</div>
</div>

</div>

<div class="mt-16 text-xl text-gray-600 text-center">
💡 Le modèle ne “sait” pas tout → il s’appuie sur un contexte injecté dynamiquement
</div>

---
layout: default
---

# Pipeline RAG Complet

<div class="text-xl mt-8 space-y-6">
```mermaid
flowchart LR
  subgraph Indexation["🧱 Data Indexing Pipeline"]
    A[Sources: DB, PDFs, APIs] --> B[Préparation & Chunking]
    B --> C[Embeddings]
    C --> D[(Vector Store<br/>MongoDB Atlas / pgvector)]
  end

  subgraph Requête["⚙️ Retrieval & Generation Pipeline"]
    Q[User Query] --> QE[Embedding de la requête]
    QE --> R{Recherche vectorielle<br/>dans Vector Store}
    R -->|Top-K documents| G[LLM + Context]
    G --> O[Réponse vérifiée]
  end

  D -.-> R
  style Indexation fill:#0e3b4e,stroke:#00ff99,stroke-width:1px,color:#fff
  style Requête fill:#102f41,stroke:#00ff99,stroke-width:1px,color:#fff

```

</div>

---
layout: center
---

# Étape 1 : Chunking 🧩

<div class="mt-16 text-2xl space-y-10">

**Pourquoi ?**  
<div class="text-lg text-gray-600">
Les docs sont trop gros → on les découpe en "morceaux" exploitables.
</div>

</div>

<div class="grid grid-cols-3 gap-10 mt-12 text-center text-xl">

<div>
<div class="font-bold mb-2">Chunking naïf</div>
<div class="text-gray-600">Taille fixe (ex : 512 tokens)</div>
</div>

<div>
<div class="font-bold mb-2">Recursive</div>
<div class="text-gray-600">On découpe par titre, sous-titre, paragraphe…</div>
</div>

<div>
<div class="font-bold mb-2">Semantic / Agentic</div>
<div class="text-gray-600">On regroupe par idée, avec un LLM</div>
</div>

</div>

<div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 text-xl text-gray-500">
Trade-off : morceaux trop petits = perte de contexte · trop gros = bruit
</div>


---
layout: center
---

# 🧩 Chunking : Attention à l’Overlap

<div class="text-2xl mt-12 space-y-8">

Découper un document = facile.  
Préserver le sens entre les morceaux = **plus subtil** ⚠️

</div>


---
layout: default
---

## Prenons le texte:

```
Les bases de données vectorielles comme MongoDB Atlas Vector Search et pgvector
permettent de stocker des embeddings pour le RAG.
Elles s’intègrent directement dans des environnements de production,
avec réplication, haute disponibilité et monitoring.
```

### Sans Overlap

```text
Chunk 1 → "Les bases vectorielles comme MongoDB Atlas Vector Search et pgvector permettent de stocker des embeddings."
Chunk 2 → "Elles s’intègrent dans des environnements de production avec haute disponibilité."
````

<div class="mt-3 mb-5 text-xl text-gray-600">
❌ Le modèle perd le lien entre *Elles* et *MongoDB Atlas / pgvector*.  
</div>



### Avec Overlap (20 %)

```text
Chunk 1 → "...embeddings pour le RAG. Elles s’intègrent directement..."
Chunk 2 → "Elles s’intègrent directement... haute disponibilité."
```

<div class="mt-3 mb-5 text-xl text-gray-600">
✅ Contexte préservé entre les deux segments.  
</div>

---

# ⚖️ Choisir le bon Overlap

| Chunk size    | Overlap | Exemple d’usage               |
| ------------- | ------- | ----------------------------- |
| 200 tokens    | 10–15 % | Docs techniques courts        |
| 500 tokens    | 20–25 % | Articles, rapports            |
| 1 000+ tokens | >25 %   | Très narratif, peu recommandé |

<div class="mt-8 text-xl text-gray-600">
💡 Attention

Trop d’overlap = redondance et coût.  

Trop peu = perte de cohérence.
</div>

---

# 💬 En résumé

<div class="text-2xl mt-12 space-y-6">

**Overlap ≠ duplication**
→ c’est un *pont sémantique* entre deux chunks 🧠

**Règle d’or :**
Chunk 200–500 tokens avec ~20 % d’overlap
pour un équilibre entre **cohérence**, **coût**, et **pertinence**.

</div>

---
layout: two-cols
---

# Étape 2 : Embeddings 📊

<div class="text-xl mt-8 space-y-6">

- Chaque chunk → **vecteur** (embedding)  
- Encodé dans un espace de dimension 256–3072  
- Chunks similaires → vecteurs proches

</div>

<div class="mt-8 text-xl space-y-4">

**Utilisation :**

- Recherche de similarité  
- Clustering / recommandation  
- Index pour la vector DB

</div>

::right::

<div class="mt-10 ml-8 text-xl space-y-8">

Fonctions typiques :

- `embed(text)` → `[0.12, -0.03, ...]`  
- `cosine_similarity(vec_q, vec_chunk)`  

<div class="text-lg text-gray-600">
Plus la similarité est haute, plus le chunk est pertinent pour la question.
</div>

</div>

---
layout: center
---

# Étape 3 : Stockage Vectoriel 🗄️

<div class="mt-14 grid grid-cols-4 gap-8 text-center text-xl">

<div>
<div class="font-bold mb-2">MongoDB</div>
<div class="text-gray-600 text-base">Cloud, scalable</div>
</div>

<div>
<div class="font-bold mb-2">Weaviate</div>
<div class="text-gray-600 text-base">Graph + Vector</div>
</div>

<div>
<div class="font-bold mb-2">ChromaDB</div>
<div class="text-gray-600 text-base">Open-source simple</div>
</div>

<div>
<div class="font-bold mb-2">Qdrant</div>
<div class="text-gray-600 text-base">Perf · Rust</div>
</div>


</div>

<div class="mt-16 text-2xl text-center">
🔍 Ces bases offrent :<br/>
<span class="text-lg text-gray-600">
Index vectoriels, filtrage par métadonnées, gestion du scale.
</span>
</div>

---
layout: two-cols
---

# Étape 4 : Retrieval 🔎

<div class="text-xl mt-8 space-y-8">

### Similarity Search

- On encode la **question**  
- On cherche les **k** chunks les plus proches  
- Mesure : cosine, dot product…

### Filtrage

- Par **source**, **date**, **type** de document  
- Ex : "seulement docs internes 2024"

</div>

::right::

<div class="mt-8 ml-8 text-xl space-y-8">

### Hybrid Search

Combiner :

- **BM25** (recherche lexicale)  
- **Vecteurs** (sémantique)



</div>

<!--
« Ici, on parle d’une recherche hybride, c’est-à-dire une combinaison entre deux approches :

BM25(Best Match 25), la recherche lexicale, très efficace quand on cherche les mêmes mots — par exemple pour retrouver une référence ou un code exact.

Et la recherche vectorielle, basée sur le sens des phrases, donc utile quand on reformule ou qu’on ne connaît pas le bon mot-clé.

En combinant les deux, on obtient le meilleur des deux mondes : la précision du lexical et la flexibilité du sémantique.

💡 C’est particulièrement utile dans des contextes techniques ou avec des noms propres, où les mots exacts comptent.
-->

---
layout: center
---

# 🔍 Hybrid Search

<div class="grid grid-cols-2 gap-16 items-center mt-16">

<div>

### 🧩 Principe

Combiner :
- **BM25** → recherche **lexicale**
- **Vecteurs** → recherche **sémantique**

<div class="text-lg text-gray-600 mt-6">
💡 Combine précision des mots-clés et compréhension du sens.
</div>

</div>

<div class="bg-gray-100 rounded-2xl p-6  text-gray-500 shadow-md">
<div class="text-3xl font-bold mb-4">Exemple</div>

<div class="text-lg leading-relaxed space-y-2">
🧠 Question : « Comment accélérer une requête LLM ? »  

🔎 <strong>BM25</strong> → trouve “LLM cache”  

🎯 <strong>Vecteur</strong> → trouve “prompt caching”, “inference cache”
</div>

<div class="mt-6 text-sm text-gray-500">
→ Résultat final : combinaison pondérée des deux scores
</div>
</div>

</div>


<div class="absolute  left-1/2 transform -translate-x-1/2 text-lg text-gray-500">
📝 Utile quand le vocabulaire est technique ou les noms propres critiques
</div>

---
layout: center
---

# Étape 5 : Reranking 🎯


<div class="mt-2 text-2xl space-y-10">

**Problème :**  
La recherche vectorielle ramène des chunks « à peu près » pertinents.

**Solution :**  
```mermaid
flowchart LR
  Q[🧑‍💻 User Query] --> V[🔍 Vector Search<br/>Top-20 résultats]
  V --> R[🤖 Reranker LLM spécialisé]
  R -->|Scores de pertinence| S[📊 Top-5 meilleurs passages]
  S --> L[🧠 LLM avec contexte filtré]
```
<div class="text-xl">
Modèle de <strong>reranking</strong> (Cohere, Jina, etc.) qui :


- relit la <strong>question + chaque chunk</strong> 
 
- donne un <strong>score de pertinence</strong> 

- réordonne et garde les meilleurs
</div>

</div>


<div class="mt-8 text-xl text-gray-600 text-center">
On passe de "pertinent globalement" à "ultra ciblé pour cette question".
</div>

---
layout: center
---

# 🧩 Exemple : Reranking en action

<div class="grid grid-cols-2 gap-16 items-center mt-12">

<div class="space-y-6 text-xl">

### 🧠 Question
> "Quels sont les avantages du cache sémantique dans un RAG ?"

### 🔍 Recherche initiale (vectorielle)
1️⃣ "Le cache réduit la latence."  
2️⃣ "Les embeddings sont stockés dans ChromaDB."  
3️⃣ "Le cache sémantique évite les requêtes redondantes."  
4️⃣ "Les chunks sont découpés en 512 tokens."



</div>

<div class="bg-gray-100 text-gray-500 rounded-2xl p-6 shadow-md">

### 🤖 Reranker (ex : Cohere Rerank v3)
Re-score chaque passage selon la **pertinence exacte à la question** :

| Passage | Score (0-1) |
|----------|-------------|
| "Le cache sémantique évite les requêtes redondantes." | 🟢 **0.95** |
| "Le cache réduit la latence." | 🟢 **0.82** |
| "Les embeddings sont stockés dans ChromaDB." | ⚪ 0.21 |
| "Les chunks sont découpés en 512 tokens." | ⚪ 0.10 |

<div class="mt-6 text-lg font-semibold text-center">
🎯 Résultat : le contexte final garde les 2 premiers passages → plus précis, moins de bruit.
</div>

</div>

</div>

<!--
📝 Le reranking affine la recherche avant l’appel au LLM.
-->

---
layout: center
---

# RAG Avancé 

<div class="mt-16 grid grid-cols-2 gap-10 text-xl">

<div class="space-y-6">

### Self-RAG
Le LLM **s’auto-contrôle** :  
<span class="text-gray-600 text-base">“Ai-je assez de contexte ? Dois-je relancer une recherche ?”</span>

### Corrective RAG
Corrige les erreurs :  
<span class="text-gray-600 text-base">post-vérification des réponses et "repair" si nécessaire.</span>

</div>

<div class="space-y-6">

### Adaptive RAG
Stratégie **dynamique** :  
<span class="text-gray-600 text-base">choix du nombre de documents, du type de recherche…</span>

### Agentic RAG
Des **agents** pilotent le RAG :  
<span class="text-gray-600 text-base">boucles de réflexion, multi-outils, workflows complexes.</span>

</div>

</div>

---
layout: center
---

# Évaluation du RAG 📏

<div class="mt-16 text-2xl space-y-10">

### RAGAS & Co

<div class="text-lg text-gray-600">
Frameworks qui mesurent :
</div>


- **Context Relevance** : contexte bien choisi ?  
- **Answer Correctness** : réponse juste ?  
- **Faithfulness** : la réponse s’appuie-t-elle sur le contexte ?


</div>

<div class="mt-10 text-xl text-center">
💡 Idée clé : on n’évalue plus seulement le LLM, mais le <strong>pipeline complet</strong>.
</div>

---
layout: center
---

# 🧩 Synthèse 2.1 – RAG

<div class="mt-14 grid grid-cols-2 gap-10 text-xl">

<div class="space-y-6">

✅ Séparer **raisonnement** (LLM) et **connaissance** (docs)  
✅ Pipeline : ingestion → chunking → embeddings → retrieval → génération  
✅ Vector DB = cœur de la stack RAG

</div>

<div class="space-y-6">

⚠️ Chunking : trouver le bon **granularité**  
⚠️ Retrieval seul ne suffit pas → **reranking** recommandé  
⚠️ Importance d’**évaluer** le pipeline (RAGAS, faithfulness…)

</div>

</div>

<div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 text-xl text-gray-500">
Next : 2.2 – Cache-Augmented Generation (CAG) ⭐
</div>


---
layout: section
---

# 2.2
# Cache-Augmented Generation (CAG)

---
layout: center
---

# ⚡ Cache-Augmented Generation
## Réutiliser intelligemment au lieu de recalculer

<div class="mt-12 text-2xl space-y-8">

💡 **Problème :**  
Chaque requête à un LLM coûte du **temps**, des **tokens** et donc de l’**argent**.

🧠 **Idée du CAG :**  
Quand une requête ou un contexte est **similaire à un déjà traité**,  
on **réutilise** une partie ou la totalité du résultat au lieu de tout recalculer.

</div>

---
layout: center
---

# 🔁 Pourquoi le Caching est essentiel en production

<div class="grid grid-cols-3 gap-10 mt-16 text-center text-xl">

<div>
<div class="text-5xl mb-4">💰</div>
<div class="font-bold mb-2">Réduction des coûts</div>
<div class="text-gray-600">Moins d’appels LLM → moins de tokens → -70 à -90 %</div>
</div>

<div>
<div class="text-5xl mb-4">⚡</div>
<div class="font-bold mb-2">Gain de latence</div>
<div class="text-gray-600">Réponse immédiate si cache hit</div>
</div>

<div>
<div class="text-5xl mb-4">📈</div>
<div class="font-bold mb-2">Scalabilité</div>
<div class="text-gray-600">Les serveurs gèrent plus d’utilisateurs avec les mêmes ressources</div>
</div>

</div>

---
layout: center
---

# 🧩 RAG vs CAG

| Caractéristique | **RAG** | **CAG** |
|-----------------|:------:|:------:|
| Objectif | Améliorer la **connaissance** | Améliorer la **performance** |
| Source externe | Oui (vector DB) | Non (cache interne) |
| Données injectées | Contexte documentaire | Contexte déjà traité |
| Type de gain | Pertinence | Latence / coût |
| Complémentaire ? | ✅ Oui, RAG → CAG combinables |

<div class="mt-8 text-xl text-gray-600">
💬 CAG ≠ RAG : le cache accélère le raisonnement, le RAG améliore la connaissance.
</div>

---
layout: center
---

# ⚙️ Types de caches dans le CAG

<div class="grid grid-cols-2 gap-12 mt-16 text-xl">

<div class="space-y-2">

### 🧠 KV Cache (Key-Value)
- Mémorise les **états d’attention** dans les Transformers  
- Utilisé lors de l’**inférence streaming**  
- Permet de générer plus vite la suite d’un texte  
### 💬 Prompt Caching
- Stocke des prompts ou requêtes déjà vues  
- Exemple : Anthropic, OpenAI, Google  
- Hash du prompt → réponse réutilisable  

</div>

<div class="space-y-2">

### 🔎 Semantic Caching
- Recherche de similarité sur les prompts  
- Si une requête est **proche sémantiquement** d’une précédente → réutilisation partielle  
- Implémenté dans **LiteLLM** et **LangChain**

### 🧩 Context Caching
- Réutilisation de blocs contextuels récurrents  
- Ex : “système prompt” constant, ou contexte RAG stable  

</div>

</div>

---
layout: center
---

# 🔬 Illustration : Semantic Cache Flow

```mermaid
flowchart LR
  Q[🧑‍💻 Nouvelle requête] --> H{🔎 Hash / Embedding<br/>déjà existant ?}
  H -->|Oui| R[💾 Retourne réponse cache]
  H -->|Non| L[🤖 Appel LLM]
  L --> S[🪣 Stocke embedding + réponse<br/>dans cache sémantique]
  S --> E[✅ Réponse utilisateur]
````

<div class="text-xl text-gray-600 mt-8">
💡 Un cache sémantique fonctionne comme une **mini base vectorielle interne**.
</div>

---

# 🧠 KV Cache – Niveau modèle

<div class="text-xl mt-8 space-y-6">

* Lors de l’inférence, le LLM garde en mémoire les clés et valeurs d’attention.
* À chaque token généré, il **réutilise les clés/valeurs déjà calculées**
  plutôt que de recalculer tout le contexte.

👉 Résultat : génération 2–4× plus rapide.

</div>

::right::

```mermaid
flowchart LR
  A[Input Tokens] --> B[Transformer Layer]
  B -->|K,V stockés| C[(KV Cache)]
  C --> D[Suivant Tokens<br/>réutilisent les K,V]
  D --> E[Sortie plus rapide]
```

<div class="text-sm text-gray-500 mt-6">
Implémenté nativement dans <b>vLLM, TGI, TensorRT-LLM, Ollama</b>.
</div>

---

# 💾 Exemple d’implémentation

## (Prompt / Semantic Cache avec LangChain)

```python
from langchain.cache import InMemoryCache
from langchain.globals import set_llm_cache
from langchain.embeddings import OpenAIEmbeddings
from langchain.vectorstores import Chroma

# 1️⃣ Cache mémoire simple
set_llm_cache(InMemoryCache())

# 2️⃣ Cache vectoriel (sémantique)
embeddings = OpenAIEmbeddings()
vector_cache = Chroma(embedding_function=embeddings)

# 3️⃣ Vérification avant requête
if vector_cache.similarity_search(query, k=1)[0].score > 0.9:
    return cached_response
else:
    response = llm.invoke(query)
    vector_cache.add_texts([query], metadatas=[response])
```

<div class="text-xl mt-6 text-gray-600">
💡 En prod : remplacer InMemoryCache par Redis, Milvus, ou MongoDB Atlas Vector Search.
</div>

---

# ⚙️ Politiques d’invalidation

| Type de stratégie                | Description                                | Usage                |
| -------------------------------- | ------------------------------------------ | -------------------- |
| ⏱ **TTL (Time-to-Live)**         | Expire après une durée donnée              | Questions volatiles  |
| 🧹 **LRU (Least Recently Used)** | Supprime les plus anciens hits             | Cache mémoire limité |
| 🧠 **Heuristique / ML**          | Basée sur fréquence ou score de similarité | Cache intelligent    |

<div class="mt-8 text-xl text-gray-600">
💬 Toujours équilibrer performance vs fraîcheur des résultats.
</div>

---

# 🧮 Impact mesuré

| Type de cache  | Latence   | Coût tokens | Exemple                        |
| -------------- | --------- | ----------- | ------------------------------ |
| KV Cache       | ↓ 50–90 % | —           | vLLM, TGI                      |
| Prompt Cache   | ↓ 70 %    | ↓ 70–90 %   | Anthropic, OpenAI              |
| Semantic Cache | ↓ 40–70 % | ↓ 30–80 %   | LiteLLM, LangChain             |
| Context Cache  | ↓ 30–50 % | ↓ 20–60 %   | Google Gemini, OpenAI o-series |

<div class="mt-8 text-xl text-gray-600">
💡 Cumulable : KV Cache + Semantic Cache = pipeline ultra-rapide ⚡
</div>

---

# 🏗️ Intégration en production

<div class="grid grid-cols-2 gap-12 mt-12 text-xl">


✅ **LangChain / LiteLLM** : gestion native du cache sémantique  
✅ **FastAPI** : endpoint REST avec Redis ou MongoDB comme cache  
✅ **vLLM / TensorRT-LLM** : KV Cache bas-niveau  
✅ **Prometheus / Grafana** : suivi cache hit-rate et latence


⚠️ **Invalidation obligatoire** après mises à jour de données  
⚠️ **Versionner les prompts** (hash prompt + model id)  
⚠️ **Sécuriser les stores** (auth, chiffrement, RBAC)  
⚠️ **Éviter fuite de données** dans logs de cache


</div>

---

# 💬 En résumé – Cache Augmented Generation

<div class="grid grid-cols-2 gap-12 mt-12 text-xl">


✅ Réutiliser au lieu de recalculer  
✅ Baisse latence & coûts drastique  
✅ Compatible RAG / production  
✅ Plusieurs niveaux : KV, Prompt, Semantic, Context


⚠️ Gérer invalidation et sécurité  
⚠️ Éviter stale data et collisions  
⚠️ Surveiller hit-rate %  
⚠️ Documenter politiques de cache



</div>

<div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 text-xl text-gray-500">
Next → 2.3 : Chain-of-Thought & Reasoning 🧠
</div>

---
layout: section
---

# 2.3
# Chain-of-Thought & Reasoning

---
layout: center
---

# 🧠 Chain-of-Thought (CoT)
## Apprendre à faire “penser” les modèles

<div class="mt-12 text-2xl space-y-8">

Les LLM ne “raisonnent” pas vraiment :  
ils **génèrent du texte** en suivant des corrélations.  

Mais on peut leur **enseigner à raisonner explicitement**,  
en leur demandant de **montrer leurs étapes de pensée**.

💡 C’est le **Chain-of-Thought (CoT)**.

</div>

---
layout: center
---

# 🔗 Principe du Chain-of-Thought

```text
Question : Si un train part à 10h de Paris à 100 km/h et un autre part à 11h de Lyon à 120 km/h, quand se croisent-ils ?

Réponse (sans CoT) : 12h47  
Réponse (avec CoT) :
- Distance Paris–Lyon = 460 km
- En 1h, le premier train parcourt 100 km → reste 360 km
- Vitesse relative = 100 + 120 = 220 km/h
- Temps pour se croiser = 360 / 220 ≈ 1.63 h
→ Réponse finale : 12h38
````

<div class="mt-8 text-xl text-gray-600">
💬 CoT = on ne veut pas juste la bonne réponse, on veut le raisonnement qui y mène.
</div>

---
layout: two-cols
---

# 🧩 Pourquoi ça marche
<div class="text-xl mt-8 space-y-4">

✅ Permet de **structurer la réflexion** du modèle

✅ Réduit les **erreurs logiques** et les hallucinations

✅ Améliore la **robustesse aux reformulations**

✅ Utile pour :

* Résolution de problèmes
* Calculs multi-étapes
* Raisonnement logique ou causal

</div>
::right::

```mermaid
flowchart TD
  Q[Question utilisateur] --> R1[Étape 1 : Analyse du problème]
  R1 --> R2[Étape 2 : Déduction]
  R2 --> R3[Étape 3 : Vérification]
  R3 --> A[✅ Réponse finale]
```

<div class="text-sm text-gray-500 mt-4">
🧠 Le modèle “simule” une pensée structurée avant de répondre.
</div>

---
layout: default
---

# 🧮 Zero-shot / Few-shot / Many-shot

| Type          | Exemple                                | Usage                      |
| ------------- | -------------------------------------- | -------------------------- |
| **Zero-shot** | “Explique ta réponse étape par étape.” | Simple, efficace           |
| **Few-shot**  | Ajout d’exemples de raisonnement       | Enseignement par imitation |
| **Many-shot** | +20 exemples contextuels               | Fine-tuning implicite      |

<div class="mt-8 text-xl text-gray-600">
💡 Le Few-shot CoT est le plus stable et le plus utilisé en production (OpenAI, Anthropic).
</div>

---
layout: default
---

# 🧠 Self-Consistency

<div class="mt-12 text-2xl space-y-8">

Les modèles peuvent se contredire d’un run à l’autre.
Pour pallier ça, on fait plusieurs CoT et on vote 🗳️

→ Le modèle **explore plusieurs chemins de pensée**,
puis **choisit la réponse la plus fréquente ou la plus cohérente.**

</div>

<div class="text-center text-xl text-gray-600 mt-8">
💬 Technique utilisée dans les modèles de raisonnement comme DeepSeek R1 ou OpenAI o3.
</div>

---
layout: two-cols
---
# 🧬 Tree-of-Thoughts (ToT)

<div class="text-xl mt-8 space-y-6">

* Au lieu d’une seule chaîne linéaire de raisonnement,
  le modèle explore **plusieurs branches possibles**.
* Chaque étape ouvre des “hypothèses”
  → on garde les meilleures, on rejette les autres.
* Approche inspirée des **search trees** (DFS, BFS).

</div>

::right::

```mermaid
graph TD
  Q(Question) --> A1[Idée 1]
  Q --> A2[Idée 2]
  A1 --> B1[Déduction 1]
  A1 --> B2[Déduction 2]
  A2 --> B3[Déduction 3]
  B2 --> C1[Réponse finale 🏁]
```

<div class="text-sm text-gray-500 mt-6">
🌳 Tree-of-Thoughts = raisonnement exploratoire.
</div>

---
layout: two-cols
---

# 🧬 Tree-of-Thoughts (ToT)

<div class="text-xl mt-8 space-y-6">

* Au lieu d’une seule chaîne linéaire de raisonnement,
  le modèle explore **plusieurs branches possibles**.
* Chaque étape ouvre des “hypothèses”
  → on garde les meilleures, on rejette les autres.
* Approche inspirée des **search trees** (DFS, BFS).

</div>

::right::

```mermaid
graph TD
  Q(Question) --> A1[Idée 1]
  Q --> A2[Idée 2]
  A1 --> B1[Déduction 1]
  A1 --> B2[Déduction 2]
  A2 --> B3[Déduction 3]
  B2 --> C1[Réponse finale 🏁]
```

<div class="text-sm text-gray-500 mt-6">
🌳 Tree-of-Thoughts = raisonnement exploratoire.
</div>

---
layout: center
---

# 🔍 Structuration et formats de sortie

| Format               | Exemple                                   | Utilisation              |
| -------------------- | ----------------------------------------- | ------------------------ |
| **JSON mode**        | `{ "reasoning": "...", "answer": "..." }` | API, intégration fiable  |
| **Function calling** | `function(solve_problem)`                 | Interaction avec backend |
| **ReAct pattern**    | “Think → Act → Observe”                   | Agents autonomes         |
| **Plan-and-Execute** | “Plan tasks → Execute sub-goals”          | Multi-step workflows     |

<div class="mt-8 text-xl text-gray-600">
💡 L’objectif : **rendre le raisonnement exploitable** par le code.
</div>

---
layout: default
---

# 🤖 Modèles de Raisonnement

<div class="grid grid-cols-2 gap-12 mt-16 text-2xl">

<div class="space-y-6">

🧠 **OpenAI o3 / o1-mini**  
<div class="text-lg text-gray-600">
Basés sur reasoning traces · 87.7% GPQA Diamond
</div>

🧩 **DeepSeek R1**

<div class="text-lg text-gray-600">
Open-source · 671B params · RL-only · raisonnement pur
</div>
</div>

<div class="space-y-6">

⚙️ **Claude 4 (Opus)**  
<div class="text-lg text-gray-600">
Raisonnement mixte + outils externes
</div>

🧮 **Gemini 2.5 Pro / Flash**

<div class="text-lg text-gray-600">
Optimisés pour réflexion rapide et multi-modale
</div>
</div>

</div>

<div class="mt-10 text-xl text-gray-600">
💡 Tous exploitent le CoT, Self-Consistency, et traces internes de raisonnement.
</div>

---
layout: default
---

# 🧩 CoT et Agents

<div class="text-2xl mt-12 space-y-8">

Les **agents** sont des systèmes basés sur LLM
qui utilisent le raisonnement **pour décider d’agir**.

→ Patterns fréquents :

* **ReAct** : penser → agir → observer
* **Plan-and-Execute** : plan global puis exécution pas à pas
* **Reflexion / Self-RAG** : raisonnement auto-correctif

</div>

<div class="text-xl mt-8 text-gray-600">
💡 Le CoT devient la “mémoire de travail” d’un agent autonome.
</div>

---
layout: default
---

# 🎯 En résumé – Chain-of-Thought & Reasoning

<div class="grid grid-cols-2 gap-12 mt-12 text-xl">

<div class="space-y-6">

✅ CoT = raisonnement explicite (montrer les étapes)  
✅ Few-shot & self-consistency → stabilité  
✅ Tree-of-Thoughts → raisonnement exploratoire  
✅ Formats structurés (JSON, ReAct, Plan-Execute)
</div>

<div class="space-y-6">

⚠️ Coût plus élevé en tokens  
⚠️ Risque de fuite de raisonnement (“show your work”)  
⚠️ Nécessite évaluation spécifique (logic accuracy, coherence)
</div>

</div>

<div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 text-xl text-gray-500">
Next → Pause ☕ avant Bloc 3 : Enablers & Protocoles
</div>

---
layout: section
---

# 3.1
# Frameworks d'Orchestration

---
layout: center
---

# ⚙️ Pourquoi un framework d’orchestration ?

<div class="mt-12 text-2xl space-y-8">

💡 Dans un projet IA, il ne suffit pas d’appeler un LLM.  
Il faut **enchaîner** : chargement des données, vectorisation, requêtes, cache, appels modèle, post-traitement, logs…

Ces pipelines deviennent vite complexes.  
Les frameworks d’orchestration permettent de les **structurer, tester et monitorer**.

</div>

<div class="mt-10 text-xl text-gray-600">
🎯 Objectif : industrialiser la génération, le RAG et les agents.
</div>

---
layout: center
---

# 🧩 Écosystème 2025

<div class="grid grid-cols-3 gap-8 mt-16 text-center text-xl">

<div>
<div class="text-5xl mb-4">🔗</div>
<div class="font-bold mb-2">LangChain</div>
<div class="text-gray-600">Le plus populaire · Chains & Graphs</div>
</div>

<div>
<div class="text-5xl mb-4">📚</div>
<div class="font-bold mb-2">LlamaIndex</div>
<div class="text-gray-600">Orienté Data / RAG avancé</div>
</div>

<div>
<div class="text-5xl mb-4">⚡</div>
<div class="font-bold mb-2">LiteLLM</div>
<div class="text-gray-600">API universelle pour tous les LLMs</div>
</div>

<div>
<div class="text-5xl mb-4">🤝</div>
<div class="font-bold mb-2">AutoGen / CrewAI</div>
<div class="text-gray-600">Multi-agents collaboratifs</div>
</div>

<div>
<div class="text-5xl mb-4">🧠</div>
<div class="font-bold mb-2">Semantic Kernel</div>
<div class="text-gray-600">Orchestration Microsoft / .NET</div>
</div>

</div>

---
layout: two-cols
---

# 🔗 LangChain (Python / JS)

<div class="text-xl mt-8 space-y-6">

- Le plus complet et documenté  
- Concept clé : **Chain** → suite d’étapes modulaires  
- Nouvelle syntaxe : **LCEL (LangChain Expression Language)**  
- Supporte :
  - LLMs, VectorStores, Tools, Agents  
  - Caching, Reranking, Evaluation (LangSmith)
- Intégration avec FastAPI, Airflow, MongoDB, Postgres

</div>

::right::

```mermaid
flowchart TD
  D[📄 Documents] --> E[🔎 Embeddings]
  E --> V[(Vector Store)]
  V --> R[🔁 Retrieval Chain]
  R --> L[🤖 LLMChain]
  L --> O[✅ Output]
````

<div class="text-sm text-gray-500 mt-4">
LangChain structure le pipeline complet : ingestion → recherche → génération.
</div>

---
layout: two-cols
---

# 📚 LlamaIndex

<div class="text-xl mt-8 space-y-6">

* Ex-GPT Index : orienté **Data RAG**
* Se concentre sur la **gestion de documents, index et requêtes complexes**
* Supporte plusieurs backends vectoriels : Chroma, MongoDB Atlas, Weaviate, Qdrant, pgvector
* Intègre le **graph RAG** (sémantique hiérarchique)
* Très utilisé pour projets **multi-source** ou **data warehouse**

</div>

::right::

```mermaid
flowchart LR
  A[PDF / SQL / API] --> B[Index Builders]
  B --> C[(Graph Index)]
  C --> D[Retriever]
  D --> L[LLM]
```

<div class="text-sm text-gray-500 mt-4">
💡 LlamaIndex = colle entre tes données et ton modèle.
</div>

---
layout: two-cols
---

# ⚡ LiteLLM

<div class="text-xl mt-8 space-y-6">

* API unique compatible avec **100+ LLMs** (OpenAI, Anthropic, Mistral, Ollama, Azure…)
* Standardise le format OpenAI (`chat.completions.create`)
* Simplifie :

  * Le **fallback** entre fournisseurs
  * Le **load balancing**
  * Le **tracking coûts**
  * Le **logging et caching**

</div>

::right::

```mermaid
flowchart TD
  A[App / API] --> L[LiteLLM Gateway]
  L -->|OpenAI| O[GPT-4]
  L -->|Anthropic| C[Claude 4]
  L -->|Mistral| M[Mistral Large]
  L -->|Local| X[Ollama / LM Studio]
```

<div class="text-sm text-gray-500 mt-6">
💡 LiteLLM = “le Stripe des APIs LLM” : unifie l’accès, réduit la friction.
</div>

---
layout: two-cols
---

# 🤝 AutoGen / CrewAI (Agents)

<div class="text-xl mt-8 space-y-6">

* **AutoGen** (Microsoft) : agents communicants avec rôles (user, assistant, critic)
* **CrewAI** : framework multi-agents open-source (Python)
* Permet la coordination de plusieurs LLMs dans une tâche :

  * Planification → exécution → validation
* Supporte la persistance, mémoire et supervision humaine

</div>

::right::

```mermaid
flowchart LR
  U[🧑‍💻 Utilisateur] --> A1[Agent 1 : Plan]
  A1 --> A2[Agent 2 : Exécute]
  A2 --> A3[Agent 3 : Vérifie]
  A3 --> R[✅ Résultat final]
```

<div class="text-sm text-gray-500 mt-6">
Agents = plusieurs cerveaux LLM coordonnés pour résoudre un problème.
</div>

---
layout: two-cols
---

# 🧠 Semantic Kernel (Microsoft)

<div class="text-xl mt-8 space-y-6">

* Framework open-source .NET / Python
* Permet de combiner prompts, outils, mémoire et plans
* S’intègre parfaitement à Azure OpenAI, Microsoft Fabric, et Graph API
* Fort accent sur **sécurité, monitoring et intégration entreprise**

</div>

::right::

```mermaid
flowchart LR
  U[User Request] --> P[Planner]
  P --> F[Functions - Tools]
  F --> M[Memory Store]
  M --> L[LLM Execution]
  L --> R[Response]
```

<div class="text-sm text-gray-500 mt-4">
🧩 Semantic Kernel = orchestrateur pour environnements Microsoft/enterprise.
</div>

---
layout: center
---

# ⚖️ Comparatif rapide

| Framework            | Points forts                     | Cas d’usage typique       |
| -------------------- | -------------------------------- | ------------------------- |
| **LangChain**        | Écosystème riche, standard open  | RAG / agents généralistes |
| **LlamaIndex**       | Gestion fine des données & index | Data-centric RAG          |
| **LiteLLM**          | Gateway unifiée pour 100+ LLMs   | Production multi-LLM      |
| **AutoGen / CrewAI** | Coordination multi-agents        | Automatisation complexe   |
| **Semantic Kernel**  | Intégration Azure / entreprise   | Environnements corporate  |

<div class="mt-10 text-xl text-gray-600">
💬 En pratique : souvent, **LangChain + LiteLLM + LlamaIndex** sont utilisés ensemble.
</div>

---
layout: center
---

# 🎓 En résumé – Frameworks d’Orchestration

<div class="grid grid-cols-2 gap-12 mt-12 text-xl">

<div class="space-y-6">

✅ Structurer les pipelines IA (RAG, CAG, Reasoning)  
✅ Simplifier les intégrations multi-LLM  
✅ Ajouter monitoring, cache et logs  
✅ Base pour l’intégration de MCP et A2A (prochaines sections)
</div>

<div class="space-y-6">

⚠️ Attention à la complexité des abstractions  
⚠️ Certaines libs évoluent très vite → veille nécessaire  
⚠️ Toujours évaluer latence / coût / maintenabilité
</div>

</div>

<div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 text-xl text-gray-500">
Next → 3.2 : Model Context Protocol (MCP) 🔌
</div>
Excellent 👌
On passe donc à **3.2 – Model Context Protocol (MCP)**, la sous-partie la plus importante du **Bloc 3**, car elle relie **tout le reste du cours** : c’est **la normalisation des intégrations IA**.

Ce module est clé pour comprendre comment les LLMs modernes (Claude, OpenAI o-series, Google Gemini 2.5…) se **branchent à des outils, données et environnements externes** de manière standardisée — et sécurisée.


---
layout: section
---

# 3.2
# Model Context Protocol (MCP)

---
layout: center
---

# 🔌 Model Context Protocol (MCP)
## Le “USB-C” universel pour connecter les IA

<div class="mt-12 text-2xl space-y-8">

💡 MCP est un **standard ouvert** créé en 2024  
pour permettre aux modèles et agents IA de  
**se connecter à n’importe quelle source de données ou outil**  
de manière **unifiée et sécurisée**.

</div>

<div class="mt-10 text-xl text-gray-600">
Conçu initialement par Anthropic · Adopté en 2025 par OpenAI, Google, AWS, etc.
</div>

---
layout: center
---

# 🧩 Pourquoi MCP est né

<div class="text-2xl mt-12 space-y-8">

Avant MCP, chaque acteur (OpenAI, Anthropic, Google, etc.)  
avait son propre format d’outils et d’intégrations.  

➡️ Résultat : un **problème M×N**  
> chaque modèle devait gérer chaque API séparément.

</div>

<div class="text-center mt-8 text-xl text-gray-600">
💬 MCP standardise la communication entre modèles, outils et données.
</div>

---
layout: center
---

# ⚙️ Architecture générale

```mermaid
flowchart LR
  A[🤖 MCP Client<br/>Agent / LLM] --> B[🔌 MCP Server<br/>Outil / Source de données]
  B --> A
  A --> U[🧑‍💻 Utilisateur / Application]
  B --> D[(📂 Base de données / API / Fichier)]
````

<div class="text-xl mt-6 text-gray-600">

Le LLM dialogue avec des serveurs MCP via un protocole commun (JSON-RPC 2.0).  
Chaque serveur expose ses **tools**, **resources**, **prompts** et **sampling**.
</div>

---
layout: two-cols
---

# 🧠 Les 4 capacités MCP

<div class="text-xl mt-8 space-y-6">

### 1️⃣ **Resources**

Accès aux données (fichiers, APIs, BDD)
→ lecture, filtrage, métadonnées

### 2️⃣ **Tools**

Actions exécutables par le modèle
→ “call tool” universel (équivalent à function calling)

### 3️⃣ **Prompts**

Templates pré-définis exposés par le serveur
→ réutilisables par différents agents

### 4️⃣ **Sampling**

Gestion déléguée du LLM (stream, multi-modèles)

</div>

::right::

```mermaid
flowchart TD
  S[(MCP Server)] --> R[Resources]
  S --> T[Tools]
  S --> P[Prompts]
  S --> SA[Sampling]
```

<div class="text-sm text-gray-500 mt-4">
Chaque capacité est accessible via JSON-RPC.  
💡 Les serveurs MCP peuvent être locaux ou distants.
</div>

---
layout: center
---

# 🧱 Architecture technique

| Composant            | Rôle                             | Exemple                                  |
| -------------------- | -------------------------------- | ---------------------------------------- |
| **MCP Client**       | LLM ou Agent IA                  | Claude 4.5, OpenAI o3, Google Gemini 2.5 |
| **MCP Server**       | Fournisseur de données ou outils | Google Drive, Slack, GitHub, PostgreSQL  |
| **Protocole**        | JSON-RPC 2.0                     | standard unifié                          |
| **Transport**        | HTTP / SSE / stdio               | selon contexte                           |
| **Interopérabilité** | multi-LLM / multi-vendor         | oui (open spec)                          |

<div class="mt-8 text-xl text-gray-600">
💡 Un serveur MCP peut être branché à plusieurs clients IA différents, sans adaptation spécifique.
</div>

---
layout: center
---

# 🔐 Sécurité & Gouvernance

<div class="grid grid-cols-2 gap-12 mt-16 text-xl">

<div class="space-y-6">

✅ Authentification par OAuth 2.1  
✅ Gestion fine des permissions (“scopes”)  
✅ Séparation des contextes d’exécution  
✅ Audit et logs d’appels tools/resources
</div>

<div class="space-y-6">

⚠️ 2025 : incidents signalés sur serveurs sans auth  
⚠️ Risques d’“over-permissioning” (cf. Replit, mai 2025)  
⚠️ Nouvelle spec : Auth obligatoire par défaut
</div>

</div>

<div class="mt-10 text-xl text-gray-600">
💬 Le MCP est pensé “secure-by-design”, mais nécessite une implémentation rigoureuse.
</div>

---
layout: center
---

# 🌐 Adoption en 2025

<div class="grid grid-cols-2 gap-12 mt-16 text-2xl">

<div class="space-y-6">

🧠 **Anthropic** → Claude Desktop & API  
⚡ **OpenAI** → Agents SDK (mars 2025)  
☁️ **Google** → Gemini 2.5 Pro (avril 2025)  
☁️ **AWS** → Steering Committee
</div>

<div class="space-y-6">

🧩 16 000+ serveurs communautaires  
💬 Support natif : Slack, GitHub, Notion, Google Drive  
💾 Connecteurs open-source : PostgreSQL, MongoDB, S3, Redis
</div>

</div>

<div class="mt-10 text-xl text-gray-600">
💡 En 2025, MCP devient la “plomberie standard” du RAG et des Agents.
</div>

---
layout: center
---

# 💡 Exemple d’intégration Claude Desktop

```yaml
# ~/Library/Application Support/Claude/claude_desktop_config.json
{
    "mcpServers": {
      "weather": {
        "command": "/Users/bricefotzo/.local/bin/uv",
        "args": [
          "--directory",
          "/Users/bricefotzo/workspace/perso/weather",
          "run",
          "weather.py"
        ]
      }
    }
  }
```

<div class="text-xl text-gray-600 mt-8">
Claude 4.5 détecte ces serveurs automatiquement  
→ accès direct à GitHub et PostgreSQL depuis l’interface IA.
</div>

---
layout: center
---

# 💡 Exemple d’intégration Claude Desktop

```yaml
# ~/Library/Application Support/Claude/claude_desktop_config.json
{
    "mcpServers": {
      ...
      },
      "mongodb": {
        "command": "docker",
        "args": [
          "run",
          "-i",
          "--rm",
          "-e",
          "MDB_MCP_CONNECTION_STRING",
          "mcp/mongodb"
        ],
        "env": {
          "MDB_MCP_CONNECTION_STRING": "mongodb+srv://username:pwd@serial-techos.hxiqgqy.mongodb.net/"
        }
      }
    }
  }
```

<div class="text-xl text-gray-600 mt-8">
Claude 4.5 détecte ces serveurs automatiquement  
→ accès direct à GitHub et PostgreSQL depuis l’interface IA.
</div>

---
layout: two-cols
---

# 🧩 Cas d’usage typiques

<div class="text-xl mt-8 space-y-6">

* 🔍 Connecter un LLM à ta base PostgreSQL / MongoDB Atlas
* 💬 Interagir avec Slack / Jira / Notion via tools
* 📂 Extraire et synthétiser du contenu Google Drive
* 📊 Exécuter des pipelines RAG en environnement contrôlé
* 🧠 Relier plusieurs IA à des ressources partagées

</div>

::right::

```mermaid
flowchart LR
  A[Claude / GPT / Gemini] -->|MCP| B[PostgreSQL]
  A -->|MCP| C[Slack]
  A -->|MCP| D[GitHub]
  A -->|MCP| E[Google Drive]
```

<div class="text-sm text-gray-500 mt-6">
💡 Chaque connexion suit la même spec MCP → déploiement simplifié.
</div>


---
layout: default
---

# 🔒 Bonnes pratiques de déploiement

| Aspect               | Recommandation                           |
| -------------------- | ---------------------------------------- |
| **Sécurité**         | Auth obligatoire, isolation des serveurs |
| **Observabilité**    | Logs d’accès tools/resources             |
| **Maintenance**      | Versionner les serveurs MCP              |
| **Interopérabilité** | Respect strict du JSON-RPC 2.0           |
| **Performance**      | Cache local + compression HTTP/SSE       |

<div class="mt-8 text-xl text-gray-600">
💡 Traiter un serveur MCP comme un microservice critique.
</div>

---
layout: default
---

# 🎓 En résumé – Model Context Protocol (MCP)

<div class="grid grid-cols-2 gap-12 mt-12 text-xl">

<div class="space-y-6">

✅ Standard universel pour connecter IA ↔ outils / données  
✅ JSON-RPC 2.0, extensible et open-source  
✅ Compatible multi-fournisseurs (Anthropic, OpenAI, Google)  
✅ Sécurisé (OAuth 2.1, scopes, audit)
</div>

<div class="space-y-6">

⚠️ Jeune standard (2024 → 2025)  
⚠️ Serveurs encore inégaux en qualité  
⚠️ Nécessite une politique de sécurité claire  
⚠️ À surveiller : MCP v2 (prévue 2026)
</div>

</div>

<div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 text-xl text-gray-500">
Next → 3.3 : Agent-to-Agent Protocol (A2A) 🤝
</div>

---
layout: section
---

# 3.3
# Agent-to-Agent Protocol (A2A)

---
layout: center
---

# 🤝 Agent-to-Agent (A2A)
## Quand les IA commencent à se parler

<div class="mt-12 text-2xl space-y-8">

💡 **A2A = protocole d’échange entre agents IA.**  
Permet à deux (ou plusieurs) agents de **se découvrir, communiquer et collaborer**,  
indépendamment du fournisseur (OpenAI, Google, Anthropic...).

</div>

<div class="text-xl text-gray-600 mt-8">
Conçu en 2025 par <strong>Google</strong> · standardisé par la Linux Foundation.
</div>

---
layout: center
---

# ⚙️ Architecture simplifiée

```mermaid
flowchart LR
  A1[🤖 Agent A] -->|HTTP + JSON-RPC| A2[🤖 Agent B]
  A2 -->|Event Stream - SSE| A1
  A1 --> U[🧑‍💻 Utilisateur / App]
````

<div class="text-xl text-gray-600 mt-8">
Chaque agent expose une “Agent Card” publique (capabilities, tools, contact).  
Les autres agents peuvent la lire et interagir via A2A.
</div>

---
## layout: center
---
# 🧩 Concepts clés

| Élément              | Description                                        |
| -------------------- | -------------------------------------------------- |
| **Agent Card**       | Fichier `.well-known/agent.json` décrivant l’agent |
| **Discovery**        | Identification des capacités et skills             |
| **Transport**        | HTTP + SSE + JSON-RPC                              |
| **Lifecycle**        | `submitted → working → completed`                  |
| **Interopérabilité** | multi-fournisseurs et open-source                  |

<div class="mt-8 text-xl text-gray-600">
💬 A2A = MCP entre agents, plutôt qu’entre modèle et outils.
</div>

---
## layout: center
---
# 🔗 MCP vs A2A

| Aspect       | MCP                       | A2A                             |
| ------------ | ------------------------- | ------------------------------- |
| Type de lien | Agent ↔ Outil / Données   | Agent ↔ Agent                   |
| Niveau       | Intégration               | Collaboration                   |
| Exemple      | Claude ↔ PostgreSQL       | Claude ↔ GPT-4o                 |
| Adoption     | Anthropic, OpenAI, Google | Google, Linux Foundation (2025) |

<div class="mt-8 text-xl text-gray-600">
Les deux sont **complémentaires** et souvent utilisés ensemble.
</div>

---

# 💡 Cas d’usage concrets

<div class="grid grid-cols-2 gap-12 mt-12 text-xl">

<div class="space-y-4">

🤝 **Collaboration multi-agents**  
(ex : un planificateur + un exécuteur)  

📊 **Coordination de tâches inter-apps**
(ex : agent marketing ↔ agent data)

</div>

<div class="space-y-4">

🔗 **Interop multi-cloud**  
(OpenAI ↔ Google Gemini ↔ Claude)

🧠 **Écosystèmes d’agents distribués**
(IBM ACP, Linux A2A, open-source)

</div>

</div>

---

# 🎯 En résumé – A2A

<div class="grid grid-cols-2 gap-12 mt-12 text-xl">

<div class="space-y-4">

✅ Communication directe entre agents IA  
✅ Standard ouvert et extensible  
✅ Basé sur JSON-RPC & HTTP  
✅ Complément naturel du MCP
</div>

<div class="space-y-4">

⚠️ Jeune standard (2025)  
⚠️ Authentification et sandbox encore limitées  
⚠️ Gouvernance multi-LLM en construction
</div>

</div>

<div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 text-xl text-gray-500">
Next → Bloc 4 : Production & Sécurité 🔒
</div>

---
layout: section
---

# 4.1
# Monitoring & Observabilité

---
layout: center
---

# 📊 Pourquoi monitorer un système IA ?

<div class="mt-12 text-2xl space-y-8">

💡 En production, **un LLM sans monitoring = une boîte noire**.  
Il faut suivre :
- ses **performances**
- ses **coûts**
- et la **qualité des réponses**

➡️ L’observabilité = pilier de la fiabilité et de la scalabilité.

</div>

<div class="text-xl text-gray-600 mt-8">
🎯 Objectif : détecter erreurs, dérives, coûts excessifs et dégradations qualité.
</div>

---
layout: two-cols
---

# 🧠 Les 3 dimensions du monitoring

<div class="text-xl mt-8 space-y-8">

### 1️⃣ Performance  
- Latence (temps moyen, TTFT)  
- Débit (req/sec, tokens/sec)  
- Disponibilité (% uptime)

### 2️⃣ Coût  
- Tokens input/output  
- Cache hit-rate  
- Coût par requête / utilisateur

### 3️⃣ Qualité  
- Hallucination rate  
- Faithfulness (véracité)  
- Pertinence (score humain / RAGAS)

</div>

::right::

```mermaid
graph TD
  A[Performance] --> D[Observabilité]
  B[Coût] --> D
  C[Qualité] --> D
  D --> R[🚦 Fiabilité globale]
```

<div class="text-sm text-gray-500 mt-4">
Les 3 axes sont liés : réduire le coût sans casser la qualité.
</div>

---
layout: two-cols
---

# 📈 Outils et plateformes

<div class="text-xl mt-8 space-y-6">

### 🔹 LangSmith (LangChain)

* Traces, latence, tokens, erreurs
* Comparaison A/B de prompts
* Replay & versioning des runs

### 🔹 Phoenix (Arize AI)

* Analyse visuelle des embeddings
* Détection de dérives / anomalies

### 🔹 TruLens

* Évalue la qualité (faithfulness, relevance)
* Supporte RAG, CoT, multi-models

</div>

::right::


<div class="text-xl mt-8 space-y-6">

### 🔹 Weights & Biases

* Tracking ML + LLM
* Dashboards + alertes

### 🔹 OpenTelemetry / Prometheus

* Instrumentation standard (latence, erreurs)
* Intégration avec Grafana

### 🔹 Datadog / New Relic

* Logs + alertes production
* Corrélation application / API / infra

</div>

<div class="mt-8 text-sm text-gray-500">
💡 En pratique : un mix LangSmith + OpenTelemetry = couverture complète.
</div>

---
## layout: two-cols
---
# 🧩 Exemple : pipeline instrumenté (RAG)

<div class="text-xl mt-8 space-y-6">

Instrumentation avec **OpenTelemetry** :

```python
from opentelemetry import trace

tracer = trace.get_tracer("rag-pipeline")

with tracer.start_as_current_span("query"):
    context = retriever.get_docs(query)
    response = llm.invoke(context)
```

→ permet de suivre :

* durée du retrieval
* temps d’inférence
* erreurs ou timeouts

</div>

::right::

```mermaid
flowchart LR
  Q[User Query] --> R[Retrieval Span]
  R --> L[LLM Span]
  L --> O[Response Span]
  subgraph Metrics
    A1[Latency]:::m
    A2[Tokens]:::m
    A3[Errors]:::m
  end
  classDef m fill:#def,stroke:#333;
```

<div class="text-sm text-gray-500 mt-6">
💡 Chaque étape du pipeline devient observable via traces et spans.
</div>

---
## layout: center
---
# 🧮 Table de métriques clés

| Catégorie   | Indicateur                 | Objectif                    |
| ----------- | -------------------------- | --------------------------- |
| Performance | Latence moyenne            | < 1 s pour requêtes courtes |
| Performance | TTFT (time to first token) | < 300 ms (vLLM / TGI)       |
| Coût        | Tokens moyens / requête    | suivre dérive               |
| Coût        | Cache hit rate             | > 70 %                      |
| Qualité     | Faithfulness score         | > 0.85                      |
| Qualité     | Hallucination rate         | < 5 %                       |

<div class="mt-10 text-xl text-gray-600">
💬 Ces valeurs guides servent à détecter les dérives avant l’utilisateur.
</div>

---
## layout: center
---
# 🧠 Évaluation qualitative automatisée

<div class="mt-12 text-2xl space-y-8">

Les outils comme **TruLens** ou **LangSmith Evaluate**
utilisent un LLM pour **noter les réponses d’un autre modèle**.

> “Cette réponse est-elle correcte, claire et cohérente avec le contexte ?”

💡 Approche “LLM-as-a-Judge” en production,
combinée à des feedbacks humains (calibration).

</div>

---

# ⚙️ A/B Testing & Expérimentation

<div class="grid grid-cols-2 gap-12 mt-16 text-xl">

<div class="space-y-6">

✅ Comparer deux versions de prompt / modèle  
✅ Mesurer impact sur qualité / coût / latence  
✅ Stocker les runs pour régression tests  
</div>

<div class="space-y-6">

⚠️ Toujours isoler les tests (dataset stable)  
⚠️ Utiliser sampling cohérent  
⚠️ Ne jamais déployer un nouveau prompt sans évaluation  
</div>

</div>

<div class="mt-10 text-xl text-gray-600">
💡 Le prompt est un composant logiciel : il se teste et se versionne.
</div>

---
## layout: center
---
# 🧩 Pipeline complet observé

```mermaid
flowchart LR
  A[User Request] --> B[FastAPI Endpoint]
  B --> C[LangChain Chain]
  C --> D[LiteLLM Gateway]
  D --> E[(LLM)]
  C --> F[(Vector Store)]
  B --> G[Monitoring Stack<br/>Prometheus + Grafana + LangSmith]
```

<div class="mt-10 text-xl text-gray-600">
💡 Observabilité intégrée = compréhension + confiance + scalabilité.
</div>

---

# 🎯 En résumé – Monitoring & Observabilité

<div class="grid grid-cols-2 gap-12 mt-12 text-xl">

<div class="space-y-4">

✅ Mesurer performance, coût et qualité  
✅ Utiliser outils : LangSmith, TruLens, Phoenix  
✅ Instrumenter avec OpenTelemetry  
✅ A/B tester et évaluer régulièrement  
</div>

<div class="space-y-4">

⚠️ Sans observabilité : dérives silencieuses  
⚠️ Qualité ≠ précision brute  
⚠️ Surveiller le coût par requête et cache hit-rate  
</div>

</div>

<div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 text-xl text-gray-500">
Next → 4.2 : Sécurité 🔒
</div>
