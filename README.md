# patched-chromium

## Installation and Usage

### Download

| **Version**    | **Linux**                                                                                                                                                             |
| -------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Chrome 136** | [136.0.7103.113-1_linux.tar.xz](https://drive.google.com/file/d/1ae0IcbnG-8Sjm0Dz7sbqKeiVqoi1t_5M/view?usp=drive_link)   |
| **Chrome 135** | [135.0.7049.95-1_linux.tar.xz](https://drive.google.com/file/d/1vefFDpkouE6mQxkQSIHu_VNi5jg_2_7r/view?usp=drive_link)      |
| **Chrome 134** | [134.0.6998.165-1_linux.tar.xz](https://drive.google.com/file/d/1uXvPxFBcsINqGzTHjMfP27ADBYLb1luI/view?usp=sharing) |


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

### **Novos Argumentos de Linha de Comando para Personalização do User-Agent**

O Chrome 131 introduz dois novos argumentos de linha de comando para personalização avançada do `User-Agent` e `User-Agent Data`:

- **`--fingerprint-brand`**
  - Especifica a marca do navegador usada no `User-Agent` e `User-Agent Data`.
  - Valores suportados: `Chrome`, `Edge`, `Opera`, `Vivaldi`, ou nomes de marcas personalizados.

- **`--fingerprint-brand-version`**
  - Especifica o número da versão para a marca especificada.
  - Valores padrão: `Chrome`, `Edge`, `Opera`, `Vivaldi` todos fornecem versões padrão, versões personalizadas também podem ser passadas.

Estes argumentos aprimoram as capacidades de simulação de ambiente do navegador, adequados para automação e cenários de teste. Se `--fingerprint-brand` não for especificado, a marca padrão será usada.

## Exemplos de Uso

Aqui estão exemplos de linha de comando para vários casos de uso comuns:

### Uso Básico

```bash
./chrome --fingerprint=1000 --user-data-dir=/tmp/chromium/1000 --timezone="America/Sao_Paulo" --proxy-server="seu_endereco_de_servidor_proxy"
```

### Personalizando o User-Agent

```bash
chrome.exe --fingerprint=2023 --fingerprint-platform=macos --fingerprint-platform-version="15.2.0" --fingerprint-brand="Edge"  --user-data-dir=%TEMP%\chromium
```
