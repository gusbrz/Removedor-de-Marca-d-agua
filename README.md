# Watermark Remover AI - Ferramenta de Remoção de Marca D'água em Vídeos

## Sobre o projeto

O **Watermark Remover AI** é uma aplicação desktop desenvolvida em Python para processamento de vídeos, permitindo ao usuário selecionar uma região contendo uma marca d'água e realizar a reconstrução inteligente dessa área utilizando técnicas de processamento de imagem e inteligência artificial.

A ferramenta possui uma interface gráfica intuitiva, permitindo carregar vídeos, selecionar visualmente a área desejada e gerar uma nova versão do vídeo processado.

---

# Funcionalidades

## Importação de vídeos

Permite carregar arquivos de vídeo diretamente na aplicação.

Formatos suportados:

- MP4
- AVI
- MOV
- MKV
- Outros formatos compatíveis com FFmpeg

---

## Visualização do vídeo

A aplicação possui um player integrado com:

- Reprodução do vídeo
- Pausar
- Avançar frames
- Retroceder frames
- Controle de progresso

Isso permite encontrar exatamente o momento ideal para selecionar a região.

---

## Seleção inteligente da área

O usuário pode:

- Desenhar uma área usando o mouse
- Selecionar exatamente onde está a marca d'água
- Visualizar a máscara criada
- Refazer a seleção quando necessário

A seleção será aplicada em todos os frames do vídeo.

---

# Processamento com Inteligência Artificial

O sistema utiliza técnicas de **Image Inpainting**, onde a área selecionada é reconstruída analisando os pixels próximos.

O processamento pode utilizar:

- OpenCV Inpainting
- Modelos avançados de IA como LaMa Inpainting
- Processamento acelerado por GPU (quando disponível)

O objetivo é reconstruir a região removida mantendo a aparência natural do vídeo.

---

# Fluxo de utilização

## 1. Abrir o aplicativo

Execute:


python main.py


---

## 2. Carregar vídeo

Clique em:


Abrir vídeo


Escolha o arquivo desejado.

---

## 3. Encontrar a marca d'água

Utilize o player para localizar o frame onde a marca aparece.

---

## 4. Selecionar área

Com o mouse:

- Clique e arraste sobre a marca d'água
- Confirme a seleção

---

## 5. Criar máscara

Clique:


Criar Máscara


A aplicação transforma a seleção em uma área que será reconstruída.

---

## 6. Processar vídeo

Clique:


Processar Vídeo


O sistema irá:

- Extrair os frames
- Aplicar a máscara
- Reconstruir a região
- Recriar o vídeo final
- Preservar áudio e qualidade original

---

## 7. Exportar resultado

O vídeo final será salvo na pasta configurada.

---

# Arquitetura do projeto


watermark_remover/

│
├── main.py

├── ui/
│ ├── main_window.py
│ └── styles.py

├── video/
│ ├── processor.py
│ ├── extractor.py
│ └── exporter.py

├── ai/
│ ├── inpainting.py
│ └── model_loader.py

├── utils/
│ ├── logger.py
│ └── config.py

├── requirements.txt

└── README.md


---

# Tecnologias utilizadas

## Linguagem

Python 3.11+

---

## Interface

- PyQt6 / PySide6

---

## Vídeo

- OpenCV
- FFmpeg

---

## Imagem

- NumPy
- Pillow

---

## Inteligência Artificial

- LaMa Inpainting
- PyTorch
- Modelos de reconstrução de imagem

---

# Instalação

## 1. Criar ambiente virtual


python -m venv venv


Ativar:

Windows:


venv\Scripts\activate


Linux/Mac:


source venv/bin/activate


---

## 2. Instalar dependências


pip install -r requirements.txt


---

## 3. Instalar FFmpeg

O FFmpeg precisa estar instalado no sistema.

Verifique:


ffmpeg -version


---

# Configuração

Arquivo:


utils/config.py


Permite configurar:

- Pasta de saída
- Qualidade do vídeo
- Uso de GPU
- Caminho do modelo IA
- Configurações de processamento

Exemplo:

```python
USE_GPU = True

OUTPUT_FOLDER = "outputs"

QUALITY = "high"
