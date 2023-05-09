# Projeto OCR de Imagens com Pytesseract e OpenCV
Este projeto consiste em um script Python que utiliza as bibliotecas `Pytesseract` e `OpenCV` para realizar a leitura e processamento de texto em imagens. A ideia é buscar por um termo específico em todas as imagens de um determinado diretório, identificar as áreas de texto que contém esse termo e marcar essas áreas com uma caixa delimitadora.

## Instalação
Antes de começar a utilizar o script, é necessário instalar algumas dependências. Você pode instalar todas elas com os seguintes comandos:

```
!pip install pytesseract
!sudo apt install tesseract-ocr
!pip install opencv-python
```
Além disso, é preciso baixar os modelos de treinamento para o português e o inglês. No exemplo abaixo, estamos baixando esses modelos para a pasta tessdata:

```
!mkdir tessdata
!wget -O ./tessdata/por.traineddata https://github.com/tesseract-ocr/tessdata/raw/main/por.traineddata
!wget -O ./tessdata/eng.traineddata https://github.com/tesseract-ocr/tessdata/raw/main/eng.traineddata
```
# Uso
Para utilizar o script, basta seguir os seguintes passos:

Coloque as imagens que deseja processar na pasta `imagens` (você pode alterar o nome dessa pasta no script, caso prefira).
Abra o script e altere o termo de busca (variável termo_pesquisa) e a confiança mínima do OCR (variável confianca_minima), caso seja necessário.

### Execute o script.

O script irá processar todas as imagens da pasta imagens, buscar pelo termo definido na variável termo_pesquisa e marcar as áreas de texto que contêm esse termo. As imagens resultantes serão salvas na pasta imagens_busca. Além disso, o script irá exibir na tela o número de ocorrências do termo em cada imagem processada.

## Como funciona
O script utiliza a biblioteca OpenCV para carregar as imagens e a biblioteca Pytesseract para realizar o OCR e identificar as áreas de texto que contêm o termo de busca. Quando uma área de texto é identificada, o script utiliza a biblioteca PIL para desenhar uma caixa delimitadora em torno da área e escrever o texto encontrado. Por fim, a imagem resultante é salva na pasta imagens_busca.
