# # Trabalho Prático 1: Pipeline Escalar e Superescalar

Este repositório contém os códigos-fonte, dados e scripts de automação referentes ao Trabalho Prático 1 da disciplina de **Arquitetura de Computadores III** da Pontifícia Universidade Católica de Minas Gerais (PUC Minas).

O objetivo deste projeto é analisar o Paralelismo a Nível de Instruções (ILP), identificando e mitigando *hazards* em pipelines escalares de 5 estágios e simulando (analítica e manualmente) arquiteturas superescalares com a aplicação do Algoritmo de Tomasulo e Renomeação de Registradores.

## 👥 Equipe
* Bárbara Maria Sampaio Portes
* Felipe Benfica
* Samir da Morim Cambraia

## 🛠️ Ferramentas Utilizadas
* **Simulador Escalar:** [RIPES v2.2.6](https://github.com/mortbopet/Ripes)
* **Linguagem:** Assembly RISC-V (RV32IM)
* **Automação de Dados:** Python 3 (Bibliotecas `pandas` e `matplotlib`)
* **Documentação:** LaTeX

## 📁 Estrutura do Repositório

* `/img/`: Contém as evidências visuais (capturas de tela) das simulações realizadas no RIPES.
* `/Gráficos/`: Diretório gerado automaticamente contendo os gráficos de CPI e Speedup.
* `Simulacao_RIPES_TP1.csv`: Tabela com os dados brutos (Ciclos, Instruções, CPI, IPC) extraídos do simulador.
* `graphs.py`: Script de automação para plotagem dos gráficos analíticos.
* `/Relatórios/``relatorio_final.tex`: Código-fonte em LaTeX do relatório técnico.
* `/Relatórios/``relatorio_final.pdf`: Versão final compilada do relatório.

## 🚀 Como Reproduzir os Resultados

### 1. Simulações no RIPES (Parte A)
1. Faça o download e abra o simulador **RIPES**.
2. Vá em `File > Load Program` e selecione um dos arquivos `.s` localizados na pasta `/src/`.
3. Vá em `Processor > Select Processor` e escolha o modelo de 5 estágios (com ou sem *Forwarding Unit*, conforme o teste desejado).
4. Clique no botão de *Reset* e em seguida no botão *Play/Run* para iniciar a simulação.
5. Os resultados de desempenho (Ciclos e CPI) estarão disponíveis na aba lateral **Execution info**.

### 2. Geração Automatizada de Gráficos
Para gerar os gráficos de análise a partir dos dados extraídos:

**Pré-requisitos:** Python 3.x instalado.

No terminal do Linux (ou WSL), crie um ambiente virtual e instale as dependências:
```bash
# Criação e ativação do ambiente virtual
python3 -m venv venv
source venv/bin/activate

# Instalação das bibliotecas
pip install pandas matplotlib
