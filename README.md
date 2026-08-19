# pc-lopal
repositório para armazenar os códigos da aula.

## 
# DESAFIO 1

Toda biblioteca JavaScript tem um número de versão, como 1.0.0. Pesquise e responda com suas palavras.

## O que significa cada um dos três números dessa versão?

## MAJOR

**MAJOR:**  (_**1**_.4.2) - **número X**


*O número **MAJOR** representa as atualizações de grande impacto dentro da aplicação. Ele é requisitado quando mudanças incompatíveis com versões anteriores são introduzidas.*

**REGRA:** Quando o número **MAJOR** é incrementado, os números **MINOR** e **PATCH** devem ser obrigatoriamente resetados para a contagem de zero.

*EXEMPLO:*

**Antes:** 1.8.4 -> **Depois:** 2.0.0

## **MINOR:**

**MINOR:**  (1._**4**_.2) - **número Y**

*O número **MINOR** representa a adição de novas funcionalidades/melhorias para a apliação, porém com o intuito de que tudo que exista na aplicação continue a funcionar exatamente da mesma forma.*

**REGRA:** Quando o número **MINOR** é incrementado, o número **PATCH** obrigatoriamente deve ser resetado para a contagem de zero.

*EXEMPLO:*

**Antes:** 1.2.1 -> **Depois:** 1.3.0

## PATCH:

**PATCH** (1.4._**2**_) - **número Z**

*O número **PATCH** representa as atualizações que corrigem bugs ou resolvem falhas dentro da aplicação. **PATCH** = "remendar/reparar"*.

**REGRA:** Quando o número **PATCH** é incrementado, os números **MAJOR** e **MINOR** se mantêm exatamente como estão. Apenas o último dígito avança.

EXEMPLO:

**Antes:** 2.1.0 -> **Depois:** 2.1.1

## - Quem decide como esse número muda e com base em quê?

**Projetos Open Source:** é decidido por quem mantêm o código (mantenedor ou time), que analisam os pedidos feitos pela comunidade e definem a próxima versão no ciclo de lançamentos;

**Em empresas/redes privadas:** é decidido pelos líderes técnicos (tech leads), desenvolvedores seniores e o gerente do produto. O gerente define o que precisa ser entregue ao cliente e o time decide como ajustar a numeração com base na prioridade e impacto da mudança no código;

**Bibliotecas/pacotes pequenos:** é decidido pelo autor do código, que faz a alteração no arquivo de configuração antes de postar a nova versão no repositório;

# DESAFIO 2

No arquivo `package.json` existem dois grupos de bibliotecas: `dependencies` e `devDependencies`. Pesquise e explique.

##  Qual a diferença entre os dois grupos? 

## Dependencies

**dependencies:** 


 *As **dependencies** representam as bibliotecas **NECESSÁRIAS** para que a aplicação execute suas funcionalidades em um "produto final". Sem as **dependencies** o projeto vai quebrar ou não iniciará.* 

## devDependencies

*As **devDependencies** representam as ferramentas necessárias no processo de desenvolvimento de uma aplicação, para que auxiliem a equipe a produzirem um código melhor escrito, mais seguro e mais rápido; mas que não são utilizadas diretamente pelo cliente no "produto final".*

## - Como você decide em qual grupo colocar uma biblioteca?

Se o a biblioteca que você adicionou for **ESSENCIAL** para a execução do código, ela deve ser atribuída as **dependencies**;

**SE NÃO** você pode atribuí-la como **devDependencies** para que auxilie na criação do código;

## 
# DESAFIO 3

Toda biblioteca JavaScript tem um número de versão, como 1.0.0. Pesquise e responda com suas palavras.

## No `package.json`, algumas versões aparecem assim: `^1.0.0`, outras assim: `~1.0.0`, e outras sem nenhum símbolo, apenas `1.0.0`. Pesquise e explique: 

## *Operadores de intervalo (range operators)*

*Estabelecem ao gerenciador de pacotes até onde eles têm permissão para atualizar automaticamente uma biblioteca quando você utiliza o comando **npm install** ou **npm update**.*

## Caret: - (^)

