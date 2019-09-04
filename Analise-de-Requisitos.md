## Análise de Requisitos

### Descrição dos Casos de Uso

**1. Caso de Uso: Registrar Usuário**

- **Ator Primário:** Usuário

- **Ator Secundário:** Servidor

- **Resumo:** Registrar USUÁRIO para acesso as funcionalidades do sistema

- **Fluxo principal:**

  ```
  1. Após instalação do aplicativo USUÁRIO acessa clicando no ícone;
  2. Sistema apresenta tela de login e USUÁRIO clica no botão Registrar;
  3. Sistema apresenta tela para que USUÁRIO preencha suas informações;
  4. USUÁRIO preenche as informações e clica no botão Enviar;
  5. Sistema executa validações dos campos (cpf, e-mail, datas, etc.);
  6. Sistema envia solicitação de registro para SERVIDOR;
  7. SERVIDOR verifica se não existe USUÁRIO com mesma identificação;
  8. SERVIDOR grava resgistro no Banco de dados e retorna resultado;
  9. Sistema confirma registro para o USUÁRIO e apresenta tela de Login.
  ```

- **Exceções:**
  
  - Se a validação dos campos no item 5 ou verificação do item 7 não ocorrer com sucesso, sistema apresenta resultado negativo para USUÁRIO e fluxo retorna para item 3.

***

**2. Caso de Uso: Autenticar Usuário**

* **Ator Primário:** Usuário
* **Ator Secundário:** Servidor
* **Resumo:** Autenticação do USUÁRIO junto ao sistema
* **Fluxo principal:**

        1. USUÁRIO abre aplicativo clicando no ícone;
        2. Sistema apresenta tela para que USUÁRIO digite login e senha para autenticação;
        3. USUÁRIO digita login e senha e clica no botão acessar;
        4. Sistema envia credenciais do USUÁRIO para o SERVIDOR autenticar;
        5. SERVIDOR retorna confirmação da autenticação para o sistema;
        6. Sistema apresenta tela principal para o USUÁRIO.

* **Exceções:**
  
  * Caso USUÁRIO digite de forma incorreta o login e/ou senha. Sistema exibe mensagem de erro para USUÁRIO e fluxo volta para item 2.

***

**3. Caso de Uso: Alterar dados do Usuário**


* **Ator Primário:** Usuário

* **Ator Secundário:** Servidor

* **Resumo:** Alterar informações cadastrais do USUÁRIO

* **Fluxo principal:**
  
        1. Na tela principal, USUÁRIO clica no menu e seleciona a opção perfil;
        2. Sistema apresenta tela de perfil do USUÁRIO;
        3. USUÁRIO clica no botão flutuante Editar;
        4. Sistema apresenta tela de edição com informações possíveis de alterar;
        5. USUÁRIO altera informações desejadas e clica no botão Salvar;
        6. Sistema executa validações dos campos alterados;
        7. Sistema envia solicitação de alteração para o SERVIDOR;
        8. SERVIDOR executa alteração no Banco de dados e retorna resultado;
        9. Sistema apresenta confirmação e retorna para tela de perfil do USUÁRIO ;
    
* **Exceções:**
  
  * Se a validação dos campos no item 6 não ocorrer com sucesso, sistema apresenta resultado negativo e fluxo retorna para item 4.

***

**4. Caso de Uso: Cadastrar Tarefa**

* **Ator Primário:** Usuário
* **Ator Secundário:** Servidor

* **Resumo:** Cadastro de tarefa pelo USUÁRIO

* **Fluxo Principal:** 
  
        1. Na tela principal, USUÁRIO clica no botão flutuante Adicionar;
        2. Sistema apresenta tela de cadastro de tarefa;
        3. USUÁRIO preenche informações da tarefa e clica em Salvar;
        4. Sistema executa validação dos campos;
        5. Sistema envia solicitação de cadastro de tarefa para o SERVIDOR;
        6. SERVIDOR executa gravação da tarefa no Banco de Dados e retorna resultado;
        7. Sistema apresenta confirmação e apresenta tela de informações da tarefa;
    
* **Exceções:**
  
  * Se a validação dos campos não ocorrer com sucesso ou gravação da tarefa no banco de dados retornar erro, sistema apresenta resultado negativo e fluxo retorna para item 2.

***

