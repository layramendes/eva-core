# ADR-0001-FOUNDATION.md

**Document:** ADR-0001-FOUNDATION.md  
**Version:** 1.0.0  
**Status:** Accepted  
**Date:** 2026-06-29  
**Owner:** EVA Core Team

---

# ADR-0001

## Title

EVA será construída como um Sistema Cognitivo de Edição orientado por decisões, e não como um editor de vídeo tradicional.

---

# Status

Accepted

---

# Context

A maioria dos editores atuais funciona da seguinte forma:

Vídeo

↓

Timeline

↓

Usuário

↓

Renderização

Mesmo ferramentas com IA normalmente apenas automatizam partes da edição.

Elas não possuem um modelo cognitivo de tomada de decisão.

Nosso objetivo é construir um sistema que compreenda o vídeo antes de editá-lo.

---

# Decision

A EVA será composta por módulos independentes.

Cada módulo possui apenas uma responsabilidade.

A arquitetura será baseada em:

- Domain Driven Design
- Hexagonal Architecture
- Event Driven Pipeline
- Agent Architecture
- Modular Design

---

# Cognitive Pipeline

Upload

↓

Video Intelligence

↓

Audio Intelligence

↓

Knowledge Engine

↓

Decision Engine

↓

EEL

↓

Render Engine

↓

Learning Engine

↓

Export

---

# Core Decisions

## Decision 01

A EVA nunca editará vídeos diretamente.

Ela produzirá uma linguagem intermediária chamada EEL.

---

## Decision 02

O Render Engine nunca tomará decisões.

Ele apenas interpreta EEL.

---

## Decision 03

O Decision Engine nunca renderiza.

Sua única função é decidir.

---

## Decision 04

Todo conhecimento ficará centralizado no Knowledge Engine.

Nenhuma regra editorial ficará espalhada pelo código.

---

## Decision 05

Todo aprendizado ficará centralizado no Learning Engine.

O Learning Engine nunca altera conhecimento automaticamente.

---

## Decision 06

Nenhum módulo dependerá diretamente de Gemini, GPT, Claude ou qualquer outro modelo.

Todos os modelos implementarão uma interface comum.

---

## Decision 07

Toda decisão deve ser explicável.

Cada decisão obrigatoriamente possui:

- reason
- confidence
- agent
- rule
- ruleVersion
- timestamp

---

## Decision 08

Toda edição começa por um objetivo.

Nunca por uma plataforma.

Objetivos:

- Conversão
- Viralização
- Storytelling
- Educação
- Branding
- Review
- Tutorial
- Podcast
- Lifestyle

---

## Decision 09

A plataforma influencia apenas a exportação.

Nunca a estratégia editorial.

---

## Decision 10

Toda funcionalidade deve ser modular.

Nenhum módulo pode acessar implementações internas de outro módulo.

Comunicação apenas através de contratos públicos.

---

# Consequences

## Positivas

- Arquitetura desacoplada
- IA substituível
- Renderizador substituível
- Fácil manutenção
- Fácil evolução
- Auditoria completa
- Versionamento de decisões
- Preparada para modelos próprios

---

## Negativas

Maior complexidade inicial.

Maior investimento em arquitetura.

Maior quantidade de documentação.

Esses custos são aceitos para garantir escalabilidade.

---

# Alternatives Considered

## Editor tradicional

Rejeitado.

Motivo:

Não separa decisão de execução.

---

## Dependência direta de um único LLM

Rejeitado.

Motivo:

Cria acoplamento tecnológico.

---

## Regras embutidas no código

Rejeitado.

Motivo:

Dificulta manutenção.

---

## IA gerando comandos FFmpeg diretamente

Rejeitado.

Motivo:

Não cria tecnologia proprietária.

Não permite auditoria.

Não permite múltiplos renderizadores.

---

# Success Criteria

Esta ADR será considerada válida quando:

- qualquer modelo puder gerar EEL;
- qualquer renderizador puder interpretar EEL;
- qualquer regra puder ser alterada sem modificar o Decision Engine;
- qualquer componente puder ser substituído sem afetar os demais.

---

# Future ADRs

ADR-0002

Knowledge System

---

ADR-0003

Decision Engine

---

ADR-0004

Learning Engine

---

ADR-0005

EEL Versioning

---

ADR-0006

Model Registry

---

ADR-0007

Rendering Architecture

---

ADR-0008

Training Pipeline

---

# Conclusion

A EVA não será construída como um editor de vídeo.

Ela será construída como um sistema operacional de decisões editoriais.

Toda a plataforma será organizada em torno de um único princípio:

> **Compreender → Decidir → Representar → Executar → Aprender**

Este princípio nunca deverá ser violado por qualquer evolução futura da arquitetura.