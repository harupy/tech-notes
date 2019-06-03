# GitHub

## How to use multiple github accounts

### Create keys

```console
ssh-keygen -t rsa -C main@mail.com -f id_rsa_main
ssh-keygen -t rsa -C sub@mail.com -f id_rsa_sub
```

### ~/.ssh/config

```bash
Host github.com.main  # main account
  HostName: github.com
  User git
  Port 22
  IdentityFile ~/.ssh/id_rsa_main  # key for main account
  TCPKeepAlive yes
  IdentitiesOnly yes

Host github.com.sub  # sub account
  HostName github.com
  User git
  Port 22
  IdentityFile ~/.ssh/id_rsa_sub  # key for sub account
  TCPKeepAlive yes
  IdentitiesOnly yes
```

### .gitconfig

global

```console
git config --global user.name main_username
git config --global user.email main_email
```

local

```console
cd <repository>
git cofig --local user.name sub_username
git cofig --local user.email sub_email
```

### Confirmation

```console
ssh -T git@github.com.main
ssh -T git@github.com.sub
```

[[備忘] 複数 Github アカウントで ssh 接続設定(config)を使い分ける手順 - Qiita](https://qiita.com/yampy/items/24638156abd383e08758)

## Languages Supported by Github Flavored Markdown

- actionscript3
- apache
- applescript
- asp
- brainfuck
- c
- cfm
- clojure
- cmake
- coffee-script, coffeescript, coffee
- cpp - C++
- cs
- csharp
- css
- csv
- bash
- diff
- elixir
- erb - HTML + Embedded Ruby
- go
- haml
- http
- java
- javascript
- json
- jsx
- less
- lolcode
- make - Makefile
- markdown
- matlab
- nginx
- objectivec
- pascal
- PHP
- Perl
- python
- profile - python profiler output
- rust
- salt, saltstate - Salt
- shell, sh, zsh, bash - Shell scripting
- sql
- scss
- sql
- svg
- swift
- rb, jruby, ruby - Ruby
- smalltalk
- vim, viml - Vim Script
- volt
- vhdl
- vue
- xml - XML and also used for HTML with inline CSS and Javascript
- yaml

[Languages Supported by Github Flavored Markdown](http://www.rubycoloredglasses.com/2013/04/languages-supported-by-github-flavored-markdown/)
