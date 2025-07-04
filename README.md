# patched-chromium

## Installation and Usage

### Download

| **Version**    | **Linux**                                                                                                                                                             |
| -------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Chrome 136** | [patched-chromium_136.tar.xz](https://drive.google.com/file/d/13EFi2tnJhYf8aJhMB3VC1sBQHCAx-A-u/view?usp=sharing)   |

---

### Enabling Fingerprint Features with Command Line Arguments

Comandos de personalização

| **Command Line Argument**                | **Descrição**                                                                          | **Exemplos**                                                             |
| ---------------------------------------- | -------------------------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| **`--fingerprint`**                      | Especifica o número aleatório base para fingerprint. Quando habilitado, a maioria dos recursos de fingerprinting são ativados | Número inteiro de 32 bits                                               |
| **`--fingerprint-platform`**             | Especifica o tipo de sistema operacional                                               | `windows`, `linux`, `macos`                                              |
| **`--fingerprint-platform-version`**     | Especifica a versão do sistema operacional                                             | Usa a versão padrão se não for especificada                              |
| **`--fingerprint-brand`**                | Especifica a marca do navegador no `User-Agent` e `User-Agent Data`                    | Chrome, Edge, Opera, Vivaldi (padrão é Chrome)                           |
| **`--fingerprint-brand-version`**        | Especifica o número da versão para a marca do navegador                                | Usa a versão padrão se não for especificada                              |
| **`--fingerprint-hardware-concurrency`** | Especifica o número de núcleos da CPU                                                  | Valor inteiro (gerado aleatoriamente a partir do número base de fingerprint se não fornecido) |
| **`--disable-non-proxied-udp`**          | Especifica a política WebRTC, por padrão as conexões UDP não-proxiadas estão desabilitadas | Recomendado manter a configuração padrão                                 |
| **`--lang`**                             | Define o idioma do navegador                                                           | Código de idioma (ex: `pt-BR`)                                           |
| **`--accept-lang`**                      | Define os idiomas aceitos pelo navegador                                               | Códigos de idioma (ex: `pt-BR,pt`)                                       |
| **`--timezone`**                         | Fuso horário                                                                           | Fuso horário (ex: `America/Sao_Paulo`, `UTC`)                            |
| **`--proxy-server`**                     | Servidor proxy                                                                         | Proxy `http`, `socks` (autenticação por senha não suportada)             |


## Exemplos de Uso

Aqui estão exemplos de linha de comando para vários casos de uso comuns:

### Uso Básico

#### Sempre criar um novo data-dir quando inicializar o browser, para garantir que será uma nova sessão.

```bash
./chrome --fingerprint=1000 --user-data-dir=/tmp/chromium/1000 --timezone="America/Sao_Paulo"  --fingerprint-platform=windows
```
