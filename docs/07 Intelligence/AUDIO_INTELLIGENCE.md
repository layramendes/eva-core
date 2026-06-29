# AUDIO_INTELLIGENCE.md

**Document:** AUDIO_INTELLIGENCE.md  
**Version:** 1.0.0  
**Status:** Approved  
**Owner:** EVA Core Team  
**Last Updated:** 2026-06-29

---

# 1. Purpose

O Audio Intelligence é responsável por compreender todo o conteúdo sonoro de um vídeo.

Ele nunca toma decisões editoriais.

Ele nunca gera EEL.

Ele apenas transforma áudio em contexto estruturado.

---

# 2. Mission

Converter áudio em informações compreensíveis para o Decision Engine.

---

# 3. Responsibilities

O Audio Intelligence deve:

- transcrever fala
- identificar locutores
- detectar silêncio
- detectar pausas
- detectar respiração
- medir energia
- detectar emoções
- medir velocidade da fala
- detectar ruídos
- detectar música
- detectar efeitos sonoros
- produzir um AudioContext

---

# 4. Inputs

Recebe:

- áudio extraído do vídeo
- metadados
- configurações do projeto

---

# 5. Outputs

Produz apenas:

```text
AudioContext
```

Nenhum módulo acessa o áudio diretamente.

Todos utilizam o AudioContext.

---

# 6. AudioContext

Estrutura principal.

```yaml
audioId:

duration:

sampleRate:

channels:

transcript:

speakers:

segments:

silences:

breaths:

noise:

music:

sfx:

emotion:

energy:

speechRate:
```

---

# 7. Speech Recognition

Toda fala é convertida para texto.

Cada segmento contém:

```yaml
text:

start:

end:

confidence:
```

---

# 8. Speaker Diarization

Identifica quem está falando.

Cada locutor possui:

```yaml
speakerId:

segments:

totalSpeakingTime:
```

---

# 9. Silence Detection

Detecta períodos sem fala.

Cada silêncio possui:

```yaml
start:

end:

duration:
```

---

# 10. Pause Detection

Nem toda pausa é silêncio.

Pausas narrativas também são identificadas.

```yaml
start:

end:

duration:

type:
```

Tipos:

- Natural
- Dramática
- Hesitação
- Respiração

---

# 11. Breath Detection

Detecta respirações audíveis.

Cada ocorrência possui:

```yaml
start:

end:

intensity:
```

---

# 12. Emotion Detection

Detecta emoções na voz.

Exemplos:

- felicidade
- entusiasmo
- surpresa
- tristeza
- medo
- raiva
- neutralidade

Cada emoção possui:

```yaml
emotion:

confidence:
```

---

# 13. Energy Analysis

Calcula energia da voz.

Escala

0

↓

100

---

# 14. Speech Rate

Calcula velocidade da fala.

Exemplo

```yaml
wordsPerMinute:

classification:
```

Classificações:

- Muito lenta
- Lenta
- Normal
- Rápida
- Muito rápida

---

# 15. Noise Detection

Detecta:

- vento
- trânsito
- televisão
- música ambiente
- pessoas
- animais
- eco

Cada ruído possui:

```yaml
type:

intensity:

confidence:
```

---

# 16. Music Detection

Detecta música existente.

Identifica:

- início
- fim
- intensidade
- predominância

---

# 17. Sound Effects

Detecta efeitos sonoros.

Exemplos:

- aplausos
- risadas
- batidas
- explosões
- cliques

---

# 18. Timeline

Todos os eventos são registrados.

Exemplo

```yaml
00:02

Início da fala

00:04

Respiração

00:08

Silêncio

00:09

Música aumenta

00:14

Nova emoção
```

---

# 19. Importance Score

Cada evento recebe importância.

Escala

0

↓

100

---

# 20. Confidence

Toda análise possui confiança.

Escala

0.00

↓

1.00

---

# 21. Explainability

Toda informação deve responder:

Como foi detectada?

Qual modelo detectou?

Qual confiança?

Quando ocorreu?

---

# 22. Agent Architecture

O Audio Intelligence pode utilizar diversos agentes.

Exemplos:

SpeechAgent

TranscriptAgent

SilenceAgent

BreathAgent

EmotionAgent

SpeakerAgent

NoiseAgent

MusicAgent

SFXAgent

EnergyAgent

---

# 23. Extensibility

Novos agentes podem ser adicionados sem alterar os existentes.

---

# 24. Non Responsibilities

O Audio Intelligence nunca deve:

✗ cortar áudio

✗ remover silêncio

✗ alterar volume

✗ escolher música

✗ criar legendas

✗ gerar EEL

✗ renderizar

✗ tomar decisões

---

# 25. Golden Rule

O Audio Intelligence não interpreta.

Ele observa.

Toda interpretação pertence ao Decision Engine.