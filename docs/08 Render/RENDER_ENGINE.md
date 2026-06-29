# RENDER_ENGINE.md

**Document:** RENDER_ENGINE.md  
**Version:** 1.0.0  
**Status:** Approved  
**Owner:** EVA Core Team  
**Last Updated:** 2026-06-29

---

# 1. Purpose

O Render Engine é responsável por transformar um documento EEL em um vídeo final.

Ele nunca toma decisões editoriais.

Ele apenas interpreta instruções.

---

# 2. Mission

Executar fielmente todas as instruções presentes em um documento EEL.

O resultado deve ser determinístico.

---

# 3. Responsibilities

O Render Engine deve:

- interpretar EEL
- executar instruções
- renderizar vídeo
- gerar prévias
- gerar vídeo final
- gerar logs de execução
- validar compatibilidade

---

# 4. Non Responsibilities

O Render Engine nunca deve:

- decidir cortes
- escolher música
- criar legendas
- analisar vídeos
- alterar EEL
- criar regras
- modificar conhecimento

---

# 5. Inputs

Recebe:

- Video Original
- EELDocument
- Assets
- RenderProfile

---

# 6. Outputs

Produz:

- Preview
- Final Video
- Execution Report
- Render Metrics

---

# 7. Render Pipeline

Video Original

↓

Load Assets

↓

Validate EEL

↓

Build Timeline

↓

Execute Instructions

↓

Encode

↓

Validate Output

↓

Export

---

# 8. Supported Instructions

O Render Engine deve suportar:

Timeline

- CUT
- TRIM
- SPLIT
- MERGE

Camera

- ZOOM
- PAN
- REFRAME
- ROTATE
- CROP

Visual

- COLOR
- BLUR
- SHARPEN
- CONTRAST
- BRIGHTNESS
- SATURATION

Motion

- SPEED
- FREEZE
- STABILIZE

Audio

- MUSIC
- SFX
- VOICE
- VOLUME
- NORMALIZE
- MUTE

Text

- CAPTION
- TITLE
- SUBTITLE
- CTA

Composition

- IMAGE
- VIDEO
- OVERLAY

Transition

- CUT
- FADE
- DISSOLVE
- SLIDE

---

# 9. Validation

Antes da renderização o sistema deve validar:

- versão da EEL
- instruções inválidas
- assets existentes
- tempos válidos
- sobreposição de eventos
- conflitos

Se houver erro:

Abortar renderização.

---

# 10. Asset Manager

Todo asset recebe:

```yaml
id:

type:

path:

duration:

metadata:
```

Tipos

- vídeo
- imagem
- áudio
- fonte
- overlay
- animação

---

# 11. Timeline Builder

O Timeline Builder transforma a EEL em uma timeline executável.

Ele não interpreta decisões.

Ele apenas organiza.

---

# 12. Renderer Interface

Todo renderizador implementa:

```ts
interface Renderer {

render(

video,

eel,

profile

): Promise<RenderResult>

}
```

---

# 13. Render Profiles

Exemplos

Vertical 9:16

Horizontal 16:9

Square 1:1

4K

1080p

720p

Instagram

TikTok

YouTube

Custom

Perfis alteram apenas parâmetros técnicos.

Nunca alteram decisões editoriais.

---

# 14. Render Result

Toda renderização retorna:

```yaml
status:

duration:

frames:

output:

logs:

warnings:

errors:
```

---

# 15. Compatibility

Motores suportados.

FFmpeg

Remotion

Shotstack

Motores futuros

Todos interpretam a mesma EEL.

---

# 16. Preview Mode

O sistema deve permitir:

- preview parcial
- preview completo
- render final

Sem alterar a EEL.

---

# 17. Error Handling

Toda falha gera:

- código
- descrição
- instrução responsável
- stack
- timestamp

---

# 18. Performance Metrics

Toda renderização registra:

Tempo

CPU

GPU

RAM

Frames

FPS

Tempo de encoding

Tempo total

---

# 19. Determinism

Mesmo vídeo

+

Mesma EEL

+

Mesmo Render Profile

↓

Mesmo resultado.

Sempre.

---

# 20. Extensibility

Novos renderizadores podem ser adicionados.

Sem alterar:

Decision Engine

Knowledge Engine

Video Intelligence

Audio Intelligence

---

# 21. Future

O Render Engine deve permitir:

- render distribuído
- render em GPU
- render em nuvem
- render incremental
- render em tempo real

Sem alterar a arquitetura.

---

# 22. Golden Rule

O Render Engine nunca pensa.

Ele apenas executa exatamente o que está descrito na EEL.