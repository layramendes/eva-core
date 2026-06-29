# EEL_SPECIFICATION.md

**Document:** EEL_SPECIFICATION.md  
**Version:** 1.0.0  
**Status:** Draft  
**Owner:** EVA Core Team  
**Last Updated:** 2026-06-29

---

# 1. Purpose

A EVA Editing Language (EEL) é a linguagem proprietária da EVA.

Sua finalidade é representar decisões editoriais de forma estruturada, independente de qualquer motor de renderização.

A EEL não descreve como renderizar.

Ela descreve o que deve acontecer.

---

# 2. Principles

A EEL deve ser:

- legível
- determinística
- auditável
- versionável
- independente
- extensível

---

# 3. Pipeline

Video

↓

Analysis

↓

Decision Engine

↓

EEL

↓

Render Engine

---

# 4. Document Structure

Todo documento EEL possui:

```yaml
version:

documentId:

projectId:

videoId:

goal:

style:

createdAt:

generatedBy:

instructions:
```

---

# 5. Instruction Structure

Toda instrução possui:

```yaml
id:

type:

start:

end:

parameters:

reason:

confidence:

agent:

rule:

ruleVersion:

priority:
```

---

# 6. Instruction Types

## Timeline

- CUT
- TRIM
- SPLIT
- MERGE

---

## Camera

- ZOOM
- PAN
- ROTATE
- CROP
- REFRAME

---

## Visual

- COLOR
- BRIGHTNESS
- CONTRAST
- SATURATION
- SHARPEN
- BLUR
- VIGNETTE

---

## Motion

- SPEED
- SLOW
- FREEZE
- STABILIZE

---

## Text

- CAPTION
- SUBTITLE
- TITLE
- LABEL
- CTA

---

## Audio

- MUSIC
- SFX
- VOICE
- VOLUME
- MUTE
- DENOISE
- NORMALIZE

---

## Composition

- IMAGE
- VIDEO
- OVERLAY
- BACKGROUND

---

## Transition

- FADE
- CUT
- DISSOLVE
- SLIDE
- ZOOM_TRANSITION

---

# 7. Timeline

Toda instrução pertence a um intervalo.

```yaml
start:

end:
```

Ou

```yaml
time:
```

---

# 8. Parameters

Cada instrução possui parâmetros próprios.

Exemplo

```yaml
type: ZOOM

parameters:

 scale: 1.15

 easing: easeOut
```

---

# 9. Reason

Toda instrução possui motivo.

Exemplo

```yaml
reason:

Produto aparece pela primeira vez.
```

---

# 10. Confidence

Escala

0.00

↓

1.00

Exemplo

```yaml
confidence:

0.94
```

---

# 11. Agent

Toda decisão informa quem a criou.

Exemplo

```yaml
agent:

EmotionAgent
```

---

# 12. Rule

Toda decisão referencia uma regra.

```yaml
rule:

HOOK_003
```

---

# 13. Rule Version

```yaml
ruleVersion:

2.1
```

---

# 14. Priority

Valores

CRITICAL

HIGH

MEDIUM

LOW

---

# 15. Example

```yaml
version: 1.0

goal: Conversion

style: UGC

instructions:

- type: CUT

  start: 2.30

  end: 3.10

  reason: Silence

  confidence: 0.99

  agent: SilenceAgent

  rule: CUT_SILENCE_001

  ruleVersion: 1.0

  priority: HIGH

- type: ZOOM

  time: 5.20

  parameters:

    scale: 1.15

  reason: Emotional emphasis

  confidence: 0.96

  agent: EmotionAgent

  rule: ZOOM_EMOTION_004

  ruleVersion: 1.1

  priority: MEDIUM

- type: CAPTION

  start: 5.20

  end: 7.00

  parameters:

    text: "VOCÊ PRECISA VER ISSO"

    style: Bold

  reason: Highlight key message

  confidence: 0.97

  agent: CaptionAgent

  rule: CAPTION_SHORT_002

  ruleVersion: 1.0

  priority: HIGH
```

---

# 16. Validation

Um documento EEL é válido somente quando:

- possui versão
- possui objetivo
- possui pelo menos uma instrução
- todas as instruções possuem motivo
- todas possuem agente
- todas possuem regra
- todas possuem confiança

---

# 17. Compatibility

O Render Engine nunca altera um documento EEL.

Ele apenas interpreta.

Qualquer alteração gera uma nova versão.

---

# 18. Versioning

Formato

Major.Minor.Patch

Exemplo

1.0.0

1.1.0

2.0.0

---

# 19. Extensibility

Novas instruções podem ser adicionadas sem quebrar versões anteriores.

Todo renderizador deve ignorar instruções desconhecidas caso não sejam obrigatórias.

---

# 20. Golden Rule

A EEL não representa vídeo.

A EEL representa decisões editoriais.