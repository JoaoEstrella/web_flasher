# SALTE Web Flasher

Instalador web do firmware homologado para a **SALTE PCB v6.1**.

O manifesto grava somente as quatro imagens geradas pelo ESP-IDF nos offsets
declarados por `flasher_args.json`. Mantendo **Erase device** desmarcado, a
instalação não apaga a flash nem grava as partições `nvs` ou `esp_secure_cert`;
por isso preserva a configuração e as credenciais de uma placa já preparada.

Placas virgens devem passar pela ferramenta de fábrica antes de serem entregues.
Nenhuma credencial Security2 ou AWS pertence a este repositório público.

## Versão publicada

- Fonte: `JoaoEstrella/salte-proto`, branch `anatel`
- Commit: `0b37eb4`
- Hardware: PCB v6.1 / ESP32-S3 / flash 16 MB
- Perfil de rádio: ANATEL FHSS TX-only, 21 canais; faixa de 906 a 915,5 MHz excluída

## Conteúdo gravado

| Offset | Arquivo |
| ---: | --- |
| `0x00000` | `bootloader.bin` |
| `0x08000` | `partition-table.bin` |
| `0x0e000` | `ota-data-initial.bin` |
| `0x20000` | `salte-proto.bin` |
