+++
title = "O que fazer após instalar o Ubuntu 22.04 LTS"
date = 2024-02-05T18:38:00-03:00
draft = false

[taxonomies]
tags=["linux", "ubuntu"]

[extra]
toc=true
+++

# Baixe e instale as últimas atualizações

Esta é a primeira coisa que faço após instalar um sistema operacional. É uma boa prática de segurança utilizar a versão mais recente do software, isso mantém você longe de bugs e falhas desnecessárias que podem prejudicar o desempenho. Além disso, as atualizações trazem novos recursos de segurança adicionais para o seu sistema.

O Ubuntu recebe atualizações regulares da comunidade com correções de bugs e recursos de segurança adicionais. Normalmente, o Ubuntu envia automaticamente as notificações de área de trabalho sempre que as atualizações estão disponíveis para download, mas recomendo que você verifique manualmente as atualizações disponíveis iniciando o aplicativo "Ubuntu Software".

![Ubuntu Software](/images/2024-02-02-post-install-ubuntu-22_04/ubuntu_software.png)

Ou no terminal utilizando o seguinte comando.

```bash
sudo apt-get update
```

```bash
sudo apt-get upgrade
```

```bash
sudo apt-get dist-upgrade
```

# Instale o Flatpak

Flatpak é uma tecnologia de empacotamento de software que visa fornecer uma maneira de distribuir aplicativos de forma independente do sistema operacional. Ele é projetado para ser uma solução de empacotamento universal e portátil, permitindo que os aplicativos sejam executados em várias distribuições Linux, eliminando algumas das dependências do sistema operacional subjacente.

A principal ideia por trás do Flatpak é criar um ambiente isolado chamado "sandbox" para os aplicativos. Cada aplicativo empacotado como Flatpak inclui suas próprias dependências e bibliotecas, reduzindo assim os possíveis conflitos com as versões do sistema. Isso permite que os desenvolvedores distribuam seus aplicativos de maneira mais consistente, independentemente da distribuição Linux que o usuário esteja usando.

Instala o flatpak

```bash
sudo apt-get install flatpak
```

Instala o plugin flatpak na loja de software GNOME

```bash
sudo apt-get install -y gnome-software-plugin-flatpak
```

Adicionar o repositório flathub

```bash
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

# Instale o Homebrew

Homebrew é um sistema de gerenciamento de pacotes para macOS e outros sistemas operacionais baseados em Unix. Ele fornece uma maneira conveniente de instalar, atualizar e gerenciar software no seu sistema, facilitando a instalação de programas adicionais e ferramentas de linha de comando.

O Homebrew é projetado para simplificar o processo de instalação de software no macOS, que historicamente não inclui um gerenciador de pacotes nativo. Com o Homebrew, os usuários podem instalar facilmente uma variedade de aplicativos, utilitários e bibliotecas, mantendo-os atualizados com comandos simples.

Alguns dos recursos principais do Homebrew incluem:

1. Fácil instalação: O Homebrew pode ser instalado com um único comando no terminal, simplificando o processo de configuração.

2. Fórmulas: Os pacotes no Homebrew são chamados de "fórmulas". Cada fórmula contém instruções sobre como baixar, compilar e instalar um determinado software.

3. Atualizações fáceis: O Homebrew permite que você mantenha seu software atualizado com um simples comando, facilitando a gestão de pacotes instalados.

4. Bibliotecas compartilhadas: O Homebrew ajuda a gerenciar dependências e bibliotecas compartilhadas, garantindo que os aplicativos tenham acesso às versões corretas das bibliotecas necessárias.

Para instalar o Homebrew no macOS, você pode usar o seguinte comando no terminal:

```bash
# requisitos
sudo apt-get install build-essential curl file git

# instalação
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Após a instalação, você pode usar comandos como brew install, brew upgrade e brew search para instalar, atualizar e pesquisar pacotes, respectivamente.

O Homebrew é uma ferramenta popular entre desenvolvedores e usuários avançados do macOS, pois oferece uma maneira simples e consistente de gerenciar software em seus sistemas.

# zsh e ohmyzsh

**zsh** e **Oh My Zsh** são duas ferramentas relacionadas que estão relacionadas ao ambiente de linha de comando em sistemas Unix-like, como o Linux e o macOS. Vamos entender o que cada uma delas faz:

1. zsh (Z Shell):

   1. O que é: zsh é um interpretador de shell, ou seja, é um programa que aceita comandos do usuário e os executa. É uma alternativa ao shell mais comum, o bash (Bourne Again SHell), e inclui recursos adicionais e melhorias de usabilidade.

   2. Recursos: zsh oferece várias características avançadas, incluindo autocompletar mais robusto, histórico de comandos melhorado, suporte a temas e plugins, entre outros.

2. Oh My Zsh:

   1. O que é: Oh My Zsh é um framework de configuração para o zsh. Ele fornece uma maneira fácil de configurar e personalizar o zsh com temas, plugins e outras opções.

   2. Recursos: Oh My Zsh simplifica a personalização do prompt de comando, oferece uma variedade de temas e inclui um sistema de plugins que facilita a adição de funcionalidades adicionais ao seu ambiente zsh.

   3. Uso de Temas e Plugins: Oh My Zsh oferece uma variedade de temas e plugins. Você pode configurar o tema editando o arquivo de configuração, e os plugins podem ser habilitados ou desabilitados da mesma forma.

