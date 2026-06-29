# LEARNING_ENGINE.md

**Document:** LEARNING_ENGINE.md  
**Version:** 1.0.0  
**Status:** Approved  
**Owner:** EVA Core Team  
**Last Updated:** 2026-06-29

---

# 1. Purpose

O Learning Engine é responsável pela evolução contínua da EVA.

Sua função é transformar decisões, feedbacks e resultados em conhecimento reutilizável.

Ele nunca toma decisões editoriais.

Ele nunca renderiza vídeos.

Ele nunca modifica diretamente o Knowledge Engine.

---

# 2. Mission

Permitir que a EVA melhore continuamente sua capacidade de edição através da observação dos resultados obtidos.

---

# 3. Responsibilities

O Learning Engine deve:

- armazenar feedback
- armazenar decisões
- medir desempenho
- detectar padrões
- construir datasets
- gerar métricas
- identificar regressões
- recomendar melhorias

---

# 4. Inputs

O Learning Engine recebe:

## Decision History

Todas as decisões produzidas pelo Decision Engine.

---

## EEL Document

Documento final utilizado na renderização.

---

## User Feedback

Exemplos:

- gostei
- não gostei
- aprovado
- rejeitado
- editado manualmente

---

## Performance Metrics

Exemplos:

- watch time
- retenção
- CTR
- taxa de conclusão
- engajamento
- conversão

---

## Render Metadata

Tempo de renderização.

Motor utilizado.

Custo.

---

# 5. Outputs

O Learning Engine produz:

- Score
- Insights
- Datasets
- Recomendações
- Alertas
- Estatísticas

Nunca altera vídeos.

---

# 6. Feedback Types

## Explicit

Fornecido pelo usuário.

Exemplos:

★★★★★

Like

Dislike

Aceito

Rejeitado

---

## Implicit

Obtido automaticamente.

Exemplos:

Usuário alterou legenda.

Usuário removeu zoom.

Usuário apagou música.

Usuário exportou sem alterações.

---

## External

Obtido após publicação.

Exemplos:

Retenção.

Conversão.

Visualizações.

CTR.

---

# 7. Decision Tracking

Toda decisão recebe um identificador permanente.

Exemplo

Decision

↓

Feedback

↓

Resultado

↓

Aprendizado

---

# 8. Learning Object

```yaml
id:

decisionId:

feedback:

score:

performance:

createdAt:
```

---

# 9. Scoring

Toda edição recebe um score.

Escala

0

↓

100

---

## Critérios

Clareza

Narrativa

Retenção

Objetivo

Qualidade

Consistência

---

# 10. Decision Score

Cada decisão também recebe nota.

Exemplo

CUT

↓

92

ZOOM

↓

71

CAPTION

↓

98

---

# 11. Pattern Detection

O Learning Engine identifica padrões.

Exemplos

Zooms aumentam retenção.

Legenda longa reduz conclusão.

Música alta reduz compreensão.

---

# 12. Dataset Generation

Todo aprendizado gera datasets.

Tipos

Editorial

Visual

Áudio

Narrativa

Objetivos

Estilos

---

# 13. Recommendation Engine

O Learning Engine nunca altera regras.

Ele apenas recomenda.

Exemplo

"A regra CUT_SILENCE_001 apresentou queda de desempenho."

---

# 14. Regression Detection

Sempre compara versões.

Exemplo

Rule v1.2

↓

Retenção

84%

Rule v1.3

↓

Retenção

79%

↓

Alerta.

---

# 15. Knowledge Suggestions

Pode sugerir:

Nova regra.

Nova heurística.

Novo estilo.

Nova prioridade.

Nunca aplica automaticamente.

---

# 16. Human Review

Toda alteração recomendada precisa de aprovação.

O Learning Engine nunca modifica conhecimento sozinho.

---

# 17. Memory

Todo histórico permanece disponível.

Nada é perdido.

Toda decisão pode ser rastreada.

---

# 18. Analytics

O Learning Engine fornece indicadores como:

- taxa de aprovação
- taxa de rejeição
- regras mais utilizadas
- agentes mais eficientes
- estilos mais utilizados
- objetivos mais eficientes

---

# 19. Model Evaluation

Também mede desempenho dos modelos de IA.

Exemplos

Gemini

↓

Qualidade

↓

Custo

↓

Tempo

↓

Precisão

Claude

↓

Qualidade

↓

Custo

↓

Tempo

↓

Precisão

---

# 20. Future Training

O principal objetivo é gerar datasets proprietários.

Esses datasets serão utilizados futuramente para treinamento de modelos próprios da EVA.

---

# 21. Non Responsibilities

O Learning Engine nunca deve:

✗ editar vídeos

✗ gerar EEL

✗ renderizar

✗ criar regras automaticamente

✗ substituir o Decision Engine

---

# 22. Golden Rule

Todo aprendizado deve ser baseado em evidências.

Nunca em suposições.