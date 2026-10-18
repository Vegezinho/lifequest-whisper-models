# lifequest-whisper-models

Arquivos de modelo do **Whisper** (OpenAI) usados pelo app **LifeQuest TDAH**
para ditado por voz **100% local** — nenhum áudio ou texto sai do aparelho.

Este repositório serve apenas como **hospedagem dos modelos** para download sob
demanda pelo app. Os arquivos são os mesmos do repositório oficial
[`ggerganov/whisper.cpp`](https://huggingface.co/ggerganov/whisper.cpp), no formato
`ggml`, usados pelo [whisper.cpp](https://github.com/ggml-org/whisper.cpp).

> Usado pelo **LifeQuest TDAH** (`com.app.tdah`) — ditado por voz 100% local.

## Modelos

| Arquivo | Modelo | Tamanho | SHA-256 |
|---|---|---|---|
| `ggml-base.bin` | Whisper **base** (multilingue, PT-BR) | 147.951.465 bytes ≈ 148 MB | `60ed5bc3dd14eea856493d334349b405782ddcaf0028d4b5df4088345fba2efe` |

> O modelo precisa ser **multilingue** (sem sufixo `.en`) para transcrever português.

## Download

Link estável usado pelo app (sempre a última release):

```
https://github.com/Vegezinho/lifequest-whisper-models/releases/latest/download/ggml-base.bin
```

Versão fixa:

```
https://github.com/Vegezinho/lifequest-whisper-models/releases/download/v1.0.0/ggml-base.bin
```

## Verificação de integridade

O app confere o SHA-256 após o download e só usa o arquivo se o hash bater.

```bash
sha256sum -c SHA256SUMS
```

## Como atualizar

1. Baixar o modelo desejado do [`ggerganov/whisper.cpp`](https://huggingface.co/ggerganov/whisper.cpp/tree/main).
2. `sha256sum ggml-*.bin` e atualizar `SHA256SUMS` e este `README.md`.
3. Criar uma nova release e anexar o arquivo como **Release Asset**.
4. Atualizar a URL e o hash fixados no código do app.

## Licença

O conteúdo deste repositório (documentação, scripts e metadados) é licenciado
sob MIT — ver [`LICENSE`](LICENSE).

Os arquivos de modelo `ggml-*.bin` são de terceiros e mantêm sua licença
original:

Modelos Whisper: [MIT](https://github.com/openai/whisper/blob/main/LICENSE) (OpenAI).
Formato `ggml` e ferramentas de conversão: [MIT](https://github.com/ggml-org/whisper.cpp/blob/master/LICENSE).
