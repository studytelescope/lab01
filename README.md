## Laboratory work I

Данная лабораторная работа посвещена изучению утилит для разработки проектов

## Tasks

- [x] 1. Ознакомиться со ссылками учебного материала
- [x] 2. Выполнить инструкцию учебного материала
- [x] 3. Составить отчет и отправить ссылку личным сообщением в **Slack**

## Report

Set up environment variables

```bash
$ export GITHUB_USERNAME=big_telescope # Set up GITHUB_USERNAME environment variable
$ export GIST_TOKEN=/********************** # Set up GIST_TOKEN environment variable
$ alias edit=subl # Setting "edit" name
```

Set up workspace environment

```ShellSession
$ mkdir -p ${GITHUB_USERNAME}/workspace #Creation of a workspace/ folder

$ cd ${GITHUB_USERNAME}/workspace #Getting into "workspace" folder

# Writing the full pathname to the stdout
$ pwd
/home/johnsnow/thedraftaccount/workspace

$ cd ..
$ pwd
/home/johnsnow/thedraftaccount

```

Create local folders for comfortable organization

```ShellSession
# Creation tasks/, projects/, reports/ folders inside workspace/ folder
$ mkdir -p workspace/tasks/
$ mkdir -p workspace/projects/
$ mkdir -p workspace/reports/
$ cd workspace
```

Get nodejs archive and install utility

```ShellSession
# Getting nodejs archive
$ wget https://nodejs.org/dist/v6.11.5/node-v6.11.5-linux-x64.tar.xz

--2020-04-18 22:00:34--  https://nodejs.org/dist/v6.11.5/node-v6.11.5-linux-x64.tar.xz
Resolving nodejs.org (nodejs.org)... 104.20.22.46, 104.20.23.46, 2606:4700:10::6814:162e, ...
Connecting to nodejs.org (nodejs.org)|104.20.22.46|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 9356460 (8,9M) [application/x-xz]
Saving to: ‘node-v6.11.5-linux-x64.tar.xz’

node-v6.11.5-linux- 100%[===================>]   8,92M  2,17MB/s    in 4,1s    

2020-04-18 22:00:38 (2,17 MB/s) - ‘node-v6.11.5-linux-x64.tar.xz’ saved [9356460/9356460]


# Unpacking nodejs archive
$ tar -xf node-v6.11.5-linux-x64.tar.xz

# Deleting nodejs archive
$ rm -rf node-v6.11.5-linux-x64.tar.xz

# Renaming unpacked nodejs programm
$ mv node-v6.11.5-linux-x64 node
```

Update Path

```ShellSession
# Looking into node/bin folder
$ ls node/bin
node  npm

# Looking at set PATH environment variable
$ echo ${PATH}
/home/johnsnow/anaconda3/bin:/home/johnsnow/anaconda3/condabin:/home/johnsnow/.rvm/gems/ruby-2.6.6/bin:/home/johnsnow/.rvm/gems/ruby-2.6.6@global/bin:/home/johnsnow/.rvm/rubies/ruby-2.6.6/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/home/johnsnow/go/src/github.com/bitmap-research/bin:/home/johnsnow/go/bin:/snap/bin:/home/johnsnow/.rvm/bin

# Adding "`pwd`/node/bin" string to PATH
$ export PATH=${PATH}:`pwd`/node/bin

# Looking at updated PATH environment variable
$ echo ${PATH}
/home/johnsnow/anaconda3/bin:/home/johnsnow/anaconda3/condabin:/home/johnsnow/.rvm/gems/ruby-2.6.6/bin:/home/johnsnow/.rvm/gems/ruby-2.6.6@global/bin:/home/johnsnow/.rvm/rubies/ruby-2.6.6/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/home/johnsnow/go/src/github.com/bitmap-research/bin:/home/johnsnow/go/bin:/snap/bin:/home/johnsnow/.rvm/bin:/home/johnsnow/thedraftaccount/node/bin

# Creation scripts/ folder
$ mkdir scripts

# Adding string below into "activate" file
$ cat > scripts/activate<<EOF
export PATH=\${PATH}:`pwd`/node/bin
EOF

# Executing script from "activate" file
$ source scripts/activate
```

Install gistup

