# Como gerar o APK - Rastreamento SESMA (motorista)

Esse projeto é a base do aplicativo Android do motorista, já preparado com o
plugin de localização em segundo plano (funciona com a tela apagada).

Como seu computador (Windows 7, 32 bits) não consegue rodar o Android Studio,
vamos compilar usando o GitHub Codespaces, que roda tudo na nuvem, direto no
navegador, sem precisar instalar nada no seu PC.

## Passo 1 - Subir esse projeto num repositório novo no GitHub

1. Cria um repositório novo no GitHub (pode ser com a mesma conta
   rastreamentotransporte2026-glitch), por exemplo chamado
   rastreamento-app-android
2. Sobe todos os arquivos dessa pasta pro repositório (arrasta tudo na tela
   de upload, igual você já fez com o index.html e painel.html antes)

## Passo 2 - Abrir o Codespaces

1. No repositório, clica no botão verde Code
2. Clica na aba Codespaces
3. Clica em Create codespace on main

Isso abre uma tela parecida com o VS Code, direto no navegador, com um
terminal (uma tela preta de comandos) na parte de baixo.

## Passo 3 - Instalar as dependências

No terminal que abriu, cola isso e aperta Enter:

```
npm install
```

Espera terminar (pode levar 1-2 minutos).

## Passo 4 - Instalar o Java (necessário para compilar Android)

```
sudo apt-get update && sudo apt-get install -y openjdk-17-jdk
```

## Passo 5 - Compilar o APK

```
cd android
./gradlew assembleDebug
```

Isso pode levar de 5 a 15 minutos na primeira vez (ele baixa várias
ferramentas do Android automaticamente). Não feche a aba enquanto roda.

Se aparecer "BUILD SUCCESSFUL" no final, deu certo.

## Passo 6 - Baixar o APK gerado

O arquivo fica em:

```
android/app/build/outputs/apk/debug/app-debug.apk
```

No painel de arquivos à esquerda do Codespaces, navega até essa pasta,
clica com o botão direito em cima do arquivo app-debug.apk e escolhe
Download.

## Passo 7 - Instalar no celular

1. Manda esse arquivo .apk pro celular do motorista (por WhatsApp, e-mail,
   ou cabo USB)
2. No celular, abre o arquivo. Vai pedir permissão pra "instalar de fontes
   desconhecidas" - permite (só precisa fazer isso uma vez)
3. Instala normalmente, como qualquer aplicativo

## Se der erro no meio do caminho

Copia a mensagem de erro completa que apareceu no terminal e manda pro
Claude analisar - a maioria dos erros nessa etapa é sobre versão de
ferramenta faltando, e tem solução.
