---
language:
  - fr
  - en
license: cc-by-4.0
library_name: transformers
base_model: Helsinki-NLP/opus-mt-fr-en
tags:
  - translation
  - opus-mt
  - marian-mt
  - marianMTModel
  - fr-to-en
  - neuro-symbolic
  - NMT
datasets:
  - opus_books
metrics:
  - bleu
  - sacrebleu
pipeline_tag: translation
---

# last release : March 16 2026 (added functions to uplaod PDF or TeX file and separate the whole corpus in 528 tokkens chuncks)

# opus-mt-fr-en-finetuned-fr-to-en

Modèle de traduction automatique neuronale (NMT) **français → anglais**, fine-tuné à partir du modèle de base [`Helsinki-NLP/opus-mt-fr-en`](https://huggingface.co/Helsinki-NLP/opus-mt-fr-en) dans le cadre des recherches doctorales en **IA hybride neuro-symbolique** à l'UQAM.

## Model Description

Ce modèle est basé sur l'architecture **MarianMT** (Marian NMT converti en PyTorch via 🤗 Transformers). Il a été fine-tuné pour améliorer la traduction de textes académiques et informationnels du français vers l'anglais, avec un focus sur des corpus spécialisés liés à la vérification de la crédibilité de l'information.

- **Architecture** : MarianMTModel (Encoder-Decoder)
- **Modèle de base** : `Helsinki-NLP/opus-mt-fr-en`
- **Tâche** : Traduction automatique (fr → en)
- **Langue source** : Français (`fr`)
- **Langue cible** : Anglais (`en`)
- **Framework** : 🤗 Transformers / PyTorch

## Intended Uses & Limitations

### Utilisations prévues
- Traduction de textes académiques et journalistiques du français vers l'anglais
- Composant NLP dans des pipelines de vérification de la crédibilité de l'information
- Recherche en traduction automatique neuronale

### Limitations
- Performances réduites sur des textes très spécialisés hors domaine d'entraînement
- Ne gère pas les dialectes régionaux du français
- Longueur maximale recommandée : 512 tokens par segment

## How to Use

### Avec `pipeline` (recommandé)

```python
from transformers import pipeline

translator = pipeline(
    "translation",
    model="DomLoyer/opus-mt-fr-en-finetuned-fr-to-en"
)

result = translator("La crédibilité de l'information est essentielle à l'ère numérique.")
print(result['translation_text'])
```



Citation:

```bibtex

## Auteur

**Dominique Loyer**  
Doctorant en Informatique Cognitive — UQAM  
ORCID: [0009-0003-9713-7109](https://orcid.org/0009-0003-9713-7109)  
Hugging Face: [@DomLoyer](https://huggingface.co/DomLoyer)

## License

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)

```

