# Como instalar/configurar/usar o `GRUB Customizer` no `Linux Ubuntu`

## Resumo

Neste documento estão contidos os principais comandos e configurações para instalar/configurar/usar o `GRUB Customizer` no `Linux Ubuntu`.

## _Abstract_

_This document contains the main commands and settings to install/configure/usar the `GRUB Customizer` on `Linux Ubuntu`._

## Descrição

### `GRUB Customizer`

O `Grub Customizer` é uma ferramenta gráfica que permite aos usuários do `Linux Ubuntu` e outras distribuições `Linux` personalizar o menu de inicialização do `GRUB2` (GRand Unified Bootloader versão 2). Com esta aplicação, você pode facilmente adicionar, remover, reordenar e editar as entradas do menu de inicialização sem ter que manipular manualmente arquivos de configuração complexos. A ferramenta também oferece opções para alterar a aparência do menu `GRUB`, como cores e resolução, e permite fazer ajustes avançados, como modificar parâmetros do kernel. É uma maneira mais amigável e acessível de gerenciar as opções de inicialização do sistema.


## 1. Configurar/Instalar/Usar o `GRUB Customizer` do `Linux Ubuntu` [1][2]

**ATENÇÂO**: Tenha em mente que o `GRUB` deve ser instalado no primário da sequência de `boot`, logo, se ele for instalado em outro disco, este, por sua vez, deve ser alterado para ser o primeiro disco na inicialização do computador.

### 1.1 Atualizar o Sistema Operacional (SO)

1. Abra o terminal. Você pode fazer isso pressionando:

    ```bash
    Ctrl + Alt + T
    ```

2. Certifique-se de que seu sistema esteja limpo e atualizado.

2.1 Limpar o `cache` do gerenciador de pacotes `apt`. Especificamente, ele remove todos os arquivos de pacotes (`.deb`) baixados pelo `apt` e armazenados em `/var/cache/apt/archives/`. Digite o seguinte comando:
```bash
sudo apt clean
```

2.2 Remover pacotes `.deb` antigos ou duplicados do `cache` local. É útil para liberar espaço, pois remove apenas os pacotes que não podem mais ser baixados (ou seja, versões antigas de pacotes que foram atualizados). Digite o seguinte comando:
```bash
sudo apt autoclean
```

2.3 Remover pacotes que foram automaticamente instalados para satisfazer as dependências de outros pacotes e que não são mais necessários. Digite o seguinte comando:
```bash
sudo apt autoremove -y
```

2.4 Buscar as atualizações disponíveis para os pacotes que estão instalados em seu sistema. Digite o seguinte comando e pressione `Enter`:
```bash
sudo apt update
```

2.5 **Corrigir pacotes quebrados**: Isso atualizará a lista de pacotes disponíveis e tentará corrigir pacotes quebrados ou com dependências ausentes:
```bash
sudo apt --fix-broken install
```

2.6 Limpar o `cache` do gerenciador de pacotes `apt` novamente:
```bash
sudo apt clean
```

2.7 Para ver a lista de pacotes a serem atualizados, digite o seguinte comando e pressione `Enter`:
```bash
sudo apt list --upgradable
```

2.8 Realmente atualizar os pacotes instalados para as suas versões mais recentes, com base na última vez que você executou `sudo apt update`. Digite o seguinte comando e pressione `Enter`:
```bash
sudo apt full-upgrade -y
```

3. **Reinstale o `software-properties-common`:** O pacote `software-properties-common` inclui o _script_ `add-apt-repository`. Reinstalá-lo pode corrigir quaisquer problemas no _script_:

    ```bash
    sudo apt install --reinstall software-properties-common
    ```

4. Adicione o repositório PPA (Personal Package Archive) que contém o GRUB Customizer:

    ```bash
    sudo add-apt-repository ppa:danielrichter2007/grub-customizer -y
    ```

5. **Instale o `Grub` Customizer:**

    ```bash
    sudo apt install grub-customizer -y
    ```

6. Após a instalação, você pode abrir o `Grub Customizer` através do menu de aplicativos ou executando no `Terminal Emulator`:

    ```bash
    grub-customizer
    ```


### 1.1 Código completo para configurar/instalar/usar

Para configurar/instalar/usar o `GRUB Customizer` no `Linux Ubuntu` sem precisar digitar linha por linha, você pode seguir estas etapas:

1. Abra o `Terminal Emulator`. Você pode fazer isso pressionando:

    ```bash
    Ctrl + Alt + T
    ```

2. Digite o seguinte comando e pressione `Enter`:

    ```bash
    sudo apt clean
    sudo apt autoclean
    sudo apt autoremove
    sudo apt update -y
    sudo apt autoremove
    sudo apt autoclean
    sudo apt list --upgradable
    sudo apt full-upgrade -y
    sudo apt install --reinstall software-properties-common
    sudo add-apt-repository ppa:danielrichter2007/grub-customizer -y
    sudo apt install grub-customizer -y
    ```


## Referências

[1] OPENAI. ***Instalar o `grub customizer` no `linux ubuntu` pelo `terminal emulator`.*** Disponível em: <https://chat.openai.com/c/9d00a24c-142f-46fc-965f-97504fc33492> (texto adaptado). ChatGPT. Acessado em: 31/10/2023 15:28.

[2] JAMES, J.. ***How to install grub customizer on ubuntu 22.04 or 20.04.*** Disponível em: <https://www.linuxcapable.com/how-to-install-grub-customizer-on-ubuntu-linux/>. ChatGPT. Acessado em: 31/10/2023 15:29.