**5. Caso de Uso: Editar Tarefa**

* **Ator Primário:** Usuário
* **Ator Secundário:** Servidor

* **Resumo:** Edição de tarefa pelo USUÁRIO

* **Fluxo Principal:** 
  
        1. Na tela principal, USUÁRIO clica na tarefa que deseja editar;
        2. Sistema apresenta tela de informações da tarefa;
        3. USUÁRIO clica no botão flutuante Editar;
        4. Sistema apresenta tela de edição da tarefa com campos possíveis de alterar;
        5. USUÁRIO altera informações desejadas e clica em Salvar;
        6. Sistema executa validação dos campos;
        7. Sistema envia solicitação de alteração de tarefa para o SERVIDOR;
        8. SERVIDOR executa gravação da alteração no Banco de Dados e retorna resultado;
        9. Sistema apresenta confirmação e retorna para tela de informações da tarefa;
    
* **Exceções:**
  
  * Se a validação dos campos não ocorrer com sucesso ou gravação da tarefa no banco de dados retornar erro, sistema apresenta resultado negativo e fluxo retorna para item 4.

***

**6. Caso de Uso: Finalizar Tarefa**

* **Ator Primário:** Usuário
* **Ator Secundário:** Servidor

* **Resumo:** Solicitação de exclusão da tarefa pelo USUÁRIO

* **Fluxo Principal:** 
  
        1. Na tela principal, USUÁRIO clica na tarefa que deseja finalizar;
        2. Sistema apresenta tela de informações da tarefa;
        3. USUÁRIO clica no botão flutuante Finalizar;
        6. Sistema envia solicitação de finalização da tarefa para o SERVIDOR;
        4. Sistema apresenta notificação sobre finalização da tarefa;
        5. SERVIDOR atualiza o estado da tarefa de "Aberta" para "Finalizada"; 
        7. Sistema volta para a tela principal.
***

**7. Caso de Uso: Configurar Rotina**

* **Ator Primário:** Usuário
* **Ator Secundário:** Servidor

* **Resumo:** Configuração de rotina pelo USUÁRIO

* **Fluxo Principal:** 
  
        1. Na tela principal, USUÁRIO clica no menu e seleciona a opção rotinas;
        2. Sistema apresenta tela com as rotinas que envolvem o usuário;
        3. USUÁRIO clica no na opção Criar/Editar;
        4. Sistema apresenta as opções de configuração da rotina;
        5. USUÁRIO configura a rotina e clica em Aplicar;
        6. Sistema faz uma validação inicial da configuração e envia as configurações para o SERVIDOR;        
        7. SERVIDOR valida as configurações recebidas e atualiza ou cria a rotina;
        8. SERVIDOR envia uma notificação de sucesso para o USUÁRIO; 
        9. Sistema retorna para a tela de rotinas.
        
* **Exceções:**
  
  * Se a validação dos campos no item 6 não tiver sucesso será evidenciado o campo com entrada inválida e o sistema continuará neste item.
  * Se a validação dos campos no item 7 não tiver sucesso será retornado uma mensagem de falha para o usuário e o sistema retornará para o item 4.
***


**8. Caso de Uso: Registrar local**

* **Ator Primário:** Usuário
* **Ator Secundário:** Servidor

* **Resumo:** Configuração de rotina pelo USUÁRIO

* **Fluxo Principal:** 
  
        1. Na tela principal, USUÁRIO clica no menu e seleciona a Casa;
        2. Sistema apresenta tela com as rotinas que envolvem o usuário;
        3. USUÁRIO clica no na opção Criar/Editar;
        4. Sistema apresenta as opções de configuração da rotina;
        5. USUÁRIO configura a rotina e clica em Aplicar;
        6. Sistema faz uma validação inicial da configuração e envia as configurações para o SERVIDOR;        
        7. SERVIDOR valida as configurações recebidas e atualiza ou cria a rotina;
        8. SERVIDOR envia uma notificação de sucesso para o USUÁRIO; 
        9. Sistema retorna para a tela de rotinas.
        
* **Exceções:**
  
  * Se a validação dos campos no item 6 não tiver sucesso será evidenciado o campo com entrada inválida e o sistema continuará neste item.
  * Se a validação dos campos no item 7 não tiver sucesso será retornado uma mensagem de falha para o usuário e o sistema retornará para o item 4.
***

