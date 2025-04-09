# Objetivo

Esta prova de habilidades técnicas tem como objetivo avaliar suas capacidades individuais e seu raciocínio lógico na resolução de problemas.
Por esse motivo, solicitamos que todo o código apresentado seja de sua autoria, sem o uso de ferramentas de Inteligência Artificial (IA) para geração de código. Acreditamos que uma avaliação honesta de suas habilidades nos permitirá tomar a melhor decisão para ambas as partes.

Caso seja identificado o uso de IA na geração do código, sua participação no processo seletivo será automaticamente encerrada.

# Linguagens

Dê preferência ao uso de Vue 2 ou Vue 3. O uso de Nuxt é permitido. Caso não consiga desenvolver com essas tecnologias, utilize as linguagens de front-end com as quais você tem mais familiaridade.

# Cenário

Crie uma interface de usuário demonstrando o básico necessário para simular o design e as interações descritas abaixo.

## Design e Funcionalidades

Você pode visualizar o mockup da interface [aqui](./mockup.png).  

Cada bloco cinza abaixo de "Quadro de Servidores" representa um servidor no cluster.
O cluster deve ser iniciado com 4 servidores.

Sua interface deve conter uma implementação básica que reflita o design com a maior fidelidade possível.

## Crítérios de avaliação

- Todas as funcionalidades básicas estão funcionando.
- Código estruturado em componentes.
- Uso de boas práticas de programação.
- Proximidade visual com o mockup fornecido.
- Comentários explicativos no código.
- Funcionalidades extras implementadas e funcionando corretamente.

**Priorize a funcionalidade sobre a perfeição visual.
Este é um simulador funcional, e sem o comportamento básico implementado, a aparência visual se torna irrelevante.**

## Interações

Utilize seu julgamento para definir qualquer detalhe de interação que considere ausente.
Documente essas decisões no README, explicando o funcionamento e o motivo das escolhas feitas.

- Clicar em "Novo Servidor" deve criar um novo servidor e adicionar um novo bloco cinza no quadro.
- Clicar em "Destruir" deve remover o último servidor criado e o respectivo bloco cinza do quadro.
- Clicar no botão "+" de um dos "Apps Disponíveis" deve iniciar uma instância desse app no cluster.
- Clicar no botão "−" de um dos "Apps Disponíveis" deve encerrar a instância mais recente desse app no cluster.

### O que acontece quando você clica em "+" de um app?

Cada servidor pode rodar no máximo **2 apps simultaneamente**.
Quando um novo app é iniciado, ele deve ser alocado de acordo com o seguinte algoritmo:

- Iniciar no primeiro servidor executando 0 (zero) apps.
- Se todos os servidores estiverem executando ao menos 1 app, alocar no primeiro servidor com apenas 1 app.
- Se todos os servidores estiverem rodando 2 apps, o novo app não deve ser iniciado.

### O que acontece quando você clica em "Destruir"?

- Ao destruir um servidor, cada app nele alocado deve ser reiniciado em outro servidor do cluster, seguindo o algoritmo de alocação acima.
- Se não houver capacidade para realocar os apps, eles devem ser encerrados.

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

Se conseguir montar o simulador e ainda tiver tempo, sinta-se livre para adicionar melhorias e acabamentos que considerar interessantes. Algumas sugestões:

- Torne o quadro responsivo para telas com no mínimo 480px de largura.
- Adicione um delay com animação ao iniciar os apps, simulando o tempo de alocação e inicialização.
- Quando um segundo app for iniciado em um servidor, anime a divisão do bloco representando o servidor.
- Implemente um overlay nos servidores a ser exibido com hover e que possua o botão "Destruir" para destruir este servidor.
- Adicione animações de alerta quando não for mais possível destruir servidores ou apps.

### Artefatos para entrega

Envie um arquivo comprimido (zip, rar, tar, tar.gz etc) contendo o código fonte e um arquivo README.md explicando o passo a passo de como podemos inicializar e visualizar seu simulador.

Não é necessário incluir a pasta node_modules no seu zip.

Você pode utilizar bibliotecas ou recursos de terceiros que julgar apropriados.
Liste todas as bibliotecas utilizadas no README.md, junto com uma breve explicação de por que as escolheu.

**IMPORTANTE**  
Não comite seu código em nenhum repositório público.

Boa sorte
