# 🧠 Segundo Cérebro: Google Forms + Apps Script + Docs

Este repositório contém um script (Google Apps Script) para criar um fluxo de captura de notas e ideias utilizando ferramentas nativas do Google. 

[cite_start]É a solução ideal para quem quer começar com o mínimo de fricção possível[cite: 14]. Não precisa de Telegram, Make ou conta extra. [cite_start]Tudo dentro do ecossistema Google que você já usa [cite: 13][cite_start], operando a zero custo[cite: 7].

[cite_start]O fluxo é simples: **Preencha o formulário → Apps Script processa → nota estruturada no Google Docs**[cite: 3, 18, 48].

---

## 🚀 Como Funciona

1. [cite_start]**Captura:** Você preenche um Google Form com sua anotação em texto e, opcionalmente, anexa uma imagem[cite: 4, 5].
2. [cite_start]**Processamento:** O Google Apps Script é ativado automaticamente[cite: 6]. Ele envia seu texto bagunçado para a IA do Gemini.
3. **Estruturação:** O Gemini formata o texto extraindo o **Contexto**, **Decisão/Ideia Principal**, **Alternativas** e **Próximos Passos**.
4. [cite_start]**Armazenamento:** O script insere o texto formatado e a imagem enviada diretamente no final de um documento específico no Google Docs[cite: 11].
5. **Limpeza Automática:** Para não lotar o seu Google Drive, o script possui uma função "Caça-Fantasmas" que apaga automaticamente as imagens de upload do Drive após elas serem anexadas com sucesso ao Google Docs.

---

## 🛠️ Pré-requisitos

* Uma **Conta do Google** pessoal ou Workspace.
* Uma **Chave de API do Google Gemini** (gerada gratuitamente no [Google AI Studio](https://aistudio.google.com/)).
* Um **Documento no Google Docs** (em branco ou já existente) onde as notas serão acumuladas. Copie o ID deste documento (o código que fica na URL entre `/d/` e `/edit`).

---

## ⚙️ Passo a Passo de Instalação

### 1. Criar o Formulário
Crie um Google Forms simples com duas perguntas:
* [cite_start]**Pergunta 1 (Texto de parágrafo):** "NOTA"[cite: 24].
* [cite_start]**Pergunta 2 (Upload de arquivo):** "IMAGEM" (Permita envio de imagens)[cite: 26].

### 2. Vincular à Planilha
1. [cite_start]Na aba "Respostas" do formulário, clique em **"Vincular ao Planilhas"** para criar a base de dados[cite: 21].
2. [cite_start]Abra a planilha recém-criada[cite: 23].

### 3. Inserir o Script
1. [cite_start]Na planilha, vá no menu superior em **Extensões > Apps Script**[cite: 34, 41].
2. Apague o código que estiver lá e cole o script abaixo.
3. Substitua `COLE_SUA_CHAVE_API_AQUI` pela sua chave do Gemini.
4. Substitua `COLE_O_ID_DO_SEU_DOC_AQUI` pelo ID do seu Google Docs.
5. Salve o projeto (ícone de disquete).

### 4. Configurar o Acionador (Trigger)
Para que o script rode sozinho ao enviar o formulário:
1. No menu lateral esquerdo do Apps Script, clique no ícone de relógio (**Acionadores**).
2. Clique no botão azul **Adicionar Acionador** (canto inferior direito).
3. Configure assim:
   * Escolha a função que deve ser executada: `processarNovaNota`
   * Selecione a origem do evento: `Da planilha`
   * Selecione o tipo de evento: `Ao enviar o formulário`
4. Salve e autorize as permissões na sua conta Google (pode aparecer um aviso de segurança, clique em "Avançado" e depois em "Acessar").

---
