# Comando Linux - Terminal Gitpod

> 2022-09-03 - Renato Puga



Comandos utilizados em aula para o terminal Linux.



[TOC]

---



## Roteiro



### Download de arquivos

### Instalação

### Gerenciador de pacotes

### Estrutura de Diretórios

### Navegação

### Segurança





## wget

Utilizado para fazer download de uma URL. 

```bash
# -c : para continuar o download (caso o link caia)
wget -c https://github.com/broadinstitute/gatk/releases/download/4.2.6.1/gatk-4.2.6.1.zip
```

> Nota: uma dos comandos alternativos mais utilizados é o `curl`



## clear

Utilizado para limpar o terminal

```bash
clear
```

> Nota: Atalho no teclado: Ctrl + L



## htop

Listar os processos em execução, como o consumo de processamento e memória em tempo real.

```bash
htop
```

**output**

![image-20220903120024689](/Users/renatopuga/Library/Application Support/typora-user-images/image-20220903120024689.png)



> **Nota**: Para sair do htop pressione a tecla `q` (quite)



## ls

Lista o conteúdo (arquivos, diretórios, link simbólicos, etc) de um diretório.

```bash
ls
gatk-4.2.6.1.zip  README.md
```

> Nota: O Comando `ls` pode ser combinado com diferentes opções que modificam a forma como os arquivos e diretórios são listados. 



`-l`: visualizar em lista

`-h`: pra humano entender (ex.: 1k, 2M e 2G)



```bash
ls -l
```

**output**

```bash
ls -l
total 443264
-rw-r--r-- 1 gitpod gitpod 453893126 Apr 13 19:23 gatk-4.2.6.1.zip
-rw-r--r-- 1 gitpod gitpod        56 Sep  3 16:50 Outro.md
-rw-r--r-- 1 gitpod gitpod        55 Sep  3 14:46 README.md
```



## md5sum

Gera um código hash (string grande) única para cada arquivo.

```bash
md5sum README.md
```

**output**

```bash
4fd1d0d55bc07932ae17c2a998f15fa4  README.md
```



> Nota: utilizamos muito para envio com arquivos grandes (GB) para garantir a integridade do arquivo recebido.



## cp

Copia um arquivo para outro local ou com outro nome.

```bash
cp README.md Outro.md 
```



## Ex1

> Sabendo que o `>` redireciona o output padrão, da tela para um arquivo, faça:



1. liste os arquivos do diretório `/workspace/comandos-linux`
2. Salve o resultado dessa lista em um novo arquivo chamado `todos-os-arquivos.txt`
3. Depois, gere o hash desse novo arquivo utilizando o md5sum. 







