# 🔄 Entity Service Communication Client (AIDL)

##### Aplicativo cliente Android desenvolvido em Kotlin para demonstrar a Comunicação entre Processos (IPC) consumindo um serviço remoto através da interface AIDL (Android Interface Definition Language).
##### O objetivo principal é demonstrar como um aplicativo pode se vincular a um serviço de outro processo, realizar chamadas de métodos síncronos de forma segura e atualizar a interface do usuário com os resultados processados remotamente.

##### Este projeto foi criado para fins acadêmicos no contexto da disciplina D2DA2 - Des. Android 2, com foco em:

- Consumo de Bound Services externos via AIDL
- Implementação de ServiceConnection para monitoramento de estado da conexão
- Conversão de IBinder para interfaces AIDL usando Stub.asInterface
- Gerenciamento de concorrência com Threads para chamadas IPC (Inter-Process Communication)
- Sincronização de threads secundárias com a UI Thread através de runOnUiThread
- Uso de ViewBinding para manipulação segura e eficiente da interface


## 🚀 Funcionalidades

##### ✔️ Vinculação Dinâmica: Conecta-se ao serviço remoto IncrementBoundService de forma transparente no ciclo de vida onCreate.
##### ✔️ Chamada de Método Remoto: Solicita o incremento de um contador para o serviço provedor enviando o valor atual.
##### ✔️ Processamento em Background: Executa a comunicação com o serviço em uma Thread separada, garantindo que a interface não congele (ANR-free).
##### ✔️ Atualização Síncrona: Recebe o retorno do incremento e atualiza o estado local do contador na tela.
##### ✔️ Feedback Visual: Exibe Toasts informativos sobre o número de cliques processados pelo serviço remoto.
##### ✔️ Segurança de Ciclo de Vida: Realiza a desvinculação automática (unbindService) no onDestroy para evitar vazamentos de memória (memory leaks).


## 🛠 Tecnologias Utilizadas
- Kotlin — Linguagem principal
- Android Studio — IDE de desenvolvimento
- ViewBinding — Acesso seguro aos elementos de UI
- AIDL — Contrato de interface para comunicação entre processos
- ServiceConnection — Gerenciamento do ciclo de vida da conexão remota
- Threads — Execução de tarefas fora da Main Thread
- Material Design — Componentes de interface como Toolbar e Botões


## 📸 Estrutura do Ecossistema

##### O funcionamento deste projeto depende da interação entre dois aplicativos:

#### 01 - EntityServiceCommunication (Service)
O provedor que contém a lógica de negócio e hospeda o IncrementBoundService.

#### 02 - EntityServiceCommunicationClient (Client - Este repositório)
O front-end que fornece a interface para o usuário e consome o serviço de incremento.

> **Nota Importante:** Para que o incremento funcione, o aplicativo do Serviço deve estar instalado no dispositivo para que este Cliente possa localizar o componente via ComponentName.


## ▶️ Como Executar o Projeto

##### 1. Clone este repositório (Cliente):
###### git clone https://github.com/MADS1974/EntityServiceCommunicationClient.git
##### 2. Clone o repositório do Serviço (Obrigatório):
###### git clone https://github.com/MADS1974/EntityServiceCommunication.git
##### 3. Abra ambos os projetos no Android Studio.
##### 4. Instale primeiro o app do Serviço no seu dispositivo/emulador.
##### 5. Instale e execute este app (Cliente).
##### 6. Clique no botão de incremento para ver a comunicação AIDL em ação.


#### 📚 Créditos

##### Projeto acadêmico desenvolvido para a disciplina Desenvolvimento para Android 2 – D2DA2, ministrada pelo professor Pedro Northon Nobile (IFSP).

#### 🙋‍♂️ Autor
#### Márcio Adriano

##### 🔗 Conecte-se comigo:
##### LinkedIn - Márcio Adriano

##### Nota Técnica: Este projeto ilustra a utilização do sistema Binder do Android para realizar a comunicação entre diferentes espaços de endereçamento de memória (Sandboxes) de aplicativos distintos.
