# Cenário

Crie uma interface de usuário demonstrando o básico necessário para simulação do design e interações descritas abaixo.

## Design e Funcionalidades

Você pode ver o mockup da interface [aqui](./mockup.png).  

Cada bloco cinza abaixo de "Quadro de Servidores" representa um servidor no cluster.  
O cluster deve ser iniciado com 4 servidores.

**Priorize funcionalidade sobre perfeição do design.  
Isto é uma funcionalidade de demonstração e sem o funcionamento básico não importa o quão bonito está.**

Sua interface deve possuir uma implementação básica que reflita o design com a maior fidelidade possível.

## Interações

Use o seu julgamento para definir qualquer detalhe de interação que acredite estar faltando.  
Faça uma nota na documentação para explicar este funcionamento e suas decisões.

- Clicar em "Novo Servidor" deve criar um novo servidor e adicionar um novo bloco cinza no quadro.
- Clicar em "Destruir" deve remover o último servidor criado e também o bloco cinza correspondente  do quadro.
- Clicar no "+" de algum dos Apps Disponíveis deve iniciar uma instância deste app no cluster.
- Clicar no "-" de algum dos Apps Disponíveis deve encerrar a instância mais novo deste app no cluster.

### O que acontece quando você clica em "+" de um app?

Cada servidor pode rodar no máximo 2 apps ao mesmo tempo.  
Quando um novo app é iniciado, ele deve ser alocado seguindo o seguinte algoritmo:

- Iniciar no primeiro servidor executando 0 (zero) apps.
- Se todos os servidores estiverem rodando ao menos 1 app, o novo app deve ser iniciado no primeiro servidor rodando apenas 1 app.
- Se todos os servidores estiverem rodando 2 apps, o novo app não deve ser iniciado.

### O que acontece quando você clica em "Destruir"?

- Quando um servidor for destruído, cada app alocado neste deve ser reiniciado em outro servidor no cluster seguindo o algoritmo citado anteriormente.
- Se não houver capacidade para reiniciar os app em outro servidor, eles devem ser encerrados.

Exemplo:

```
servidor 1 contendo Hadoop e Rails
servidor 2 contendo Hadoop
servidor 3 contendo Chronos
```

Se clicar em destruir o resultado esperado será

```
servidor 1 contendo Hadoop e Rails
servidor 2 contendo Hadoop Chronos
```

## Crédito extra

Se você conseguir montar o simulador e tiver tempo extra, adicione melhorias e acabamentos que achar interessantes. Seguem algumas idéias:

- Faça o quadro responsivo para telas de, no mínimo, 480px de largura.
- Coloque um delay para iniciar os apps via animação para simular a alocação e tempo de inicialização.
- Quando um segundo app for iniciado no servidor, anime o particionamento do servidor em 2 pedaços.
- Implemente um overlay nos servidores a ser exibido com hover e que possua o botão "Destruir" para destruir este servidor.
- Coloque animações de alerta quando servidores ou apps não puderem mais ser destruídos.

### Artefatos para entrega

Envie um arquivo comprimido (zip, rar, tar, tar.gz etc) contendo o código fonte e um arquivo README.md explicando o passo a passo de como podemos inicializar e visualizar seu simulador.

Você pode utilizar recursos ou bibliotecas de terceiros que achar convenientes para o cenário dado.  Liste estas bibliotecas no arquivo README e uma explicação breve de por quê utilizou cada uma.

Desenvolva para browsers modernos e teste neles. Aconselhamos realizar testes no Chrome, Firefox e Safari.

**IMPORTANTE**  
Não comite seu código em nenhum repositório público.

Boa sorte