```ShellSession

# Installing gistup
$ npm install -g gistup
/home/johnsnow/thedraftaccount/node/bin/gistup -> /home/johnsnow/thedraftaccount/node/lib/node_modules/gistup/bin/gistup
/home/johnsnow/thedraftaccount/node/bin/gistup-open -> /home/johnsnow/thedraftaccount/node/lib/node_modules/gistup/bin/gistup-open
/home/johnsnow/thedraftaccount/node/bin/gistup-rename -> /home/johnsnow/thedraftaccount/node/lib/node_modules/gistup/bin/gistup-rename
/home/johnsnow/thedraftaccount/node/lib
└─┬ gistup@0.1.3 
  ├─┬ optimist@0.3.7 
  │ └── wordwrap@0.0.3 
  └── queue-async@1.2.1 
$ ls node/bin
```

Update json file

```ShellSession

# Adding string below to gistup.json file
$ cat > ~/.gistup.json <<EOF
{
  "token": "${GIST_TOKEN}"
}
EOF
```

Make report

## Report

```ShellSession
# Setting LAB_NUMBER environment variable
$ export LAB_NUMBER=01

# Cloning tasks/lab01 repo
$ git clone https://github.com/tp-labs/lab${LAB_NUMBER} tasks/lab${LAB_NUMBER}

# Creation of reports/lab01 directory
$ mkdir reports/lab${LAB_NUMBER}

# Copying .md file from tasks/ to reports/
$ cp tasks/lab${LAB_NUMBER}/README.md reports/lab${LAB_NUMBER}/REPORT.md
$ cd reports/lab${LAB_NUMBER}
$ edit REPORT.md

# Pushing into gists
$ gistup -m "lab${LAB_NUMBER}" # enter: yes↵
```

## Links

### Unix commands

- [ar](https://en.wikipedia.org/wiki/Ar_(Unix))
- [cat](https://en.wikipedia.org/wiki/Cat_(Unix))
- [cd](https://en.wikipedia.org/wiki/Cd_(command))
- [cp](https://en.wikipedia.org/wiki/Cp_(Unix))
- [cut](https://en.wikipedia.org/wiki/Cut_(Unix))
- [echo](https://en.wikipedia.org/wiki/Echo_(command))
- [env](https://en.wikipedia.org/wiki/Env_(shell))
- [ex](https://en.wikipedia.org/wiki/Ex_(editor))
- [file](https://en.wikipedia.org/wiki/File_(command))
- [find](https://en.wikipedia.org/wiki/Find)
- [ls](https://en.wikipedia.org/wiki/Ls)
- [man](https://en.wikipedia.org/wiki/Man_page)
- [mkdir](https://en.wikipedia.org/wiki/Mkdir)
- [mv](https://en.wikipedia.org/wiki/Mv)
- [nm](https://en.wikipedia.org/wiki/Nm_(Unix))
- [ps](https://en.wikipedia.org/wiki/Ps_(Unix))
- [pwd](https://en.wikipedia.org/wiki/Pwd)
- [rm](https://en.wikipedia.org/wiki/Rm_(Unix))
- [sed](https://en.wikipedia.org/wiki/Sed)
- [touch](https://en.wikipedia.org/wiki/Touch_(Unix))

### Package Managers

- [apt](http://help.ubuntu.ru/wiki/apt) | [dnf](https://en.wikipedia.org/wiki/DNF_(software)) | [yum](https://fedoraproject.org/wiki/Yum/ru)
- [brew](https://brew.sh) | [linuxbrew](http://linuxbrew.sh)
- [npm](https://docs.npmjs.com)

### Software

- [curl](https://www.gitbook.com/book/bagder/everything-curl/details)
- [wget](https://www.gnu.org/software/wget/manual/wget.pdf)
- [clang](https://clang.llvm.org)
- [g++](https://gcc.gnu.org/onlinedocs/gcc-4.0.2/gcc/G_002b_002b-and-GCC.html)
- [make](https://en.wikipedia.org/wiki/Make_(software))
- [open](https://developer.apple.com/legacy/library/documentation/Darwin/Reference/ManPages/man1/open.1.html)
- [openssl](https://www.openssl.org)
- [nano](https://www.nano-editor.org)
- [tree](https://linux.die.net/man/1/tree)
- [vim](http://www.vim.org)
