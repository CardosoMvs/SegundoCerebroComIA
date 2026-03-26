# 🧠 Telegram to Obsidian Bot (Make.com Automation)

Este repositório contém um Blueprint (arquivo JSON) para o [Make.com](https://www.make.com/) que transforma um Bot do Telegram em um assistente pessoal para o seu "Segundo Cérebro" no Obsidian.

A automação captura áudios, textos e fotos enviadas no Telegram, processa o conteúdo usando a inteligência artificial do Google Gemini (corrigindo gramática, resumindo e formatando em Markdown) e salva os arquivos diretamente em uma pasta do Google Drive sincronizada com o seu cofre do Obsidian.

---

## 🚀 Funcionalidades (3 Rotas)

O fluxo possui um roteador que lida com três tipos diferentes de entradas:

1. **🎙️ Áudio para Texto:** Recebe mensagens de voz ou áudio, transcreve e gera uma anotação estruturada.
2. **✍️ Texto Direto:** Recebe mensagens de texto soltas e as transforma em notas formatadas com Resumo (TL;DR), Tags e Próximos Passos.
3. **📸 Foto com Legenda:** Recebe imagens acompanhadas de texto, salva a imagem no Drive e gera uma nota em Markdown com o texto processado e o link interno para a imagem salva (`![[nome_da_imagem.jpg]]`).

---

## 🛠️ Pré-requisitos

Para reproduzir esta automação, você precisará de:

* Uma conta no **[Make.com](https://www.make.com/)** (o plano gratuito atende, mas verifique seu limite de operações).
* Um bot no **Telegram** (criado via [@BotFather](https://t.me/BotFather) para obter o Token de API).
* Uma conta do **Google** (para acessar o Google Drive e o Google AI Studio/Gemini).
* Uma pasta no **Google Drive** sincronizada com o seu cofre do Obsidian.

---

## ⚙️ Como Instalar e Configurar

### 1. Importando o Blueprint no Make
1. Baixe o arquivo `Integration Telegram Bot.blueprint.json` deste repositório.
2. Crie um novo cenário vazio no Make.
3. Clique nos três pontinhos (`...`) no menu inferior, selecione **Import Blueprint** e faça o upload do arquivo JSON baixado.

### 2. Configurando as Conexões
Após importar, você verá módulos com avisos solicitando configuração. Clique em cada um para vincular suas contas:
* **Telegram Bot (Módulos Azuis):** Clique em *Add* ou *Create a connection* e insira o Token fornecido pelo BotFather.
* **Google Gemini AI (Módulos Azuis Escuros):** Conecte sua conta do Google vinculada ao Google AI Studio. O modelo já configurado na automação é o `gemini-flash-lite-latest`.
* **Google Drive (Módulos Amarelos):** Conecte sua conta do Google e garanta que o Make tenha as permissões necessárias para ler e gravar arquivos no seu Drive.

### 3. Ajustando os Caminhos das Pastas (Importante!)
Você precisará alterar os módulos do **Google Drive (IDs 14, 23, 27 e 29)** para apontar para a sua própria pasta do Obsidian:
1. Abra cada módulo do Google Drive.
2. No campo **New Folder Location** (ou `folderId`), navegue até a pasta do seu Google Drive onde você deseja que as notas em `.md` e as imagens sejam salvas.

### 4. Ativando o Cenário
1. Salve o cenário clicando no ícone de disquete na barra de ferramentas inferior.
2. Ligue o cenário (mude a chave para **ON** no canto inferior esquerdo).
3. Envie uma mensagem de teste para o seu bot no Telegram para validar o funcionamento!

---

## 📝 Regras de Prompt (Personalização)

O prompt do Gemini já está configurado no blueprint com as seguintes regras de formatação:
* Criar um título curto na primeira linha.
* Gerar um resumo executivo (`> **TL;DR:**`).
* Formatar o texto com links bidirecionais do Obsidian (ex: `[[Conceito]]`).
* Extrair promessas ou decisões como tarefas (`- [ ]`).
* Inserir `#tags` no final.
* Manter um histórico da anotação original enviada.

Se desejar alterar o comportamento da IA, você pode modificar essas instruções abrindo os módulos do **Google Gemini AI** e editando o campo **System Instructions**.
