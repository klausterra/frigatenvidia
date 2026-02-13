<<<<<<< HEAD
# Frigate + NVIDIA GPU Configuration

Configuração otimizada do Frigate NVR com aceleração por GPU NVIDIA usando TensorRT/ONNX.

## Hardware

- **GPU**: NVIDIA (testado com Quadro RTX 4000)
- **Detector**: ONNX com TensorRT automático
- **Modelo**: YOLOv7-640
- **Decodificação**: NVDEC via `preset-nvidia-h264`

## Funcionalidades Habilitadas

- ✅ Detecção de objetos (person, car) via GPU
- ✅ Gravação contínua com retenção por movimento
- ✅ Snapshots com bounding box
- ✅ Semantic Search
- ✅ Reconhecimento Facial (nativo)
- ✅ Leitura de Placas (LPR)
- ✅ Zonas de detecção customizadas
- ✅ Máscaras de movimento

## Arquivos

- `docker-compose.yml` — Container do Frigate com passthrough da GPU NVIDIA
- `config/config.yml` — Configuração principal do Frigate

## Como Usar

1. Clone este repositório
2. Ajuste as URLs RTSP das câmeras no `config/config.yml`
3. Ajuste as credenciais MQTT
4. Configure seu `PLUS_API_KEY` se tiver Frigate+
5. Baixe o modelo YOLOv7-640 ONNX e coloque em `config/model_cache/`
6. Execute: `docker compose up -d`

## Requisitos

- Docker + Docker Compose
- Driver NVIDIA >= 545
- NVIDIA Container Toolkit
- Câmeras com stream RTSP

## Notas

- Troque `YOUR_*` nos arquivos de configuração pelos seus valores reais
- As senhas e tokens foram removidos por segurança
=======
# Frigate (Exemplo Público) — NVidia + TensorRT + YOLOv9

Este repositório é um exemplo público e redigido para rodar o Frigate usando GPU NVidia.

## O que este exemplo faz

- Usa a imagem `ghcr.io/blakeblackshear/frigate:stable-tensorrt`.
- Usa detector `onnx`; na imagem `-tensorrt`, o Frigate usa TensorRT automaticamente quando possível.
- Aponta o `model.path` para um modelo YOLOv9 em formato ONNX (`/config/model_cache/yolov9-c-640.onnx`).

## Como usar

1. Coloque o modelo em `config/model_cache/yolov9-c-640.onnx`.
2. Ajuste `mqtt.*` e as câmeras (`cameras.*.ffmpeg.inputs[].path`).
3. Suba o container:

```bash
docker compose up -d
```

>>>>>>> 28a3c43 (Initial public example)
