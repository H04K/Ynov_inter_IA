# 🤖 PROJET TECHCORP - Challenge IA 7h 🤖

## 📋 BRIEFING DE MISSION

**Contexte :** Vous êtes la nouvelle équipe technique de TechCorp Industries. L'équipe précédente a été licenciée suite à des soupçons de compromission du code et des données. Vous devez reprendre leur travail, valider l'intégrité du projet et finaliser le déploiement.

## 🎯 OBJECTIFS PRINCIPAUX

### 🚀 **Mission Critique - Production Ready**
**Déployer le modèle Phi-3.5-Financial sur Triton Inference Server avec interface chat :**
- Serveur Triton Inference Server opérationnel avec Phi-3.5-Financial
- Interface web moderne pour tester le modèle en temps réel
- Documentation technique pour la production

### 🔬 **Mission Expérimentale - R&D**
**Fine-tuner un modèle médical expérimental (pas pour production) :**
- Fine-tuning LoRA d'un modèle de base avec dataset médical fourni
- Tests et validation des performances conversationnelles
- *Note : Ce modèle reste expérimental, pas besoin de le déployer sur Triton*

## 📦 CE QUE VOUS AVEZ À DISPOSITION

### 🏗️ Infrastructure Technique
- **Serveur Triton Inference Server** (configuration partiellement faite)
- **Modèle Phi-3.5-Financial** (prêt à déployer, modèle principal)
- **Dataset médical** pour fine-tuning expérimental
- **Code source** de l'interface web de chat (non finalisé)
- **Accès Google Colab Pro** pour le fine-tuning et les tests

### 📁 Fichiers Hérités de l'Équipe Précédente
- Configuration Docker et scripts de déploiement Triton
- Code source de l'interface web (React/Node.js)
- Dataset de conversations médicales (format JSON)
- Documentation technique partielle
- *Quelques fichiers de logs et notes personnelles laissés sur les machines*

### 💡 **Pistes Techniques Suggérées**
- **Quantization** : Envisagez des modèles quantisés (4-bit/8-bit) pour optimiser les performances
- **Backend Python** : Triton supporte un backend Python plus simple que TensorRT
- **Modèles légers** : Une liste de modèles alternatifs légers est disponible en annexe

---

## 👥 RÉPARTITION DES RÔLES PAR FILIÈRE

### 🏗️ **INFRA** - L'Architecte du Système

**Votre Mission :**
- Déployer et configurer le serveur Triton Inference Server
- Configurer le backend Python pour Triton (plus simple que TensorRT)
- Optimiser les performances et monitoring système
- Tester les modèles quantisés pour améliorer les performances

**Livrables :**
- Serveur Triton opérationnel avec Phi-3.5-Financial
- Documentation de déploiement

---

### 🤖 **IA** - Le Spécialiste Modèles

**Mission Production :**
- Validation et tests du modèle Phi-3.5-Financial
- Optimisation des paramètres d'inférence

**Mission Expérimentale :**
- Fine-tuning LoRA d'un modèle médical avec le dataset fourni
- Tests de performance du modèle expérimental
- *Pas besoin de déployer ce modèle sur Triton*

**Livrables :**
- Modèle Phi-3.5-Financial validé et optimisé
- Modèle médical expérimental fine-tuné (LoRA)

---

### 📊 **DATA** - L'Expert Données

**Mission Production :**
- Validation des données d'entrée pour Phi-3.5-Financial
- Tests de qualité des conversations

**Mission Expérimentale :**
- Analyse et nettoyage du dataset médical
- Préparation des données pour le fine-tuning LoRA
- Validation de la qualité des conversations médicales

**Livrables :**
- Dataset médical préparé et nettoyé
- Rapport de qualité des données

---

### 🔒 **CYBER** - Le Responsable Sécurité

**Mission Production :**
- Audit de sécurité du déploiement Triton
- Tests de robustesse du modèle Phi-3.5-Financial
- Validation de l'intégrité des réponses

**Mission Expérimentale :**
- Tests de sécurité du modèle médical fine-tuné
- Vérification de l'absence de biais problématiques

