# Delatoris Signatori

> *"Verba celata revelantur" - As palavras ocultas são reveladas*

## Limpador & Detector de Marcadores de IA em Go

**Delatoris Signatori** é uma ferramenta em Go que detecta e remove marcadores invisíveis, watermarking estatístico e fingerprinting inseridos por sistemas de IA generativa em textos.

![GitHub stars](https://img.shields.io/github/stars/had-nu/Delatoris-Signatori?style=social)
![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Go Version](https://img.shields.io/badge/go-%3E%3D%201.16-blue)

## Principais funcionalidades

- **Detecção de caracteres invisíveis** - Identifica caracteres Unicode ocultos (U+200B, etc.)
- **Análise de watermarking estatístico** - Detecta padrões não naturais de distribuição de texto
- **Identificação de fingerprinting** - Reconhece assinaturas estilísticas de diferentes IAs
- **Remoção de metadados ocultos** - Limpa hashing e codificações secretas
- **Identificação da ferramenta de origem** - Determina qual IA provavelmente gerou o texto
- **Limpeza completa** - Remove todos os marcadores para obter texto puro

## Instalação

```bash
# Clonar o repositório
git clone https://github.com/had-nu/Delatoris-Signatori.git

# Entrar no diretório
cd Delatoris-Signatori

# Compilar
go build -o delatoris main.go
```

## Como usar

### Análise básica:
```bash
./delatoris -input texto_ia.txt -output texto_limpo.txt
```

### Apenas detecção (sem limpar):
```bash
./delatoris -input texto_ia.txt -detect-only -verbose
```

### Entrada pelo terminal:
```bash
./delatoris
# Cole seu texto e pressione Ctrl+D quando terminar
```

## Opções

| Opção | Descrição |
|-------|-----------|
| `-input` | Arquivo de texto para analisar |
| `-output` | Arquivo de saída para texto limpo |
| `-detect-only` | Apenas detectar, sem limpar o texto |
| `-verbose` | Exibir informações detalhadas |

## Exemplo de saída

```
=== Resultados da Análise ===
- Caracteres invisíveis detectados: 17
- Provável ferramenta de IA: ChatGPT (confiança: 87.5%)

=== Detalhes da Análise ===
Pontuações por ferramenta:
- ChatGPT: 0.87
- Claude: 0.64
- Bard: 0.52
- LLaMA: 0.45
- GPT-4: 0.72

Características estatísticas:
- pontuacao_ratio: 0.11
- diversidade_vocabulario: 0.68
- sequencias_espacos: 3.00

Marcadores encontrados:
- watermark_estatistico: Detectado
- padrao_unicode_oculto: Detectado
```

## Como funciona

A ferramenta utiliza várias técnicas para detectar e remover marcadores:

1. **Análise de caracteres Unicode** - Identifica sequências de caracteres invisíveis
2. **Análise estatística** - Examina distribuições e padrões não naturais no texto
3. **Identificação de padrões específicos** - Reconhece fingerprints de diferentes IAs
4. **Normalização de texto** - Remove anomalias e restaura o texto ao seu estado natural

## Licença

Este projeto está licenciado sob a Licença MIT - veja o arquivo LICENSE para detalhes.

## Contribuição

Contribuições são bem-vindas! Sinta-se à vontade para abrir um issue ou enviar um pull request.

---

*Delatoris Signatori* foi criado para fins educacionais e de pesquisa. Use com responsabilidade.
