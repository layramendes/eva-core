# VIDEO_INTELLIGENCE.md

**Document:** VIDEO_INTELLIGENCE.md  
**Version:** 1.0.0  
**Status:** Approved  
**Owner:** EVA Core Team  
**Last Updated:** 2026-06-29

---

# 1. Purpose

O Video Intelligence é responsável por compreender o conteúdo visual de um vídeo.

Ele nunca toma decisões editoriais.

Ele nunca gera EEL.

Ele apenas transforma vídeo em conhecimento estruturado.

---

# 2. Mission

Converter imagens em contexto compreensível para o Decision Engine.

---

# 3. Responsibilities

O Video Intelligence deve:

- analisar quadros
- identificar cenas
- detectar objetos
- detectar pessoas
- detectar rostos
- identificar produtos
- analisar enquadramento
- detectar movimentos
- medir qualidade
- identificar emoções visuais
- produzir um VideoContext

---

# 4. Inputs

Recebe:

- vídeo bruto
- metadados
- configurações do projeto

---

# 5. Outputs

Produz apenas:

```text
VideoContext
```

Nenhum outro módulo pode acessar o vídeo diretamente.

Todos consomem o VideoContext.

---

# 6. VideoContext

Estrutura principal.

```yaml
videoId:

duration:

fps:

resolution:

orientation:

quality:

scenes:

objects:

faces:

people:

products:

camera:

composition:

motion:

lighting:

emotions:
```

---

# 7. Scene Detection

Cada vídeo é dividido em cenas.

Cada cena possui:

```yaml
id:

start:

end:

frames:

description:
```

---

# 8. Object Detection

Detecta objetos relevantes.

Exemplos

- celular
- roupa
- maquiagem
- cadeira
- notebook
- embalagem
- caixa
- copo
- cachorro
- gato

Cada objeto possui:

```yaml
name:

confidence:

boundingBox:

firstSeen:

lastSeen:
```

---

# 9. Product Detection

Produtos possuem prioridade.

Para cada produto:

```yaml
productVisible:

screenPercentage:

focus:

centered:

occluded:

rotation:
```

---

# 10. Face Detection

Para cada rosto:

```yaml
faceId:

confidence:

boundingBox:

lookingCamera:

visibility:

expression:
```

---

# 11. Emotion Detection

Emoções detectadas.

Exemplos:

- felicidade
- surpresa
- tristeza
- neutralidade
- entusiasmo
- dúvida

Cada emoção recebe:

```yaml
emotion:

confidence:
```

---

# 12. Camera Analysis

Detecta:

- zoom
- pan
- tilt
- shake
- movimento
- estabilidade

---

# 13. Composition

Analisa:

- regra dos terços
- centralização
- espaço negativo
- profundidade
- foco
- enquadramento

---

# 14. Motion Analysis

Detecta movimento de:

- câmera
- objetos
- pessoas
- produto

---

# 15. Lighting

Mede:

- brilho
- contraste
- temperatura
- exposição
- sombras

---

# 16. Quality

Calcula:

- resolução
- nitidez
- ruído
- compressão
- estabilidade

---

# 17. Timeline

Todos os eventos são registrados na timeline.

Exemplo

```yaml
00:02

Produto entrou

00:05

Pessoa sorriu

00:08

Produto saiu

00:12

Produto voltou
```

---

# 18. Importance Score

Cada evento recebe importância.

Escala

0

↓

100

---

# 19. Confidence

Toda análise possui confiança.

Escala

0.00

↓

1.00

---

# 20. Explainability

Toda informação deve responder:

Como foi detectada?

Qual modelo detectou?

Qual confiança?

Quando ocorreu?

---

# 21. Agent Architecture

O Video Intelligence pode utilizar múltiplos agentes.

Exemplos

SceneAgent

ObjectAgent

FaceAgent

ProductAgent

EmotionAgent

MotionAgent

LightingAgent

QualityAgent

---

# 22. Extensibility

Novos agentes podem ser adicionados sem alterar os existentes.

---

# 23. Non Responsibilities

O Video Intelligence nunca deve:

✗ cortar vídeo

✗ criar legendas

✗ escolher música

✗ aplicar zoom

✗ gerar EEL

✗ renderizar

✗ decidir

---

# 24. Golden Rule

O Video Intelligence não interpreta.

Ele observa.

Toda interpretação pertence ao Decision Engine.