# OfensaBR-10k Dataset

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![HuggingFace](https://img.shields.io/badge/🤗-HuggingFace-orange)](https://huggingface.co/datasets/pjarbas312/OfensaBR-10k)
[![Language: Portuguese](https://img.shields.io/badge/Language-Portuguese%20(BR)-green)](https://en.wikipedia.org/wiki/Brazilian_Portuguese)

Dataset em português brasileiro para detecção de linguagem ofensiva, coletado de redes sociais (Twitter/X). Contém 10.000 textos balanceados classificados automaticamente.

[English](#english-version) | [Português](#versão-em-português)

---

## Versão em Português

### 📊 Visão Geral

OfensaBR-10k é um dataset balanceado de textos em português brasileiro coletados do Twitter/X para detecção de conteúdo ofensivo. Ideal para:

- 🛡️ Sistemas de moderação de conteúdo
- 🔍 Pesquisa em detecção de toxicidade
- 🤖 Treinamento de modelos de classificação
- 📱 Análise de redes sociais em PT-BR
- ✅ Sistemas de guardrails e segurança

### 🎯 Estrutura do Dataset

Cada instância contém:

```json
{
  "id": 0,
  "text": "Exemplo de texto da rede social",
  "category": "OFFENSIVE",
  "score": 0.87
}
```

**Campos:**
- `id`: Identificador único
- `text`: Comentário ou resposta de rede social
- `category`: `OFFENSIVE` ou `NON_OFFENSIVE`
- `score`: Confiança do classificador (0.0 a 1.0)

### 📈 Estatísticas

| Métrica | Valor |
|---------|-------|
| **Total de Textos** | 10.000 |
| **Balanceamento** | 50% OFFENSIVE / 50% NON_OFFENSIVE |
| **Idioma** | 100% Português (BR) |
| **Tamanho Mínimo** | 10 caracteres |
| **Duplicatas** | Removidas |

### 🚀 Como Usar

#### Via HuggingFace Datasets

```python
from datasets import load_dataset

# Carregar dataset
dataset = load_dataset("pjarbas312/OfensaBR-10k")

# Acessar dados
for example in dataset['train']:
    print(f"Texto: {example['text']}")
    print(f"Categoria: {example['category']}")
    print(f"Score: {example['score']}\n")
```

#### Download Direto (CSV)

```bash
# Clone o repositório
git clone https://github.com/PJarbas/OfensaBR-10k.git
cd OfensaBR-10k

# O dataset está em formato CSV
# Utilize com pandas, polars, ou qualquer biblioteca de sua escolha
```

```python
import pandas as pd

df = pd.read_csv('ofensaBR_10k.csv')
print(df.head())
```

### ⚠️ Aviso de Conteúdo

**Este dataset contém linguagem ofensiva por design**, incluindo:
- Profanidade e linguagem vulgar
- Insultos e ataques pessoais
- Discurso de ódio e conteúdo discriminatório
- Expressões tóxicas e prejudiciais

**Use com responsabilidade e salvaguardas apropriadas.**

### ✅ Usos Apropriados

- Treinar sistemas de moderação de conteúdo
- Pesquisa acadêmica sobre linguagem ofensiva
- Desenvolvimento de ferramentas de segurança online
- Benchmarking de modelos de NLP em PT-BR
- Análise de discurso em redes sociais

### ❌ Usos Inapropriados

- Treinar sistemas para gerar conteúdo ofensivo
- Assédio ou direcionamento de indivíduos
- Discriminação ou perfilamento
- Vigilância sem consentimento

### 🔬 Metodologia de Criação

**Coleta de Dados:**
- Fonte: Comentários públicos do Twitter/X
- Filtros: Apenas português (langdetect), mínimo 10 caracteres
- Privacidade: Sem usernames, timestamps ou metadados

**Classificação:**
- Modelo: [Detoxify](https://github.com/unitaryai/detoxify) (`unitary/multilingual-toxic-xlm-roberta`)
- Threshold: 0.5 (score > 0.5 = OFFENSIVE)
- Método: Classificação automática (sem anotação humana)

### ⚖️ Limitações Conhecidas

- ⚠️ **Classificação automática**: Não verificado por humanos
- ⚠️ **Viés cultural**: Pode refletir vieses presentes nas redes sociais
- ⚠️ **Contexto limitado**: Textos isolados da thread de conversação
- ⚠️ **Variação temporal**: Reflete o uso da linguagem no momento da coleta
- ⚠️ **Nuances perdidas**: Threshold binário pode não capturar toda a nuance

### 📄 Licença

Este dataset é licenciado sob a [MIT License](LICENSE).

### 📚 Citação

Se você usar este dataset em sua pesquisa, por favor cite:

```bibtex
@dataset{ofensabr10k2025,
  title={OfensaBR-10k: A Brazilian Portuguese Dataset for Offensive Language Detection},
  author={Jarbas, Paulo},
  year={2025},
  publisher={HuggingFace},
  howpublished={\url{https://huggingface.co/datasets/pjarbas312/OfensaBR-10k}}
}
```

## English Version

### 📊 Overview

OfensaBR-10k is a balanced dataset of Brazilian Portuguese texts collected from Twitter/X for offensive content detection. Ideal for:

- 🛡️ Content moderation systems
- 🔍 Toxicity detection research
- 🤖 Training classification models
- 📱 PT-BR social media analysis
- ✅ Guardrails and safety systems

### 🎯 Dataset Structure

Each instance contains:

```json
{
  "id": 0,
  "text": "Sample social media text",
  "category": "OFFENSIVE",
  "score": 0.87
}
```

**Fields:**
- `id`: Unique identifier
- `text`: Social media comment or reply
- `category`: `OFFENSIVE` or `NON_OFFENSIVE`
- `score`: Classifier confidence (0.0 to 1.0)

### 📈 Statistics

| Metric | Value |
|--------|-------|
| **Total Texts** | 10,000 |
| **Balance** | 50% OFFENSIVE / 50% NON_OFFENSIVE |
| **Language** | 100% Portuguese (BR) |
| **Min Length** | 10 characters |
| **Duplicates** | Removed |

### 🚀 How to Use

#### Via HuggingFace Datasets

```python
from datasets import load_dataset

# Load dataset
dataset = load_dataset("pjarbas312/OfensaBR-10k")

# Access data
for example in dataset['train']:
    print(f"Text: {example['text']}")
    print(f"Category: {example['category']}")
    print(f"Score: {example['score']}\n")
```

#### Direct Download (CSV)

```bash
# Clone the repository
git clone https://github.com/PJarbas/OfensaBR-10k.git
cd OfensaBR-10k

# Dataset is in CSV format
# Use with pandas, polars, or any library of your choice
```

```python
import pandas as pd

df = pd.read_csv('ofensaBR_10k.csv')
print(df.head())
```

### ⚠️ Content Warning

**This dataset contains offensive language by design**, including:
- Profanity and vulgar language
- Insults and personal attacks
- Hate speech and discriminatory content
- Toxic and harmful expressions

**Use responsibly and with appropriate safeguards.**

### ✅ Appropriate Uses

- Training content moderation systems
- Academic research on offensive language
- Developing online safety tools
- Benchmarking PT-BR NLP models
- Social media discourse analysis

### ❌ Inappropriate Uses

- Training systems to generate offensive content
- Harassment or targeting individuals
- Discrimination or profiling
- Surveillance without consent

### 🔬 Creation Methodology

**Data Collection:**
- Source: Public Twitter/X comments
- Filters: Portuguese only (langdetect), minimum 10 characters
- Privacy: No usernames, timestamps, or metadata

**Classification:**
- Model: [Detoxify](https://github.com/unitaryai/detoxify) (`unitary/multilingual-toxic-xlm-roberta`)
- Threshold: 0.5 (score > 0.5 = OFFENSIVE)
- Method: Automatic classification (no human annotation)

### ⚖️ Known Limitations

- ⚠️ **Automatic classification**: Not verified by humans
- ⚠️ **Cultural bias**: May reflect biases present in social media
- ⚠️ **Limited context**: Texts isolated from conversation threads
- ⚠️ **Temporal variation**: Reflects language use at collection time
- ⚠️ **Lost nuances**: Binary threshold may not capture all nuance

### 📄 License

This dataset is licensed under the [MIT License](LICENSE).

### 📚 Citation

If you use this dataset in your research, please cite:

```bibtex
@dataset{ofensabr10k2025,
  title={OfensaBR-10k: A Brazilian Portuguese Dataset for Offensive Language Detection},
  author={Jarbas, Paulo},
  year={2025},
  publisher={HuggingFace},
  howpublished={\url{https://huggingface.co/datasets/pjarbas312/OfensaBR-10k}}
}
```
