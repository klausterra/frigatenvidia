# Frigate (Exemplo Público) — NVidia + TensorRT + YOLOv9

Este repositório é um exemplo público e redigido para rodar o Frigate usando GPU NVidia.

## O que este exemplo faz

- Usa a imagem `ghcr.io/blakeblackshear/frigate:stable-tensorrt`.
- Usa detector `onnx`; na imagem `-tensorrt`, o Frigate usa TensorRT automaticamente quando possível.
- Aponta o `model.path` para um modelo YOLOv9 em formato ONNX (`/config/model_cache/yolov9-c-640.onnx`).

## Pré-requisitos

- Docker + Docker Compose
- Driver NVidia instalado e funcional (`nvidia-smi`)
- NVIDIA Container Toolkit

## Arquivos

- `docker-compose.yml`
- `config/config.yml`

## Como usar

1. Coloque o modelo em `config/model_cache/yolov9-c-640.onnx`.
2. Ajuste `mqtt.*` e as câmeras (`cameras.*.ffmpeg.inputs[].path`).
3. Troque os valores `CHANGE_ME`.
4. Suba o container:

```bash
docker compose up -d
```

## Segurança

Este repositório não inclui segredos. Não commite senhas RTSP, credenciais MQTT ou tokens.