Padrão ao instalar uma biblioteca nova. Trava o número **MAJOR**, porém permite que os números **MINOR** e **PATCH** sejam atualizados automaticamente.(quando der comando)

*EXEMPLO:*

**^1.0.0**

**Vai instalar/atualizar para:** 1.0.1, 1.2.0, 1.9.9.

**NÃO** vai atualizar para: **2.0.0.**
## Tilde: - (~)

É focado apenas em correções.Trava tanto o número **MAJOR** quanto **MINOR**, porém permite apenas que o número **PATCH** seja atualizado automaticamente. (quando der comando)

Exemplo:

 **~1.0.0**

**Vai instalar/atualizar para:** 1.0.1, 1.0.5, 1.0.9

**NÃO** vai atualizar para: **1.1.0 nem 2.0.0**

## - O que acontece quando não existe nenhum símbolo?

É a versão exata/**pinned**. Barra completamente o gerenciador de pacotes de atualizar a biblioteca automaticamente. 

Toda vez que alguém clonar o projeto e rodar npm install, será baixada exatamente a versão 1.0.0. Mesmo que os criadores da biblioteca lancem a versão 1.0.1 corrigindo uma falha grave de segurança no dia seguinte, o seu projeto continuará instalando a 1.0.0 até que você altere o número manualmente no package.json.

##
# Desafio 4

O JavaScript tem duas formas de importar e exportar código: CommonJS e ES Modules. Pesquise e explique.

## - Qual a diferença entre os dois? 

A diferença está em como o JavaScript organiza, carrega e compartilha código entre os arquivos.

## COMMONJS

*O **CommonJS** foi criado para o ecossistema **Node.js**, portanto utiliza as funções do ambiente Node.js: **require e module.exports**.*

***Require:** O **require()** é uma função global do Node.js usada para carregar e ler um arquivo de módulo externo. Ele lê o conteúdo que foi disponibilizado pelo outro arquivo via **module.exports.***

Retorna o objeto ou função que foi exportado. É chamado passando o caminho do arquivo: **const meuModulo = require('./meuModulo')**;

***Module.exports:** O module.exports é um objeto especial em um arquivo JavaScript do Node.js. Ele guarda tudo o que você deseja disponibilizar para que outros arquivos do seu projeto possam usar.*

Permite exportar funções, objetos ou textos. Você pode atribuir um valor direto a ele: **module.exports = minhaFuncao**; 

Você pode adicionar propriedades a ele: **module.exports.soma = (a, b) => a + b**;

## ES MODULES

*Já o **ES Modules** é um padrão oficial da **ECMAScript**, basicamente um "livro de regras" que estipula padrões na linguagem de programação **JavaScript**, **JScript** e **ActionScript**. Utiliza palavras-chave nativas da linguagem **import** e **export**.*

***Exportar (Export):***

Torna um pedaço de código visível para fora do arquivo. Pode ser feito individualmente **(export function somar() {})** ou de uma vez no fim do arquivo.*

***Importar (Import)*** 

Puxa o código exportado para o arquivo atual. Usa chaves **{}** para itens específicos ou nomes diretos.*

## - Como cada um surgiu? 

***CommonJS:*** criado em 2009 pelo engenheiro **Kevin Dangoor** que fez um manifesto sobre a importância do JavaScript fora dos navegadores. Na época não havia uma biblioteca padrão e formato comum para exportação e importação de módulos do JavaScript. Ele fundou o projeto **ServerJS** que foi renomeada posteriormente para **CommonJS**, visando melhorar o gerenciamento de módulos, leitura de arquivos, redes, etc.

No mesmo ano, em novembro, o engenheiro **Ryan Dahl** lançou a primeira versão do **Node.js**. O formato **síncrono** (carregamento em tempo real) do CommonJS encaixou perfeitamente com o **require**, tornando-se uma base para o ecossistema **npm.**

***ES Modules:*** Apesar da revolução do **CommonJS**, ele não funcionava bem em navegadores. A comunidade resistia à base de soluções temporárias; percebendo isso, o comitê responsável pelo JavaScript resolveu que era a hora da linguagem ter um padrão nativo de módulos que servisse tanto em navegadores quanto servidores. **ESM** usa formato **assíncrono** (processa arquivos em paralelo, não em tempo real).