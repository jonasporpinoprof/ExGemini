### Instala ou atualiza a biblioteca google-generativeai para a versão mais recente disponível.
### Importa a biblioteca google-generativeai e a referência como genai.
### Importa a função userdata do Google Colab, que é usada para acessar dados do usuário.
```bash
!pip install -U google-generativeai
import google.generativeai as genai
from google.colab import userdata
```
### Configura a biblioteca google-generativeai para usar a chave da API recuperada.
### Itera sobre a lista de modelos disponíveis fornecidos pela biblioteca google-generativeai.

```bash
GOOGLE_API_KEY=userdata.get('GOOGLE_API_KEY')
genai.configure(api_key=GOOGLE_API_KEY)
```
### Verifica se o modelo suporta o método de geração de conteúdo.
### Imprime o nome dos modelos que suportam o método de geração de conteúdo.

```bash
for m in genai.list_models():
  if 'generateContent' in m.supported_generation_methods:
    print(m.name)
```

### model = genai.GenerativeModel('gemini-1.0-pro')
```bash
model = genai.GenerativeModel('gemini-1.0-pro')
```

### Usa o modelo selecionado para gerar conteúdo com base no prompt "Como tocar violão".
### Imprime a resposta gerada pelo modelo.
```bash
response = model.generate_content("Como tocar violão")
print("Resposta", response.text)
```
