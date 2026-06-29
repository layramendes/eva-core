# KNOWLEDGE_ENGINE.md

**Document:** KNOWLEDGE_ENGINE.md  
**Version:** 1.0.0  
**Status:** Approved  
**Owner:** EVA Core Team  
**Last Updated:** 2026-06-29

---

# 1. Purpose

O Knowledge Engine é o cérebro de conhecimento da EVA.

Ele não toma decisões.

Ele fornece conhecimento para que o Decision Engine tome decisões consistentes.

Todo comportamento da EVA deve ser baseado em conhecimento armazenado neste módulo.

---

# 2. Responsibilities

O Knowledge Engine deve:

- armazenar conhecimento editorial
- organizar conhecimento
- versionar conhecimento
- disponibilizar conhecimento
- validar conhecimento
- permitir evolução contínua

Nunca gera EEL.

Nunca renderiza vídeos.

Nunca modifica vídeos.

---

# 3. Knowledge Categories

Todo conhecimento pertence a uma categoria.

## Editorial Rules

Regras editoriais.

Exemplos:

- remover silêncio
- manter continuidade
- evitar excesso de texto
- limitar duração das legendas

---

## Heuristics

Conhecimento baseado em experiência.

Exemplos:

- produtos devem aparecer cedo
- benefícios devem aparecer antes das características
- emoção aumenta retenção

---

## Styles

Define estilos editoriais.

Exemplos:

- UGC
- Cinematic
- Corporate
- Luxury
- Minimal
- FastPaced

---

## Goals

Conhecimento específico para objetivos.

Exemplos:

Conversão

↓

priorizar benefício

↓

CTA forte

↓

produto cedo

---

Storytelling

↓

narrativa

↓

emoção

↓

continuidade

---

## Templates

Estruturas reutilizáveis.

Exemplo

Review

↓

Hook

↓

Problema

↓

Demonstração

↓

Resultado

↓

CTA

---

## Constraints

Restrições.

Exemplos

Texto máximo

Velocidade máxima

Número máximo de efeitos

Quantidade máxima de legendas

---

# 4. Knowledge Object

Toda informação armazenada segue o mesmo formato.

```yaml
id:

name:

category:

description:

version:

status:

priority:

createdAt:

updatedAt:
```

---

# 5. Editorial Rule

Estrutura.

```yaml
id:

CUT_SILENCE_001

condition:

Silêncio maior que 0.5 segundos

action:

CUT

goal:

Conversation

priority:

HIGH
```

---

# 6. Heuristic

Estrutura.

```yaml
id:

HOOK_FIRST_SECONDS

description:

Mostrar informação importante nos primeiros segundos.

confidence:

0.92
```

---

# 7. Style

Cada estilo define características.

Exemplo

UGC

```yaml
camera:

Natural

captions:

Bold

speed:

Medium

effects:

Minimal
```

---

# 8. Goal

Cada objetivo altera prioridades.

Exemplo

Conversion

Prioridades

- clareza
- produto
- benefício
- CTA

---

Storytelling

Prioridades

- narrativa
- emoção
- continuidade

---

# 9. Rule Resolution

Quando duas regras entram em conflito.

Ordem:

Priority

↓

Specificity

↓

Version

↓

Confidence

---

# 10. Versioning

Toda regra possui versão.

Formato

Major.Minor.Patch

Exemplo

1.0.0

1.1.0

2.0.0

---

# 11. Status

Toda regra possui estado.

Valores

Draft

Approved

Deprecated

Archived

---

# 12. Search

O Decision Engine nunca percorre regras manualmente.

Ele consulta o Knowledge Engine através de filtros.

Exemplo

Goal

↓

Conversion

↓

Style

↓

UGC

↓

VideoContext

↓

Regras retornadas

---

# 13. Retrieval

Toda busca retorna:

- regras
- heurísticas
- templates
- estilos
- restrições

Ordenados por prioridade.

---

# 14. Knowledge Layers

Layer 1

Global

Conhecimento válido para qualquer vídeo.

---

Layer 2

Goal

Conhecimento específico do objetivo.

---

Layer 3

Style

Conhecimento específico do estilo.

---

Layer 4

Context

Conhecimento específico do vídeo atual.

---

# 15. Validation

Nenhuma regra pode ser utilizada se:

- estiver arquivada
- estiver inválida
- possuir versão incompatível

---

# 16. Extensibility

Novas categorias podem ser adicionadas.

Exemplo

Platform Profiles

Audience Profiles

Brand Rules

Language Rules

Sem alterar o restante da arquitetura.

---

# 17. Future

No futuro o Knowledge Engine poderá incluir:

- pesquisa automática
- aprendizado contínuo
- conhecimento gerado por especialistas
- conhecimento gerado por IA
- marketplace de regras

---

# 18. Non Responsibilities

O Knowledge Engine nunca deve:

✗ editar vídeos

✗ gerar EEL

✗ renderizar

✗ decidir

✗ aprender sozinho

Aprendizado pertence ao Learning Engine.

---

# 19. Golden Rule

O Decision Engine nunca inventa conhecimento.

Ele apenas consulta, interpreta e aplica o conhecimento armazenado no Knowledge Engine.