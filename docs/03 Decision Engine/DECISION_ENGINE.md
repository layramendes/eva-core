# DECISION_ENGINE.md

**Document:** DECISION_ENGINE.md  
**Version:** 1.0.0  
**Status:** Approved  
**Owner:** EVA Core Team  
**Last Updated:** 2026-06-29

---

# 1. Purpose

O Decision Engine é o cérebro da EVA.

Sua única responsabilidade é transformar análises em decisões editoriais.

Ele nunca renderiza vídeos.

Ele nunca modifica arquivos.

Ele nunca aplica efeitos.

Ele apenas decide.

---

# 2. Inputs

O Decision Engine recebe apenas objetos estruturados.

## VideoContext

Produzido pelo Video Intelligence.

Contém:

- cenas
- enquadramentos
- rostos
- objetos
- movimentos
- composição
- emoção visual

---

## AudioContext

Produzido pelo Audio Intelligence.

Contém:

- transcrição
- pausas
- silêncio
- emoção
- energia
- velocidade
- ruído
- locutores

---

## Goal

Objetivo principal.

Exemplos:

- Conversão
- Viralização
- Educação
- Storytelling

---

## Style

Estilo desejado.

Exemplos:

- UGC
- Minimal
- Corporate
- Cinematic

---

## Knowledge

Regras editoriais.

Heurísticas.

Templates.

Boas práticas.

---

# 3. Output

O único resultado possível é:

EELDocument

Nada mais.

---

# 4. Decision Pipeline

VideoContext

+

AudioContext

+

Knowledge

+

Goal

+

Style

↓

Decision Engine

↓

EELDocument

---

# 5. Decision Flow

Toda decisão segue exatamente esta sequência.

1. Entender

2. Identificar oportunidades

3. Gerar candidatos

4. Avaliar candidatos

5. Escolher a melhor decisão

6. Validar

7. Gerar instrução EEL

---

# 6. Decision Object

Toda decisão possui obrigatoriamente:

```yaml
id:

type:

reason:

confidence:

agent:

rule:

ruleVersion:

timestamp:

priority:
```

---

# 7. Decision Types

A EVA pode gerar decisões como:

CUT

TRIM

ZOOM

CAPTION

TEXT

TRANSITION

MUSIC

SFX

COLOR

CROP

SPEED

OVERLAY

IMAGE

FREEZE

MASK

VOICE

SUBTITLE

---

# 8. Decision Priority

Prioridade:

CRITICAL

HIGH

MEDIUM

LOW

---

# 9. Confidence

Toda decisão possui confiança.

Escala:

0.00

↓

1.00

Exemplo

0.96

---

# 10. Decision Validation

Nenhuma decisão é aceita sem responder:

Existe objetivo?

Existe justificativa?

Existe ganho esperado?

Existe regra?

Existe agente?

Existe confiança?

Se qualquer resposta for NÃO:

A decisão é descartada.

---

# 11. Rule System

Toda decisão é baseada em regras.

Nunca em improvisação.

Exemplo:

CUT_SILENCE_001

HOOK_VISUAL_002

CAPTION_SHORT_004

---

# 12. Rule Versioning

Toda regra possui versão.

Exemplo

CUT_SILENCE_001

v1.0

v1.1

v2.0

---

# 13. Agents

O Decision Engine nunca executa IA diretamente.

Ele consulta agentes.

Exemplos:

HookAgent

EmotionAgent

NarrativeAgent

CaptionAgent

MotionAgent

AudioAgent

ReviewAgent

---

# 14. Conflict Resolution

Quando dois agentes discordam.

O Decision Engine deve:

comparar confiança

↓

comparar prioridade

↓

comparar objetivo

↓

selecionar vencedor

---

# 15. Decision Principles

Toda decisão deve:

melhorar compreensão

OU

melhorar retenção

OU

melhorar emoção

OU

melhorar clareza

Caso contrário:

não executar.

---

# 16. Explainability

Toda decisão precisa responder:

Por que foi tomada?

Qual regra foi utilizada?

Qual agente decidiu?

Qual conhecimento foi consultado?

---

# 17. Determinism

Mesmas entradas.

Mesmas regras.

Mesmo conhecimento.

↓

Mesmo resultado.

Sempre.

---

# 18. Audit

Toda decisão fica registrada.

Incluindo:

entrada

saída

tempo

modelo

tokens

regra

confiança

---

# 19. Decision Lifecycle

Created

↓

Validated

↓

Approved

↓

Converted to EEL

↓

Rendered

↓

Evaluated

↓

Learned

---

# 20. Responsibilities

O Decision Engine deve:

✓ decidir

✓ justificar

✓ validar

✓ documentar

✓ gerar EEL

---

# 21. Non Responsibilities

O Decision Engine nunca deve:

✗ renderizar

✗ editar vídeo

✗ acessar banco diretamente

✗ exportar arquivos

✗ publicar conteúdo

✗ criar interface

---

# 22. Golden Rule

O Decision Engine não pergunta:

"Como editar este vídeo?"

Ele pergunta:

"Qual decisão editorial produz o melhor resultado para o objetivo definido?"