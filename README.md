<h1 align="center">📊 Agregador de Dados para Declaração de Imposto de Renda</h1>

<p align="center">
  <b>Ferramenta 100% Excel</b> para organizar, validar e reunir num só lugar as informações que você vai precisar na hora de declarar o Imposto de Renda.
</p>

> 💡 O objetivo **não** é substituir o programa da Receita Federal — é ser o seu **painel de pré-organização**: você centraliza dados do titular, informes bancários e entradas mensais, com listas suspensas e validação para evitar erro de digitação e retrabalho.

---

## 📚 Sumário

- [Sobre o projeto](#-sobre-o-projeto)
- [Funcionalidades](#-funcionalidades)
- [Estrutura da planilha](#️-estrutura-da-planilha)
- [Recursos técnicos aplicados](#-recursos-técnicos-aplicados)
- [Fluxo de utilização](#-fluxo-de-utilização)
- [Como usar](#-como-usar)
- [Estrutura do repositório](#-estrutura-do-repositório)
- [Aprendizados](#-aprendizados)
- [Aviso de privacidade](#️-aviso-de-privacidade)
- [Autor](#-autor)

---

## 📖 Sobre o projeto

Este projeto foi desenvolvido como exercício prático de **organização e automação de dados no Excel**, aplicado a um cenário real: a preparação das informações exigidas na declaração de Imposto de Renda Pessoa Física (IRPF).

A planilha reúne, em abas separadas, os dados cadastrais do titular, os informes de rendimentos bancários e o extrato mensal de entradas (holerites, notas fiscais, freelas), com **validação automática de dados**, **totais calculados por fórmula** e **navegação simples entre seções**.

---

## 🚀 Funcionalidades

| | Funcionalidade |
|---|---|
| 👤 | Cadastro completo do titular (nome, CPF, nascimento, título de eleitor, cônjuge, endereço, contatos) |
| 🔽 | Listas suspensas (`SIM`/`NÃO`) para os campos de situação do titular, evitando digitação livre |
| 🏦 | Cadastro de até 3 bancos, com lista suspensa de **+50 instituições financeiras brasileiras** |
| 🧮 | **Total automático** dos rendimentos bancários via fórmula (`SOMA`) — recalcula sozinho |
| 📎 | Campo de referência ao anexo/comprovante de cada informe bancário |
| 📅 | Lançamento mês a mês das entradas, com categoria padronizada (`HOLERITE`, `CNPJ`, `FREELANCE`) |
| ✉️ | Link `mailto:` pronto no e-mail do titular, já com assunto preenchido, para abrir o cliente de e-mail em 1 clique |
| 🙈 | Aba de apoio **oculta** com a base de bancos, mantendo a planilha principal limpa |

---

## 🗂️ Estrutura da planilha

O arquivo `Projeto_completo.xlsx` tem 4 abas:

| Aba | Visibilidade | O que tem dentro |
|---|:---:|---|
| 👤 **TITULAR** | Visível | Seção *"1. Dados do Titular"* — dados cadastrais da pessoa física |
| 🏦 **INFORMES** | Visível | Seção *"2. Informes de Rendimentos Bancários"* — até 3 bancos, valor atual, anexo e total automático |
| 💰 **NOTAS** | Visível | Seção *"3. Notas Bancárias ou Extrato de Holerites"* — lançamentos mês a mês |
| 📋 **TABELAS** | 🙈 Oculta | Lista de bancos usada como fonte das listas suspensas |

<details>
<summary><b>🔎 Detalhar cada aba</b></summary>

<br>

**1. TITULAR** — Nome, CPF, Nascimento, Título de Eleitor, Cônjuge, Rua, Rua Abreviada, CEP, Telefone, Celular, E-mail (com link `mailto:`), Houve Alterações da Entrega Anterior, Dependente Cônjuge, Residente do Exterior.

**2. INFORMES** — Para cada banco (1º, 2º, 3º): campo **Banco** (lista suspensa ligada à aba `TABELAS`), **Valor Atual** e **Anexo** (nome do arquivo comprobatório). O campo **Total** soma automaticamente os três valores.

**3. NOTAS** — Tabela com colunas **Data**, **Categoria** (lista suspensa) e **Valor**, para registrar a receita mês a mês.

**4. TABELAS** — Lista de referência com os códigos e nomes dos principais bancos brasileiros (Banco do Brasil, Itaú, Bradesco, Nubank, Inter, C6 Bank, Santander, entre outros), usada como origem das listas suspensas de `INFORMES`. Fica oculta para não poluir a navegação do usuário final.

</details>

---

## 🛠️ Recursos técnicos aplicados

- ✅ **Validação de Dados (Data Validation)** do tipo lista, com mensagens de entrada e de erro personalizadas (ex.: *"Banco não encontrado" / "Informe um banco da lista"*);
- 🔗 **Referência entre abas** — as listas suspensas de `INFORMES` buscam valores direto da aba oculta `TABELAS` (`TABELAS!$A$2:$A$51`), separando dados de apresentação e de apoio;
- ➕ **Fórmulas nativas do Excel** (`SOMA`) para o total dos rendimentos — sem nenhum valor "chumbado", tudo recalcula sozinho;
- ✉️ **Hyperlink funcional** (`mailto:`) para contato rápido direto da planilha;
- 🙈 **Ocultação de abas** como técnica de organização e proteção dos dados de apoio.

---

## 🔄 Fluxo de utilização

```
👤 Dados do Titular  →  🏦 Informes Bancários  →  💰 Entradas Mensais  →  🧮 Totais automáticos
```

Depois de preencher as três primeiras etapas, os totais calculados servem de referência direta para o preenchimento no programa oficial da Receita Federal.

---

## ▶️ Como usar

1. Baixe o arquivo `Projeto_completo.xlsx` deste repositório e abra no Excel (no Google Sheets/LibreOffice Calc as listas suspensas podem ter pequenas diferenças de compatibilidade);
2. Na aba **TITULAR**, preencha seus dados pessoais;
3. Na aba **INFORMES**, selecione o banco na lista suspensa e informe o valor atual e o nome do arquivo do comprovante de cada instituição;
4. Na aba **NOTAS**, registre suas entradas mensais com data, categoria e valor;
5. Use os totais calculados automaticamente como apoio na hora de declarar.

---

## 📁 Estrutura do repositório

```
.
├── README.md
├── Projeto_completo.xlsx
└── images/
    └── (capturas de tela das abas do projeto)
```

---

## 📚 Aprendizados

- Aplicação prática de conceitos de organização de dados, validação e usabilidade dentro do Excel;
- Estruturação de uma planilha com múltiplas abas interligadas, separando entrada, cálculo e apoio;
- Documentação técnica clara de um processo/produto: estrutura de dados, decisões de design e instruções de uso.

---

## ⚠️ Aviso de privacidade

Os dados presentes no arquivo de exemplo (nome, CPF, valores) são **fictícios**, usados apenas para demonstração.

> 🔒 **Nunca suba para um repositório público uma planilha preenchida com seus dados reais** (CPF, endereço, valores bancários). Substitua sempre por um modelo em branco ou por dados fictícios antes de compartilhar.

---
