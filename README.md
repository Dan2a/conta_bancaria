# Projeto Conta Bancária

Este projeto é um sistema simples de gerenciamento de contas bancárias de linha de comando (CLI), desenvolvido como parte do bootcamp **Desenvolvedor Full Stack JavaScript** da [Generation Brasil](https://brazil.generation.org/).

## Sobre o Projeto

O sistema simula as operações básicas de um banco, permitindo ao usuário gerenciar contas correntes e contas poupança. Ele utiliza conceitos de Programação Orientada a Objetos (POO), como classes, herança e interfaces, para estruturar o código.

## Funcionalidades

O menu interativo permite ao usuário realizar as seguintes operações:

* **1 - Criar Conta:** Permite criar uma nova Conta Corrente ou Conta Poupança.
* **2 - Listar todas as Contas:** Exibe os dados de todas as contas cadastradas.
* **3 - Buscar Conta por Número:** Procura e exibe os dados de uma conta específica.
* **4 - Atualizar Dados da Conta:** Permite modificar os dados de uma conta existente.
* **5 - Apagar Conta:** Remove uma conta do sistema.
* **6 - Sacar:** Realiza um saque de uma conta, validando o saldo (e o limite, no caso de Conta Corrente).
* **7 - Depositar:** Adiciona um valor ao saldo de uma conta.
* **8 - Transferir valores entre Contas:** Move um valor de uma conta de origem para uma conta de destino.
* **9 - Sair:** Encerra o programa.

## Tecnologias Utilizadas

Este projeto foi construído com as seguintes tecnologias:

* **[Node.js](https://nodejs.org/en/)**: Ambiente de execução para o JavaScript no backend.
* **[TypeScript](https://www.typescriptlang.org/)**: Superset do JavaScript que adiciona tipagem estática e recursos de POO.
* **[readline-sync](https://www.npmjs.com/package/readline-sync)**: Biblioteca para receber entradas de usuário de forma síncrona no terminal.

## Estrutura do Projeto

O código-fonte está organizado da seguinte maneira:

* `Menu.ts`: Arquivo principal que contém a lógica do menu e inicia a aplicação.
* `src/`
    * `model/`: Contém as classes que representam os dados (entidades) da aplicação.
        * `Conta.ts`: Classe abstrata base para os tipos de conta.
        * `ContaCorrente.ts`: Classe que estende `Conta` e adiciona o atributo `limite`.
        * `ContaPoupanca.ts`: Classe que estende `Conta` e adiciona o atributo `aniversario`.
    * `repository/`: Define a interface (`ContaRepository.ts`) com os métodos que a `ContaController` deve implementar (CRUD e operações bancárias).
    * `controller/`: Contém a classe `ContaController.ts`, que implementa a interface `ContaRepository` e armazena a lógica de negócio e o gerenciamento das contas (em um Array).
    * `util/`: Contém arquivos de utilidade, como o `Colors.ts` para colorir a saída do console.
* `package.json`: Lista as dependências e scripts do projeto.
* `tsconfig.json`: Arquivo de configuração do compilador TypeScript.

## Como Executar

1.  **Clone o repositório** (ou certifique-se de ter todos os arquivos na mesma pasta).

2.  **Instale as dependências**
    No terminal, dentro da pasta do projeto, execute:
    ```bash
    npm install
    ```

3.  **Execute o projeto**
    Existem duas formas principais:

    **Opção 1: Usando `ts-node` (Recomendado para desenvolvimento)**
    Se você não tiver o `ts-node` instalado globalmente, instale-o:
    ```bash
    npm install -g ts-node
    ```
    Em seguida, execute:
    ```bash
    ts-node Menu.ts
    ```

    **Opção 2: Compilando para JavaScript**
    Primeiro, compile os arquivos TypeScript:
    ```bash
    tsc
    ```
    Isso irá gerar os arquivos `.js` correspondentes. Em seguida, execute o arquivo principal com o Node.js:
    ```bash
    node Menu.js
    ```

---
Feito por **Daniel Almeida Andrade** para o **Bootcamp Generation** 🚀
