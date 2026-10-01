# 📊 Banco de Dados — Minicurso Preparatório de SQL

Este repositório contém o banco de dados em formato **SQLite** utilizado nas práticas do minicurso de SQL. A base reúne dados epidemiológicos de notificações de sífilis por município e ano, com uma estrutura simples ideal para o aprendizado de comandos de consulta (`SELECT`, `WHERE`, `GROUP BY`, `JOIN`, etc.).

---

## 🗂️ Estrutura das Tabelas

O arquivo do banco contém as seguintes tabelas:

* **`municipios`**: Cadastro dos municípios.
  * `codigo_municipio` (Chave Primária)
  * `municipio` (Nome do município)

* **`sifilis_notificacoes2`**: Notificações mensais de sífilis.
  * `ano`, `codigo_municipio`, colunas dos meses (`jan` a `dez`), `total`

* **`sifilis_idade`**: Distribuição dos casos por faixas etárias.
  * `codigo_municipio`, `ano`, `10-14`, `15-19`, `20-39`, `40-59`

* **`sifilis_clinica2`**: Classificação clínica das notificações.
  * `codigo_municipio`, `ano`, `primaria`, `secundaria`, `terciaria`, `latente`, `ign_branco`, `total`

---

## 🚀 Como Utilizar no Curso

Você pode utilizar o banco de dados tanto no **Google Colab** (ambiente utilizado na aula) quanto em softwares instalados no seu computador.

### Opção 1: No Google Colab (Recomendado para as Aulas)
1. Faça o download do arquivo do banco de dados (`.db` ou `.sqlite`) presente neste repositório.
2. Acesse o **[Google Colab](https://colab.research.google.com/)** e abra o *notebook* disponibilizado para a aula.
3. No painel esquerdo do Colab, clique no ícone de **pasta** 📁 (*Arquivos*) e selecione a opção de **fazer upload** 📤.
4. Envie o arquivo do banco de dados para o ambiente do Colab.
5. Siga os exercícios do *notebook* para conectar e consultar o banco via SQL!

## 1. Download do banco de dados direto do GitHub e instalação do suporte a SQL
* !wget -O sifilis_pb.db "https://raw.githubusercontent.com/vivianrodrigues-dev/Banco-de-Dados-Sifilis-PB/main/sifilis_pb.db"
* !pip install -q jupysql

## 2. Carregamento da extensão SQL e conexão com o SQLite
* %load_ext sql
* %config SqlMagic.autopandas = False
* %config SqlMagic.feedback = 0
* %sql sqlite:///sifilis_pb.db

---

### Opção 2: Em Programas Locais (Para Estudar e Praticar)
Caso deseje explorar o banco fora do ambiente do Colab, pode abri-lo em ferramentas como:
* **[DB Browser for SQLite](https://sqlitebrowser.org/)** (Interface gráfica simples)
* **DBeaver**
* Extensão **SQLite** no **VS Code**
