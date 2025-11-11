# Analisador de Reviews da Steam com IA (Gemini)

Este é um projeto prático para a disciplina de Processamento de Linguagem Natural (PLN). A ferramenta se conecta à API da Steam para buscar reviews de jogos, utiliza o **Google Gemini** (via LangChain) para realizar uma análise de texto detalhada e, em seguida, usa o modelo **TTS (Text-to-Speech) do Gemini** para gerar um áudio da review com base no sentimento detectado.

## ✨ Funcionalidades Principais

* **Coleta de Dados Reais:** Busca reviews de qualquer jogo da Steam através da API pública.
* **Análise de Texto com Gemini:** Utiliza um prompt único e eficiente para extrair:
    * Uma breve análise da review.
    * Pontos positivos e negativos.
    * A classificação de sentimento (Positivo, Negativo ou Misto/Neutro).
* **Geração de Áudio Emocional:** Converte o texto da review em áudio usando o Gemini TTS, ajustando o tom da voz (ex: "animado", "desapontado") com base no sentimento analisado.
* **Seleção Aleatória:** Filtra reviews muito curtas e seleciona aleatoriamente uma review de qualidade para análise, garantindo um resultado novo a cada execução.
* **Saída Limpa:** Apresenta a análise de texto formatada em Markdown e um player de áudio diretamente no notebook.
* **Segurança:** Utiliza o Gerenciador de Secrets do Google Colab para proteger a chave de API.

## 🛠️ Tecnologias Utilizadas

* **Python**
* **Google Colab**
* **Google Gemini (LLM)** para análise de texto.
* **Google Gemini (TTS)** para geração de áudio.
* **LangChain** (Framework)
* **API da Steam** (Fonte dos dados)

## 🚀 Como Executar o Projeto

Para executar este notebook, siga os passos abaixo:

### 1. Configurar a Chave de API

Este projeto requer uma chave de API do Google Gemini.

1.  Acesse o **[Google AI Studio](https://makersuite.google.com/app/apikey)** e gere sua chave de API.
2.  No Google Colab, clique no ícone de chave ( **🔑** ) na barra lateral esquerda para abrir o **Gerenciador de Secrets**.
3.  Crie um novo secret com o nome exato:
    ```
    GOOGLE_API_KEY
    ```
4.  Cole sua chave de API no campo `value` (valor).
5.  Ative o botão ao lado do nome para permitir o acesso do notebook.

### 2. Executar as Células

Execute as células do notebook `PLN_Analise_Reviews_Steam.ipynb` na ordem correta:

1.  **Células 1 a 6:** Execute-as em sequência. Elas instalarão as bibliotecas, configurarão a API e definirão as funções principais e o prompt do LangChain.
2.  **Célula 7 (IDs de Jogos):** Esta célula é um Markdown com uma lista de IDs de jogos que você pode usar para testar.
3.  **Célula 8 (Análise de Texto):**
    * Esta é a célula principal de análise.
    * Você pode alterar o `id_do_jogo` e o `min_comprimento_review` conforme desejar.
    * Ao executar, ela buscará 100 reviews, filtrará as curtas, selecionará uma aleatoriamente e exibirá a análise de texto formatada em Markdown.
4.  **Célula 9 (Lista de Vozes):** Esta célula é um Markdown com a lista de vozes disponíveis para o TTS.
5.  **Célula 10 (Geração de Áudio):**
    * Execute esta célula *após* a Célula 8.
    * Ela usará o texto e o sentimento da review analisada para gerar um arquivo `review_audio.wav`.
    * Um player de áudio aparecerá logo abaixo para você ouvir o resultado.

---
*Este notebook foi desenvolvido como projeto prático para a disciplina de Processamento de Linguagem Natural.*
