# Instalação e Configuração do Zsh e Oh My Zsh em Debian/Ubuntu

Este guia fornece instruções detalhadas para instalar e configurar o **Zsh** e o **Oh My Zsh** em distribuições baseadas em Debian/Ubuntu (criado no ChatGpt).

## 1. Instalando o Zsh

O **Zsh** (Z Shell) é um shell poderoso e altamente customizável. Para instalá-lo, execute:

```sh
sudo apt update && sudo apt install -y zsh
```

Para verificar a versão instalada:

```sh
zsh --version
```

Defina o Zsh como o shell padrão:

```sh
chsh -s $(which zsh)
```

Reinicie a sessão ou execute `zsh` para iniciar o novo shell.

## 2. Instalando o Oh My Zsh

O **Oh My Zsh** é um gerenciador de configuração do Zsh que fornece temas e plugins. Para instalá-lo, execute:

```sh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

ou, se preferir `wget`:

```sh
sh -c "$(wget -O- https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

## 3. Configurando Plugins no Oh My Zsh

Os plugins do Oh My Zsh adicionam funcionalidades extras ao shell. Para ativá-los, edite o arquivo `~/.zshrc` e adicione os nomes dos plugins na linha `plugins=(...)`.

### Plugins Recomendados

#### 3.1 zsh-autosuggestions
Sugere comandos conforme você digita.

```sh
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

Ative-o editando `~/.zshrc` e adicionando `zsh-autosuggestions` na seção de plugins:

```sh
plugins=(git zsh-autosuggestions)
```

#### 3.2 zsh-syntax-highlighting
Destaca sintaxe dos comandos digitados.

```sh
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

Edite `~/.zshrc` e adicione `zsh-syntax-highlighting`:

```sh
plugins=(git zsh-autosuggestions zsh-syntax-highlighting)
```

Reinicie o shell para aplicar as mudanças:

```sh
source ~/.zshrc
```

## 4. Escolhendo um Tema

O Oh My Zsh oferece diversos temas. O padrão é `robbyrussell`, mas você pode trocar por `agnoster`, por exemplo. Edite `~/.zshrc`:

```sh
ZSH_THEME="agnoster"
```

Salve o arquivo e recarregue o shell:

```sh
source ~/.zshrc
```

Para listar todos os temas disponíveis:

```sh
echo $ZSH/themes/*
```

## 5. Conclusão

Com esses passos, você terá um terminal mais produtivo e visualmente organizado. Explore outros plugins e temas do Oh My Zsh para personalizar ainda mais seu ambiente!
