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

Aluno | md5sum | nome do arquivo
------|--------|-----------------
Renato | efb9ed3316b1a0996a241180ccbdb898 | todos-os-arquivos.txt
Victor | b4f311ec2152e8f05b3ccf2c01def35 | todos_os_arquivos.txt
Giovanna | 0412a2caeb33e9369813fa60349dabbe | todos-os-arquivos.txt
Leonardo | efb9ed3316b1a0996a241180ccbdb898 | todos-os-arquivos.txt
Greyce | efb9ed3316b1a0996a241180ccbdb898 | todos-os-arquivos.txt
Paulo | efb9ed3316b1a0996a241180ccbdb898 | todos-os-arquivos.txt
Fábio | 27995247488fcfce15d989c2fe79a0a7 | todos-os-arquivos.txt
Márcio | 10afc6d42d6ec6263329bf3d6751a2a1 | todos-os-arquivos.txt
Nathalia | d41d8cd98f00b204e9800998ecf8427e | todos-os-arquivos.txt
Yuri | 35fbaf692033a9741935cd0046064fba | todos-os-arquivos.txt
Lucas | efb9ed3316b1a0996a241180ccbdb898 | todos-os-arquivos.txt
Erick | 83bf3f22dc6abe1882f0b3516a29174c | todos-os-arquivos.txt
Aldi | 27995247488fcfce15d989c2fe79a0a7 | todos-os-arquivos.txt
Marina | d41d8cd98f00b204e9800998ecf8427e | todos-os-arquivos.txt
Ivone | 424ca4a748b6b43991ecb4dd0370ee77 | todos-os-arquivos.txt
Andressa | d41d8cd98f00b204e9800998ecf8427e | todososarquivos.txt
Geovana | 24f0f055ba9d2f783dcb3c549fc4e42e | todos-os-arquivos.txt


## unzip

Descompactar arquivos .zip 

```bash
unzip gatk-4.2.6.1.zip
```

> Nota: se o arquivo for `.gzip` o comando seria: `gunzip`



## cd 

Para navegar entre os diretórios

```bash
# Entrar em um diretório
cd gatk-4.2.6.1
```

```bash
# voltar para o diretório anterior
cd ..
```

> Nota: sempre será: comando [espaço] opção



## Ex2



1. Entrar no diretório do gatk
2. Identificar o tipo de todos os arquivos no diretório
3. Salvar em novo arquivo chamado `todos-os-arquivos-gatk.txt`
4. Gerar o md5sum do arquivo `todos-os-arquivos-gatk.txt`

```
a:                              ASCII text
gatk:                           Python script, ASCII text executable
gatk-completion.sh:             ASCII text, with very long lines
gatkcondaenv.yml:               ASCII text
GATKConfig.EXAMPLE.properties:  ReStructuredText file, ASCII text
gatkdoc:                        directory
gatk-package-4.2.6.1-local.jar: Zip archive data, at least v1.0 to extract
gatk-package-4.2.6.1-spark.jar: Zip archive data, at least v1.0 to extract
gatkPythonPackageArchive.zip:   Zip archive data, at least v1.0 to extract
README.md:                      UTF-8 Unicode text, with very long lines
scripts:                        directory
```


> md5sum esperado: `f725ca4388802ef3ec3652e0951b5211`


## mkdir

Comando para criar diretório



```bash
mkdir reference app input ouput
```



## df

Verfica o espaço utilizado em disco

```bash
# -h: humano entender
df -h
```

**output**

`/`: como o c:\ no Windows

`/workspace`: onde ficam nossos arquivos (gitpod)

```bash
Filesystem        Size  Used Avail Use% Mounted on
/.workspace/mark  1.5T  1.1T  375G  76% /
tmpfs              64M     0   64M   0% /dev
/dev/sda1         512G   16G  496G   4% /dev/termination-log
shm                64M     0   64M   0% /dev/shm
tmpfs              32G     0   32G   0% /sys/firmware
/dev/md42          30G  1.6G   29G   6% /workspace
/dev/md44         1.5T  1.1T  375G  76% /etc/hostname
tmpfs              32G     0   32G   0% /tmp
tmpfs              32G     0   32G   0% /proc/acpi
tmpfs              64M     0   64M   0% /proc/keys
tmpfs              32G     0   32G   0% /proc/scsi
```

# seq e awk

> https://hgdownload.soe.ucsc.edu/goldenPath/hg38/chromosomes/



Gerar uma sequencia de número de 1 até 22 com o comando `seq` e combinar com o comando `awk` para gerar um arquivo de download com o comando `wget` dos cromossomos do hg38 na UCSC.



```bash
seq 1 22 | awk '{print("wget -c https://hgdownload.soe.ucsc.edu/goldenPath/hg38/chromosomes/chr"$1".fa.gz")}' > pegar-fa.txt
```



**Excecutar** (download automático por chr)

```bash
sh pegar-fa.txt
```



**Concatenando os arquivos**

> zcat  foi utilizado para não precisar descompactar os arquivos de chr

```bash
zcat chr1.fa.gz chr2.fa.gz ... chr22.fa.gz > hg38.fa
```



## grep

Comando para procurar uma *string* dentro de um arquivo texto.

```bash
grep ">" hg38.fa
```



Ex.: Arquivo FASTA

```bash
>SEQ_01
ACAGCGAGTCAGCATGCTGTACGAT
ACAGCGAGTCAGCATGCTGTACGAT
ACAGCGAGTCAGCATGCTGTACGAT
>SEQ_02
ACAGCGAGTCAGCATGCTGTACGAT
ACAGCGAGTCAGCATGCTGTACGAT
ACAGCGAGTCAGCATGCTGTACGAT
```


# Ex3
Utilizar o comando `diff` para identificar as linhas que são diferentes entre os chr22 (hg19) e chr22 (hg38)

1. Download do chr22 das duas versões do genoma (hg19 e hg38)
2. Utilizar o comando `diff` (ver o help: diff --help)
3. Salvar o resultado do comadno diff em um novo arquivo chamado: `hg19-hg38-chr22-diff.txt`
4. md5sum hg19-hg38-chr22-diff.txt (no chat)

**Respostas**

Voltar para o diretório Workspace:
```bash
cd /workspace/comandos-linux
```

Criar os diretórios para cada versão do genoma:

```bash
mkdir hg19 hg38
```

Fazer download de cada versão:

**hg19**
```bash
cd hg19
wget -c https://hgdownload.soe.ucsc.edu/goldenPath/hg19/chromosomes/chr22.fa.gz
```

**hg38**
```bash
cd ../hg38
wget -c https://hgdownload.soe.ucsc.edu/goldenPath/hg38/chromosomes/chr22.fa.gz
```

Voltar um diretorio
```bash
cd ..
```

Rodando o comando `diff` entre os chr22:
```bash
diff <(zcat hg19/chr22.fa.gz) <(hg38/chr22.fa.gz) > hg19-hg38-chr22-diff.txt
```

```bash
md5sum hg19-hg38-diff-chr22.txt
```

> Nota: Caso tenho rodado o diff na ordem hg38 hg19 (hg38-hg19-chr22-diff.txt) o hash será diferente.

```bash
md5sum hg*.txt
a3891e51d50acaf1aa36d42dbc3f37d3  hg19-hg38-chr22-diff.txt
ed1ae57cf51c5a92d0af656b3ec54000  hg38-hg19-chr22-diff.txt
```


# Anexo

![image](https://user-images.githubusercontent.com/8321336/188283993-c63fe72b-b2a3-4c27-8277-432f86e75d13.png)