Tanto o zsh quanto o Oh My Zsh são populares entre usuários que desejam uma experiência de linha de comando mais rica e personalizável. Eles oferecem muitos recursos úteis para tornar a interação com o terminal mais eficiente e agradável.

```bash
sudo apt-get install -y zsh curl git
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

## Plugin zsh_auto_suggestions

```bash
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions

# set zsh-autosuggestions plugin in zsh
# open .zshrc file with nano
nano ~/.zshrc

# add zsh-autosuggestions in plugins
plugins=(git zsh-autosuggestions)
# press ^o enter then ^x to exit

# load the zsh file changes
source ~/.zshrc
```

# nvm

```bash
# install nvm
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash
# set nvm plugin in zsh
# open .zshrc file wiht nano
nano ~/.zshrc
# add nvm in plugins
plugins=(git zsh-autosuggestions nvm)
# press ^o enter then ^x to exit

# load the zsh file changes
source ~/.zshrc
```

# nodejs

```bash
nvm install --lts
```

# yarn

```bash
npm i -g yarn
```

# Docker

```bash
sudo snap install docker
```

# Firacode

```bash
# add repository
sudo add-apt-repository "deb http://archive.ubuntu.com/ubuntu $(lsb_release -sc) universe"
# update
sudo apt-get update
# install fira code
sudo apt-get install -y fonts-firacode
```

# VisualStudio Code

```bash
flatpak install flathub com.visualstudio.code
```

# Instale o GNOME Tweak Tool

O GNOME Tweak Tool, agora conhecido como GNOME Tweaks, é uma ferramenta de personalização para o ambiente de desktop GNOME.

O GNOME Tweaks fornece uma interface gráfica para ajustar várias configurações e opções do GNOME que podem não estar acessíveis diretamente nas configurações padrão do sistema. Com o GNOME Tweaks, os usuários podem personalizar a aparência, comportamento e funcionalidades do ambiente de desktop GNOME de acordo com suas preferências.

Algumas das configurações que podem ser ajustadas usando o GNOME Tweaks incluem a aparência do tema, ícones, fontes, comportamento do touchpad, atalhos de teclado, extensões do GNOME Shell e muito mais. É uma ferramenta útil para usuários que desejam personalizar sua experiência no ambiente de desktop GNOME de maneira mais detalhada e específica.

```bash
sudo apt install gnome-tweaks
```

# Habilite o Firewall

UFW é o firewall integrado para Ubuntu e é altamente confiável. Por padrão, ele não está habilitado e você deve habilitá-lo manualmente.

```bash
sudo ufw enable
```

# Instale o pacote ubuntu-restricted-extras

O pacote ubuntu-restricted-extras é um conjunto de software adicional disponível para sistemas operacionais baseados em Ubuntu, como o Ubuntu Linux. Esse pacote inclui vários codecs de áudio e vídeo, bem como fontes TrueType adicionais, que são essenciais para reproduzir uma variedade de formatos de mídia comumente encontrados na internet.

Alguns dos componentes incluídos no ubuntu-restricted-extras são:

1. Codecs de Áudio e Vídeo: Inclui codecs para reproduzir formatos populares de áudio e vídeo que podem não ser suportados por padrão devido a restrições de patentes ou licenças.

2. Suporte para Flash Player: Inclui o plugin Adobe Flash Player, que é necessário para reproduzir conteúdo Flash em navegadores da web.

3. Fontes TrueType adicionais: Inclui fontes TrueType que podem ser usadas para melhorar a renderização de texto em aplicativos e navegadores.

Ao instalar o ubuntu-restricted-extras, os usuários podem melhorar significativamente a capacidade de reprodução de mídia em seus sistemas Ubuntu, garantindo suporte para uma ampla gama de formatos. Isso é particularmente útil ao reproduzir vídeos online, ou ao utilizar aplicativos que requerem esses codecs e recursos adicionais.

Para instalar o pacote, você pode usar o seguinte comando no terminal:

```bash
sudo apt-get install ubuntu-restricted-extras
```

É importante observar que, devido a questões de licenciamento e patentes, alguns desses componentes podem não estar disponíveis em todas as regiões do mundo. Os usuários devem verificar a conformidade com as leis locais ao instalar e usar esses pacotes em seus sistemas.

# Referências

- [Site oficial do Ubuntu](https://ubuntu.com/)
- [GNOME Tweaks](https://wiki.gnome.org/Apps/Tweaks)
- [GNOME Tweak Tool: aprenda a personalizar seu sistema](https://diolinux.com.br/gnome/gnome-tweak-tool-gnome-tweaks-no-ubuntu.html)
- [Ubuntu-restricted-extras](https://pt.wikipedia.org/wiki/Ubuntu-restricted-extras)
- [Flatpak Ubuntu Quick Setup](https://flatpak.org/setup/Ubuntu)
- [Homebrew on Linux](https://docs.brew.sh/Homebrew-on-Linux)
