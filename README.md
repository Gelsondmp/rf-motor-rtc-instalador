# Instalador do RTC para Windows

O RTC simula a Reforma Tributária do Consumo (CBS, IBS e Imposto Seletivo) sobre os dados fiscais da empresa, usando as calculadoras oficiais da Receita Federal. Tudo roda no próprio computador. **O sistema não emite, não assina e não transmite documento fiscal.**

Este repositório só distribui o instalador. O código-fonte não fica aqui.

---

## ⚠️ Leia antes de baixar: dois avisos do Windows são esperados

O instalador é gratuito e não tem assinatura digital paga. Por isso o navegador e o Windows mostram avisos na primeira vez. **Eles são esperados e não indicam problema.**

**1. No navegador (Edge ou Chrome), ao baixar**

Pode aparecer *"Instalador-RTC-….exe não é baixado com frequência"*.
Clique nos **três pontinhos (…)** ao lado do arquivo → **Manter** → **Mostrar mais** → **Manter mesmo assim**.

**2. No Windows, ao abrir o instalador**

Aparece uma tela azul: *"O Windows protegeu o computador"*.

1. Clique em **Mais informações** (texto pequeno, logo abaixo da mensagem).
2. Clique no botão **Executar assim mesmo**, que só aparece depois do passo 1.

Depois disso, o Windows pede permissão de administrador (**Sim**) e o assistente de instalação abre.

> Para conferir que o arquivo é o original, compare o código SHA-256 publicado na página da versão com o do arquivo baixado. No PowerShell:
> `Get-FileHash .\Instalador-RTC-<versão>.exe`

---

## Baixar

👉 **[Baixar a versão mais recente](https://github.com/Gelsondmp/rf-motor-rtc-instalador/releases/latest)**: na página da versão, baixe **só** o arquivo `Instalador-RTC-<versão>.exe`. Os outros arquivos são componentes que o próprio instalador baixa e confere.

Sem acesso ao GitHub na empresa? Peça à consultoria a **variante offline** (`RTC-offline-<versão>.zip`): descompacte e abra o instalador de dentro da pasta, sem baixar mais nada.

## Antes de instalar

| | |
| --- | --- |
| Sistema | Windows 10 (22H2) ou Windows 11, 64 bits |
| Memória | 16 GB (mínimo 8 GB) |
| Disco | 40 GB livres |
| Internet | Durante a instalação (o instalador baixa os componentes da versão) |
| Usuário | Entre no Windows com o usuário que vai usar o RTC; ele precisa ser administrador do computador |
| Licença | Arquivo de licença (`.lic`) enviado pela consultoria que fornece o sistema |

Não é preciso instalar nada antes. O instalador prepara o que falta sozinho. Sem a licença, o sistema abre só para consulta.

## O que o instalador faz

1. Confere o computador (Windows, memória, disco, virtualização, porta e usuário) e diz o que fazer se algo faltar.
2. Ativa o subsistema Linux do Windows (WSL2), se ainda não estiver ativo. Se o Windows pedir para reiniciar, o instalador abre sozinho depois do reinício.
3. Baixa os componentes da versão, confere a integridade de cada um e instala.
4. Liga o sistema e abre a tela inicial no navegador.
5. Cria atalhos no menu Iniciar: **Abrir RTC**, **Parar RTC**, **Fazer backup**, **Atualizar RTC**, **Gerar diagnóstico** e **Manuais**.

Nenhum programa pago é instalado. Para atualizar, use o atalho **Atualizar RTC** (com backup antes). Para remover, use **Configurações → Aplicativos → RTC → Desinstalar**: um backup final é feito antes, e a pasta com backups, exportações e configuração é mantida.

## Problemas?

Use o atalho **Gerar diagnóstico** no menu Iniciar e envie o arquivo `.zip` gerado para a consultoria que forneceu o sistema. Ele não contém senhas, licença nem dados fiscais.

## Componentes de terceiros

O instalador usa somente componentes gratuitos: Inno Setup (assistente de instalação), WSL2 (Microsoft), Debian, Docker Engine (Apache 2.0), PostgreSQL e as calculadoras oficiais da Receita Federal. A lista completa, com as licenças, acompanha cada versão (`TERCEIROS.txt`).
