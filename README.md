# RECON-AI 🤖

**RECON-AI** é um pipeline de reconhecimento automatizado totalmente adaptado e nativo para o **Windows**. Ele orquestra as melhores ferramentas de Web Pentest e fornece uma triagem inteligente via Inteligência Artificial, descartando falsos positivos direto no seu PowerShell ou CMD.

---

## 🚀 Principais Características

| Característica | Descrição |
|----------------|-----------|
| **Nativo no Windows** | Usa caminhos e codificações (`UTF-8`) otimizados para o sistema |
| **Setup Mágico** | Baixa os `.exe` do Subfinder, Nuclei, Httpx e injeta no PATH sozinho |
| **Triagem Cognitiva** | Usa IA para ler logs confusos e apontar falhas reais |
| **Evasão de WAF** | Usa `psutil` para suspender as threads ao detectar HTTP 429 |
| **Multi-Modelos** | Suporte integrado para Gemini, OpenAI e DeepSeek |

---

## 📦 Instalação e Setup

O RECON-AI de Windows é inteligente: ele resolve as próprias dependências. O único requisito manual é ter o Python e o motor do Golang instalados na máquina.

**Pré-Requisitos:**
1. Instale o [Python 3](https://www.python.org/downloads/) (marque a caixa *Add Python to PATH* na instalação)
2. Instale o [Golang](https://go.dev/dl/) (baixe o arquivo `.msi` e clique em *Next* até o fim)

Abra o seu **PowerShell** ou **CMD** e rode os comandos abaixo:

```powershell
# 1. Baixar o repositório
git clone https://github.com/Hvxyznn/recon-ai-win.git
cd recon-ai-win

# 2. Rodar a Instalação Automática (o script fará o resto!)
python recon-ai-win.py --setup
```

---

## 🔧 Configuração das APIs

Antes de procurar os bugs, você precisa adicionar a chave da Inteligência Artificial que vai fazer o trabalho de leitura dos logs.

```powershell
# Adicionar chave do Google Gemini (Recomendado)
python recon-ai-win.py --set-api gemini SUA_CHAVE_AQUI

# Adicionar chave da OpenAI
python recon-ai-win.py --set-api openai SUA_CHAVE_AQUI

# Adicionar chave do DeepSeek
python recon-ai-win.py --set-api deepseek SUA_CHAVE_AQUI
```

---

## 💬 Exemplo Rápido de Uso

Basta passar o site do programa de Bug Bounty e escolher o cérebro (IA) que vai gerar o relatório final:

```powershell
# Iniciar pipeline contra o alvo
python recon-ai-win.py --target example.com --ai gemini
```

A ferramenta roda sozinha e, no final, cospe o relatório direto no seu terminal:

**Resposta:**

```
============================================================
             RELATÓRIO EXECUTIVO E TRIAGEM (TERMINAL)
============================================================
[ALVO & TIPO]
https://api.example.com/v1 - Parameter Pollution / Fuzzing Alert (High)

[IMPACTO REAL]
Possível extração de dados via parâmetros ocultos não filtrados.

[VALIDAÇÃO MANUAL RÁPIDA]
Faça um GET passando o parâmetro descoberto pelo Arjun:
curl "https://api.example.com/v1?admin=true"
============================================================
```

---

## 🎯 Para que Serve?

- ✅ **Bug Bounty**: Escale seus hunts de forma automatizada no Windows
- ✅ **Web Pentest**: Pare de configurar VMs Linux só para fazer reconhecimento
- ✅ **Análise de Logs**: A IA lê os JSONs gerados e mastiga a vulnerabilidade para você

---

## 🔥 Diferenciais

| RECON-AI (Windows) | Alternativas |
|----------------------|---------------|
| **Roda nativo no Windows** | Exige WSL ou VM Linux |
| **Setup automático (.exe)** | Compilação manual de binários Go |
| **Triagem via IA** | Triagem manual |
| **Evasão de WAF (`psutil`)** | Sem evasão de WAF |
| **Totalmente grátis** | Custo variável |

---

## 📊 Ecossistema de Ferramentas

| Categoria | Ferramentas Integradas |
|-----------|--------------------------|
| **Reconhecimento** | Subfinder, Assetfinder, Httpx |
| **Crawling & Endpoints** | Katana, GAU (GetAllUrls) |
| **Parameter Fuzzing** | Arjun |
| **Scanning Ativo** | Nuclei, Dalfox |

*Todos baixados como binários `.exe` nativos durante o `--setup`.*

---

## 🛠️ Comandos Úteis

```powershell
# Refazer a instalação/atualização das ferramentas
python recon-ai-win.py --setup

# Ver o painel de ajuda e comandos
python recon-ai-win.py -h
```

---

## ⚖️ Uso Responsável

O RECON-AI foi criado para acelerar o reconhecimento em **alvos autorizados** — programas de Bug Bounty, contratos de pentest ou laboratórios próprios. O uso contra sistemas sem autorização é de responsabilidade exclusiva de quem executa a ferramenta.

---

## 📝 Resumo

> **RECON-AI (Win)** = Enumeração Massiva → Sondagem Web → Fuzzing → Scanning → Triagem com IA → Relatório Limpo no PowerShell

Desenvolvido por [**Hvx**](https://github.com/Hvxyznn). Automação pesada e sem dor de cabeça no Windows! 🚀
