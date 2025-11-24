# Analisador de Reviews da Steam com IA (Gemini)

Este é um projeto prático para a disciplina de Processamento de Linguagem Natural (PLN). A ferramenta se conecta à API da Steam para buscar reviews de jogos, utiliza o **Google Gemini** (via LangChain) para realizar uma análise de texto detalhada e, em seguida, usa o modelo **TTS (Text-to-Speech) do Gemini** para gerar um áudio da review com base no sentimento detectado.

Disponível em:
https://colab.research.google.com/drive/1HfH4XTY8ubQlWI0DxkPu9-uo9sexCsZy#scrollTo=lmv3bsn6aA3v

## Funcionalidades Principais

* **Coleta de Dados Reais:** Busca reviews de qualquer jogo da Steam através da API pública.
* **Análise de Texto com Gemini:** Utiliza um prompt único e eficiente para extrair:
    * Uma breve análise da review.
    * Pontos positivos e negativos.
    * A classificação de sentimento (Positivo, Negativo ou Misto/Neutro).
* **Geração de Áudio Emocional:** Converte o texto da review em áudio usando o Gemini TTS, ajustando o tom da voz (ex: "animado", "desapontado") com base no sentimento analisado.
* **Seleção Aleatória:** Filtra reviews muito curtas e seleciona aleatoriamente uma review de qualidade para análise, garantindo um resultado novo a cada execução.
* **Saída Limpa:** Apresenta a análise de texto formatada em Markdown e um player de áudio diretamente no notebook.
* **Segurança:** Utiliza o Gerenciador de Secrets do Google Colab para proteger a chave de API.

## Tecnologias Utilizadas

* **Python**
* **Google Colab**
* **Google Gemini (LLM)** para análise de texto.
* **Google Gemini (TTS)** para geração de áudio.
* **LangChain** (Framework)
* **API da Steam** (Fonte dos dados)

## Como Executar o Projeto

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

Execute as células do notebook `PLN_Analise_Reviews_Steam.ipynb` na ordem.

---
*Este notebook foi desenvolvido como projeto prático para a disciplina de Processamento de Linguagem Natural.*
