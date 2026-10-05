# Thirium Link

[English](README.md) · **Português**

O Thirium Link é um app gratuito e pequeno para Windows que envia as informações do hardware do seu PC (CPU, placa de
vídeo, memória, disco, rede e temperaturas) para o wallpaper **Thirium OS (Detroit: Become Human)** do Wallpaper Engine.

Wallpapers não conseguem ler o hardware sozinhos. Sem o Thirium Link, todo o resto do Thirium OS funciona normalmente;
só o widget de hardware fica escondido.

## Baixar e instalar

1. Baixe o **`ThiriumLink.exe`** na [versão mais recente](https://github.com/Nanokaso/thirium-link/releases/latest).
2. Abra uma vez. Pronto: ele se instala, abre junto com o Windows e fica como um ícone perto do relógio.

> **Apareceu "O Windows protegeu o computador"?** O Windows mostra isso para apps sem certificado de assinatura pago.
> Clique em **Mais informações → Executar assim mesmo**. Dá para confirmar que o arquivo é o oficial pelo hash SHA-256
> (veja [Conferir o arquivo](#conferir-o-arquivo)).

Não precisa instalar .NET nem nada: tudo está dentro do .exe (cerca de 52 MB).

## Como usar

Clique no ícone perto do relógio:

| Opção | O que faz |
|-------|-----------|
| **Ativar temperatura da CPU...** | Opcional. Veja abaixo. |
| **Iniciar com o Windows** | Vem ligado. |
| **Ver dados** | Abre no navegador os dados que o Thirium Link está enviando. |
| **Desinstalar...** | Remove o Thirium Link. Também dá em Configurações → Aplicativos. |
| **Sair** | Fecha até a próxima vez que o Windows iniciar. |

### Temperatura da CPU (opcional)

O Windows só deixa ler a temperatura da CPU com um driver de kernel. O Thirium Link usa o **PawnIO**, um driver gratuito
e assinado (o mesmo do LibreHardwareMonitor). Ao escolher *Ativar temperatura da CPU*:

1. o Windows pede confirmação **uma vez**;
2. roda o instalador oficial do PawnIO (ele vai dentro do .exe; não precisa baixar nada);
3. a partir daí o Thirium Link abre como administrador junto com o Windows, sem pedir de novo.

Todo o resto (temperatura da placa de vídeo, uso, memória, disco, rede) funciona sem isso.

## É seguro?

- **Só no seu PC:** nada na sua rede ou na internet consegue se conectar a ele.
- **Só leitura:** não consegue mudar, executar ou apagar nada no seu PC.
- **Sem dados pessoais:** só compartilha números de hardware.

## Conferir o arquivo

Cada versão mostra o hash SHA-256 do `ThiriumLink.exe`. Para conferir o seu, abra o PowerShell na pasta do download e rode:

```powershell
Get-FileHash .\ThiriumLink.exe -Algorithm SHA256
```

O resultado tem que ser igual ao da versão. **Baixe o Thirium Link só por esta página.**

## Problemas?

- O widget de hardware não aparece: confira se o ícone do Thirium Link está perto do relógio. Se estiver, abra
  `http://127.0.0.1:4580/diagnostico` no navegador e mande o que aparecer junto com o relato do problema.
- Relate problemas em [Issues](https://github.com/Nanokaso/thirium-link/issues).
- Achou um problema de segurança? Por favor **não** abra uma issue pública; veja [SECURITY.md](SECURITY.md).

## Créditos

O Thirium Link usa o [LibreHardwareMonitor](https://github.com/LibreHardwareMonitor/LibreHardwareMonitor) e o driver
[PawnIO](https://pawnio.eu). Veja [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md).

Projeto feito por fã. Detroit: Become Human é marca da Quantic Dream. Sem ligação com a Quantic Dream ou o Wallpaper Engine.