**Livrables :**
- Rapport d'audit sécurité
- Tests de robustesse validés

---

### 🌐 **DEV WEB** - Le Développeur Interface

**Mission Production :**
- Finaliser l'interface web de chat
- Intégrer l'API Triton pour communication avec Phi-3.5-Financial
- Interface utilisateur intuitive pour tester le modèle

**Livrables :**
- Interface web complète et fonctionnelle
- Intégration API temps réel avec Triton

---

## 📊 CRITÈRES D'ÉVALUATION

### 🏆 **Réussite Complète (18-20/20)**
- ✅ Triton Server opérationnel avec Phi-3.5-Financial
- ✅ Interface web fluide et professionnelle
- ✅ Modèle médical expérimental fine-tuné avec succès
- ✅ Documentation technique complète
- ✅ Optimisations de performance (quantization, backend Python)

### 🥈 **Réussite Satisfaisante (14-17/20)**
- ✅ Système de base fonctionnel
- ⚠️ Interface avec quelques limitations
- ⚠️ Fine-tuning réussi mais non optimisé
- ⚠️ Documentation partielle

### 🥉 **Réussite Minimale (10-13/20)**
- ✅ Déploiement basique réussi
- ❌ Interface incomplète
- ❌ Fine-tuning non finalisé
- ❌ Documentation insuffisante

---

## 🛠️ RESSOURCES TECHNIQUES FOURNIES

### 📁 **Architecture du Projet**
```
techcorp-ai-chat/
├── tritton_server/              # Configuration Triton Inference Server
├── phi_financial_model/         # Modèle Phi-3.5-Financial
├── medical_dataset/            # Dataset pour fine-tuning médical expérimental
├── web_interface/              # Interface React/Node.js (non finalisée)
├── docker/                     # Configurations Docker
├── scripts/                    # Scripts de déploiement et utilitaires
├── docs/                       # Documentation technique (partielle)
├── team_logs_archive.md        # Logs de l'équipe précédente
└── README_medical_fine_tuning.md # Guide fine-tuning médical
```

### 🧠 **Modèles IA Disponibles**
1. **Phi-3.5-Financial** - Modèle spécialisé finance/business

### 💻 **Infrastructure**
- **Google Colab Pro** : GPU A100 pour fine-tuning et tests
- **Triton Inference Server** : Déploiement optimisé des modèles
- **Docker containers** : Environnement isolé et reproductible

### 🔧 **Pistes Techniques Détaillées**

**Quantization Options :**
- GPTQ 4-bit pour réduire la mémoire
- AWQ pour préserver la qualité
- BitsAndBytes pour quantization dynamique

**Backend Triton Python :**
- Plus simple que TensorRT/ONNX
- Support natif HuggingFace Transformers
- Debugging facilité

**Modèles Légers Alternatifs :**
- Phi-3.5-Mini (3.8B paramètres)
- Qwen2.5-3B
- Mistral-7B quantisé
- TinyLlama-1.1B

## 📝 **DOCUMENTATION ET GUIDES**
### 📚 **Ressource utile : [Déploiement rapide de modèles HuggingFace avec Triton Inference Server](https://github.com/triton-inference-server/tutorials/tree/main/Quick_Deploy/HuggingFaceTransformers)**
### 📖 **Dataset Médical : [Dataset Hugging Face pour POC](https://huggingface.co/datasets/ruslanmv/ai-medical-chatbot)**
---

## 🎯 MISSION FINALE

**Votre objectif principal : Rendre le modèle Phi-3.5-Financial accessible via une interface chat professionnelle déployée sur Triton Server.**

*Le fine-tuning médical est un bonus expérimental - concentrez-vous d'abord sur la mission de production !*

**TechCorp compte sur vous pour finaliser ce projet. Explorez les fichiers laissés par l'équipe précédente, ils peuvent contenir des informations utiles !**

---

## 🚀 **PRÊTS ? À VOS CLAVIERS !** 

*Bonne chance pour ce défi technique ! La réussite de TechCorp dépend de votre expertise.* 🤖✨