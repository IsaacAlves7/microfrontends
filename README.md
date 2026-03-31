<a href="https://github.com/IsaacAlves7/microfrontends"><img width="100%" height="628" alt="170123_MICROFRONTEND_DESIGN" src="https://github.com/user-attachments/assets/6b3639b9-8128-4fe5-a448-75e5fc7348db" /></a>

> Versículo chave: "Consagre ao Senhor tudo o que você faz, e os seus planos serão bem-sucedidos." - Provérbios 16:3

# 🎨 MFE - Micro-Frontends
<img src="https://img.shields.io/badge/Figma-features-tomato?style=flat&logo=Figma&logoColor=white"> <img src="https://img.shields.io/badge/Vue.js-SPA-339933?style=flat&logo=Vue.js&logoColor=white"> <img src="https://img.shields.io/badge/Angular-SPA-CC342D?style=flat&logo=Angular&logoColor=white"> <img src="https://img.shields.io/badge/Angular-3.3-CC342D?style=flat&logo=Angular&logoColor=white"> <a href="https://blog.bitsrc.io/top-9-react-component-libraries-for-2025-a11139b3ed2e?source=post_page---author_recirc--df10edf0e8d0----0---------------------1744195f_55d3_428f_b6fa_370d3ddc78c4--------------"><img src="https://img.shields.io/badge/React-SPA-00ADD8?style=flat&logo=React&logoColor=white"></a> <a href=""><img src="https://img.shields.io/badge/Vite-23-violet?style=flat&logo=Vite&logoColor=white"></a> <img src="https://img.shields.io/badge/Blazor-8.0.300-512BD4?style=flat&logo=Blazor&logoColor=white"> <img src="https://img.shields.io/badge/Svelte-SPA-orange?style=flat&logo=Svelte&logoColor=white">

<img src="https://em-content.zobj.net/source/microsoft-teams/400/artist-palette_1f3a8.png" align="right" height="77">

**Micro-frontend** é uma abordagem de arquitetura de software para desenvolvimento web inspirada em padrões de <a href="https://github.com/IsaacAlves7/microservices/">microsserviços</a>. Ou seja, estamos construindo aplicativos componíveis de forma orquestrada e escalável usando uma plataforma de desenvolvimento orientada a componentes (CDD - Component-Driven Development). Ao longo da minha carreira, testemunhei os desafios das arquiteturas monolíticas de front-end e o poder transformador dos microfront-ends.

Talvez você já tenha ouvido falar sobre o conceito de microserviços. Aquele negócio de dividir o back-end em partes menores, cada um com sua responsabilidade (SOLID). Porém, no front-end ainda é muito comum o uso de monolitos. 

Mas e se quisermos dividir também o front-end em partes menores e independentes, pois o desenvolvimento de softwares para web está em constante mudança, para acompanhar as crescentes demandas de escalabilidade, manutenção e performance. Nesse sentido, uma das grades evoluções é o conceito de Aplicações _Micro Front-end_.

A técnica de **micro front-end** se baseia na fragmentação de projetos extensos e complexos (conhecidos como monolitos) em elementos menores e mais simplificados. Esses elementos podem ser desenvolvidos, implantados e mantidos independentemente uns dos outros, enquanto são apresentados ao usuário final como um produto único e integrado. 

Micro frontends são uma abordagem de desenvolvimento frontend que divide uma aplicação em componentes menores, independentes e reutilizáveis, que podem ser desenvolvidos, testados e implantados separadamente. Essa abordagem, inspirada nos microserviços do backend, permite que diferentes equipes trabalhem em partes distintas da aplicação, acelerando o desenvolvimento e melhorando a escalabilidade. 

Aposto que você conhece essa história – seja pela sua própria experiência, ou por vários casos semelhantes descritos por toda a Internet. Quando entrei nesse projeto, o poder do espaguete já era forte nele. Só deixamos mais forte, adicionando cada vez mais camadas de macarrão por cima. Com o tempo, ficou cada vez mais difícil adicionar um recurso sem causar bugs, os lançamentos demoravam cada vez mais, a plataforma ficou cada vez menos estável e, eventualmente, ficamos travados.

Naquela época, levávamos uma semana inteira para enviar uma nova versão do nosso aplicativo dos computadores dos desenvolvedores para os usuários finais – tínhamos um lançamento por semana. Hoje em dia, podemos colocar praticamente qualquer parte da lógica de negócio ou interface do usuário, dos computadores dos desenvolvedores, para produção em menos de 30 minutos, claro, sem omitir nenhuma das etapas padrão do processo de lançamento, como integração ou testes de ponta a ponta. Conseguimos fazer isso com – na verdade, ainda em andamento – a transformação da arquitetura monolítica para a orientada a serviços, mas não seria possível fazer isso totalmente sem estender essa ideia para o desenvolvimento frontend. E é sobre isso que este artigo trata – estender a ideia de arquitetura orientada a serviços (SOA) para o desenvolvimento frontend – uma abordagem frequentemente chamada de "microfrontends".

Como mencionei, a ideia de microfrontends é a extensão direta da ideia de arquitetura orientada a serviços para o desenvolvimento frontend. Portanto, analogicamente a serviço ou microserviço, microfrontend é uma parte pequena e logicamente separada da sua aplicação, ou mais precisamente, no contexto do desenvolvimento frontend, parte da interface do usuário da sua aplicação. Parte, que, antes de tudo, é independente do restante do seu sistema em termos de implantação. Além disso, o microfrontend deve encapsular alguma parte da lógica de negócio da sua aplicação e deve ser exclusivamente de propriedade de uma equipe responsável por essa parte da aplicação de ponta a ponta.

A arquitetura microfrontend seria então um estilo arquitetônico onde aplicações frontend entregáveis de forma independente – microfrontends – são compostas e servidas ao usuário final como uma única aplicação completa e coerente.

Quão micro é microfrontend? Resumindo, o microfrontend deve ser tão pequeno quanto faz sentido. Assim como na arquitetura orientada a serviços, também microfrontends vêm com trade-offs claros. Entidades menores são mais fáceis e rápidas na implantação, mas dividir uma entidade em várias significa necessidade de mais processos de implantação, automação, integração e também mais dependências entre elas. Uma entidade grande é mais fácil de manter como um todo, mas vem com o custo da falta de separação – pode se tornar menos legível, levar mais tempo para ser testada e implantada, ou combinar diferentes áreas lógicas em si mesma, levando à falta de propriedade clara.

No nosso sistema, temos microfrontends que variam muito em tamanho. A maioria deles são pequenos widgets únicos – dezenas dos quais seriam combinados em uma única visão – mas também há muitos exemplos de microfrontends que representam páginas inteiras ou até coleções de páginas logicamente relacionadas entre si.

Ao decidir o tamanho do microfontend, levamos em conta vários fatores.

Reutilização: A primeira pergunta a se fazer seria: "esse elemento deve ser reutilizado em diferentes visões separadas?". Se sim, não vale a pena duplicar o código dela em todos esses lugares. Em vez disso, deveria se tornar uma entidade separada com uma única fonte de verdade e integrada a essas visões separadamente.

No entanto, é bastante comum que não seja exatamente a mesma microfonte em diferentes vistas, mas sim algum tipo de variação. Nesses casos, tomamos decisões com base na quantidade e gravidade dessas diferenças. Para pequenas diferenças entre variantes, mantemos tudo como um só e tornamos os elementos variados configuráveis. Quanto mais configuração for necessária, mais variantes diferentes são e maior a probabilidade de que sejam microfrontends separados.

Também é importante, neste caso, considerar o contexto em que essa parte será usada por outros. A principal questão é: se você, como proprietário desse elemento, quiser fornecer uma única fonte de verdade sobre ele – então você tem controle total sobre qual das versões é usada por todos os consumidores, mas você é responsável por fazer funcionar para todos – ou quer dar escolha a outros – então você passa essa responsabilidade para eles, Mas você não pode controlar qual versão eles usam e não pode fazer com que migrem para a mais nova quando você a encontrar pronta.

Propriedade
Outro motivo para criar microfrontends separados seria baseado na resposta à pergunta: "esse elemento se estende por diferentes áreas lógicas pertencentes a equipes separadas?". Se sim, isso quebra a regra da propriedade única e clara, portanto deve ser dividido em elementos menores, cada um designado para equipes específicas responsáveis pela área correspondente.

É importante que cada microfrontend seja propriedade de uma única equipe que se interessa por áreas lógicas relacionadas a esse microfrontend. No entanto, com o tempo, muitas vezes adicionamos mais e mais funcionalidades aos nossos widgets e aplicações, e às vezes eles acabam combinando recursos de diferentes áreas. Quando percebemos que um determinado elemento inclui lógica de negócios que deveria ser responsabilidade de outra equipe, ele se torna um bom candidato para fatiamento.

Raramente é cortado ao meio, porém. Na maioria das vezes, é uma relação bastante hierárquica: participamos de encapsular esse recurso e o tornamos um microfrontend separado, fornecendo essa funcionalidade, passamos a propriedade para outra equipe e colocamos dentro do espaço deles, depois nos referimos a ela das aplicações principais, que se tornam meio que consumidores.

Normalmente, já estamos cientes desse tipo de situação antes do código ser enviado para produção – perceber que você está desenvolvendo fora da sua área de especialização não exige nenhuma mágica. Por isso, tentamos fazer da maneira certa desde o início, o que significa solicitar essa funcionalidade à equipe responsável pela área relacionada. No entanto, pode não ser possível obtê-lo em tempo razoável – afinal, eles podem estar ocupados com outras coisas.

Depois, podemos implementar para eles, tanto quanto nosso conhecimento limitado permitir, e colocar diretamente na infraestrutura deles criando pull request. Ainda exige algum trabalho deles – revisá-lo e propor melhorias, provavelmente mais do que poucas, já que estamos desenvolvendo na área deles e tentando nos conformar aos padrões deles – trabalho, pelo qual também teríamos que esperar por um tempo às vezes inaceitável.

Portanto, tais candidatos para divisão estão sendo criados, e estamos perfeitamente de acordo com eles, desde que sejam marcados como dívida técnica, que planejamos pagar de forma transparente no futuro próximo.

Tamanho puro
Por último, mas não menos importante, há candidatos a serem divididos em entidades menores devido ao seu tamanho: "esse elemento começa a apresentar problemas semelhantes aos que as aplicações de monólitos têm?". Se sim, esse é mais um motivo para considerar a divisão em entidades separadas.

Algumas de nossas aplicações não possuem elementos que possam ser reutilizados e se encaixem perfeitamente na responsabilidade de uma única equipe, mas as dividimos em menores porque o desenvolvimento e a manutenção começam a se tornar um problema. É uma métrica totalmente subjetiva, baseada no instinto do desenvolvedor e em algumas estatísticas, geralmente relacionadas à escalabilidade ou lançamento desse software.

Em outras palavras, se planejarmos escalar certa parte do microfrontend de forma diferente do resto – por exemplo, uma parte do aplicativo será acessada em tempo de execução por 1 usuário por minuto, e outra por 1000 usuários por minuto – é melhor que essas partes sejam separadas. Se o lançamento se tornar problemático, levar muito tempo, resultar em alguns bugs e geralmente se tornar pouco confiável – também é melhor dividir esse elemento em outros menores, embora nesse caso seja menos óbvio onde traçar limites.

Na prática: Um bom exemplo de partes altamente fragmentadas da aplicação seriam a página inicial ou dashboards de algum tipo – eles frequentemente combinam elementos que também são visíveis em outras páginas.

<table>
  <tr>
    <td><a href="https://codepen.io/your-work"><img src="https://github.com/user-attachments/assets/3bb5bd0c-6941-4a95-80e7-6f3ba9d1f479" align="right" height="377"></a></td>
    <td><img src="https://github.com/user-attachments/assets/9335f5b7-b920-4dc8-aff1-7d27226bb0fd" align="right" height="477"></td>
  </tr>
</table>

Um exemplo de aplicação simples de página única seria, no nosso caso, a página de edição do perfil do usuário. É uma página com várias seções editáveis, onde o usuário pode fornecer diferentes tipos de informações relacionadas à sua educação e carreira profissional. É um app inteiro, nenhuma de suas partes é usada em outra visão, se encaixa na responsabilidade de uma equipe única e não observamos nenhum problema causado pelo seu tamanho.

Por fim, existem aplicações de página única que encapsulam várias páginas – como editor de ofertas de emprego, com as quais os recrutadores podem convenientemente configurar todo tipo de conteúdo que depois é consultado pelos candidatos. Esse aplicativo é muito mais sofisticado do que a página de edição do perfil do usuário, pois há muito mais tipos de informações para serem disponibilizadas. Ele vem com várias páginas diferentes e seu próprio roteamento. Ainda assim, em nossa arquitetura, é um microfrontend – não reutilizado em outras partes do sistema, pertencente a uma equipe, lançado como um todo.

Claro, nenhum desses exemplos certamente permanecerá nesse estado no futuro – seu tamanho depende das necessidades do negócio e do que encontramos funcionando para nós no desenvolvimento e manutenção no momento. Os requisitos vão mudar, o ambiente vai mudar, nossas preferências vão mudar, então a configuração de microfrontends específicos também vai mudar. Precisamos levar em conta tudo o que sabemos quando começamos e adotar a solução mais simples possível. Portanto, assim como na arquitetura de toda a aplicação, também com microfrontends específicos, geralmente começamos com pequenos monólitos, a menos que saibamos previamente que existem requisitos para reutilização, recursos de multiequipes ou outras contraindicações.

No geral, não existe uma regra de ouro quando se trata de tamanho de microfrontend, e não confie em ninguém dizendo que frontends mais "micro" ou mais "macro" são melhores. Confie em si mesmo e no seu julgamento. Pese prós e contras e decida dividir uma parte específica da sua aplicação em menores sempre que achar mais útil para você.

Micro frontends vieram para ficar! Micro frontends oferecem uma solução promissora para esse problema, proporcionando uma forma mais eficiente e gerenciável de construir aplicações web complexas. À medida que as empresas continuam a exigir aplicações web mais rápidas e ágeis, os desenvolvedores precisam adotar essa nova abordagem. Seja você construindo uma pequena startup ou uma grande aplicação empresarial, com as ferramentas e a abordagem certas, você pode criar aplicações web que sejam escaláveis, mantidas e, mais importante, amigáveis para o usuário.

> [!Tip]
> "Ajudar desenvolvedores a trabalharem de forma mais inteligente e rápida, com uma abordagem compartilhável e de blocos de construção para criar experiências consistentes é central para o foco moderno e centrado no cliente da Dell Digital. Compartilhar componentes capacita os desenvolvedores a desenvolver e lançar recursos de forma mais rápida e consistente. Eles podem publicar e acessar componentes e recursos de UX aplicáveis em diversas experiências digitais.
>
> Antes, os desenvolvedores ficavam realmente frustrados por ter que escrever aparentemente um milhão de linhas de código repetidamente, descobrindo detalhes e fazendo os testes. Com componentes prontamente disponíveis, agora podem se desenvolver e entregar em um quarto do tempo que levavam antes. Agora eles podem investir em um desenvolvimento de recursos mais inovadores." <a href="https://www.dell.com/en-us/blog/a-shared-building-block-approach-to-better-user-experience/">Líder de Transformação Tecnológica na Dell, Bit Platform</a>

Exemplo: Na StepStone Services, estamos trabalhando na manutenção e desenvolvimento de uma plataforma grande e complexa para quadros de empregos, entre outras coisas. Esse projeto inicialmente seguia a arquitetura monolítica e permaneceu assim por muitos anos. No entanto, para combater certos problemas causados por essa abordagem, foram empregadas arquiteturas orientadas a serviços no lado backend e arquitetura microfrontend no lado frontend. Neste artigo, descrevo nossa forma de fazer microfrontends, o que aprendemos com isso até agora e ferramentas e técnicas que nos ajudam a criar e manter essa arquitetura de software sofisticada.

Entrei na StepStone Services há quatro anos como engenheiro de software para trabalhar na manutenção e desenvolvimento do nosso produto principal – o portal de vagas online. Sabe, esse tipo de site, onde o usuário pode buscar ofertas de emprego interessantes com base em certos critérios, navegar, ler, se candidatar se quiser, e muito, muito mais.

O projeto acabou sendo um pouco mais complexo do que eu esperava – tanto em termos de lógica de negócios e número de funcionalidades, quanto em termos de solução técnica e arquitetura. Basicamente, era um grande repositório com alguns milhões de linhas de código, escrito sem muita atenção à separação de código, modularidade ou legibilidade.

<table>
  <tr>
    <td><img height="692" alt="Captura de tela 2025-11-18 143946" src="https://github.com/user-attachments/assets/1fdae87d-deae-41e7-be47-fa7c54e9f9c8" /></td>
    <td><img height="692" src="https://github.com/user-attachments/assets/55945ea7-7c16-4ad8-bf35-9490acb9ec2a"></td>
  </tr>
</table>

<a href="https://medium.com/better-programming/the-future-of-micro-frontends-2f527f97d506">Micro frontends</a> são uma abordagem arquitetônica poderosa para gerenciar a complexidade de aplicações empresariais modernas. Ao atender aos principais requisitos de desenvolvimento desacoplado, versionamento independente, atualizações incrementais, implantações independentes, integração em tempo de execução, componentes compartilhados, desenvolvimento colaborativo e equipes autônomas, as organizações podem alcançar uma arquitetura frontend altamente modular e escalável. A Bit and Webpack Module Federation oferece um conjunto robusto de ferramentas para apoiar esses objetivos, capacitando as equipes a inovar mais rápido e entregar experiências excepcionais ao usuário em um cenário digital em rápida evolução.

Micro frontends estão mudando fundamentalmente a forma como construímos e escalamos frontend. Ao dividir frontends monolíticos em partes menores e mais gerenciáveis, as equipes podem desenvolver, implantar e atualizar componentes de frontend de forma independente, o que aumenta a escalabilidade e a flexibilidade. 

Aplicações criadas com abordagem de microfrontends para o usuário final podem parecer um site comum, enquanto no fundo podem ser construídas como uma composição de microaplicações separadas. Cada uma dessas aplicações tem sua própria base de código e repositório, seu próprio pipeline para passar esse código de ambiente em ambiente, sua própria versão em cada um desses ambientes em determinado momento, e sua própria equipe responsável por essa área de ponta a ponta. Funciona perfeitamente para o modelo Spotify Squad + Lean Startup + Metodologias Ágeis:

<table>
  <tr>
    <td><a href="https://blog.bitsrc.io/component-driven-development-and-composable-applications-a-guide-7a0934e60936"><img src="https://github.com/user-attachments/assets/53f7ba2c-3f7f-4624-8563-885b97210803" height="777"></a></td>
    <td><img height="577" alt="microfrontend-app-in-development" src="https://github.com/user-attachments/assets/1d48f502-9eba-4ec9-b7ea-080e3e8c5681" /></td>
  </tr>
</table>

A ideia desse tipo de separação de código não é novidade – apenas em relação ao desenvolvimento web frontend já havia abordagens semelhantes descritas no passado, como "aplicações verticalmente decompostas", "sistemas autônomos" ou "sites de microserviços" – mas com o surgimento da arquitetura orientada a serviços e microserviços nos últimos anos, essa abordagem, desta vez chamada de "microfrontends", está ganhando muita popularidade e sendo amplamente adaptada. Você pode encontrar muitas palestras e artigos dos últimos anos vindos de empresas como Microsoft, Spotify ou Zalando, onde descrevem suas experiências com o desenvolvimento de seus produtos com essa arquitetura.

À medida que as aplicações empresariais se tornam complexas, adotar micro frontends é fundamental para manter a agilidade e acelerar os ciclos de desenvolvimento. As aplicações de micro front-end estão transformando a forma como abordamos o desenvolvimento web. Ao dividir o front-end monolítico em partes menores, ganhamos vantagens em escalabilidade, manutenção e velocidade de desenvolvimento. Esses benefícios capacitam equipes a trabalhar de forma eficiente, colaborativa e a manter a competitividade em um cenário digital em constante evolução.

Antes do Desenvolvimento Orientado por Componentes (CDD) e do desenvolvimento de aplicativos composáveis (CAD - Composable App Development), a cadeia de ferramentas monolítica orientada a projetos tornava o processo de escalar o desenvolvimento de múltiplos produtos e equipes muito desafiador. Cada aplicação foi desenvolvida como um projeto de código compartimentado, com todas as suas funcionalidades como implementação interna de código, altamente acoplada a um projeto específico, dificultando separar, compartilhar e atualizar diferentes partes da aplicação em todo o sistema.

Soluções corrigidas exigiam muita flexibilização de arquitetura, ferramentas adicionais construídas e integradas, e criavam problemas complexos como compartilhamento de código, controle de versões, gerenciamento de dependências, atualizações etc. Cada projeto ficou mais difícil de escalar à medida que mais recursos e desenvolvedores se juntaram, enquanto as organizações não tinham uma forma eficaz de compartilhar componentes, colaborar em mudanças e orquestrar atualizações. Como resultado, os desenvolvedores tiveram que escrever o mesmo código repetidamente, levando a um enorme desperdício de tempo e recursos e a experiências de produto inconsistentes. Como resultado, as organizações experimentaram uma diminuição do ROI no desenvolvimento de software.

![1_JzDawgQIj9TGcI6CyUeJkA](https://github.com/user-attachments/assets/c813bec6-ce3b-46d7-a105-4ad30644ed9b)

CDD é uma abordagem evolutiva componível para o desenvolvimento moderno de software. Ele define um padrão de design arquitetônico que resolve desafios fundamentais que atrasaram o desenvolvimento de software por décadas, por meio da composabilidade e modularidade para o desenvolvimento de aplicações.

Base de plataforma composável OSS: Composable Platform

<table>
	<tr>
		<td><img src="https://github.com/user-attachments/assets/5534800c-3834-42c3-a06e-36aaeca07c9a"></td>
		<td><img src="https://github.com/user-attachments/assets/b56b7550-3ca1-4ae0-ae6e-8f62988afdd6"></td>
	</tr>
</table>

CDD define uma arquitetura componível onde as aplicações são compostas como Lego por meio de blocos de construção menores, independentes e reutilizáveis — componentes. CDD é uma abordagem baseada em reutilização; os componentes são compartilhados e gerenciados como blocos de construção e disponibilizados para todas as equipes e produtos da organização, para serem reutilizados e orquestrados de forma eficiente em escala.

Os componentes podem ser desde interfaces simples até recursos, micro-frontends, experiências completas do usuário, aplicativos, utilitários e até lógica front-end e backend. Ao dividir o desenvolvimento em componentes fracamente acoplados, o desenvolvimento pode ser distribuído entre as equipes e os componentes se tornam ativos reutilizáveis que são compartilhados e orquestrados entre os produtos.

Os benefícios da composabilidade e do CDD são revolucionários no curto e longo prazo:

1. **Velocidade de entrega**: Componentes reutilizáveis permitem que desenvolvedores acelerem o desenvolvimento e reduzam o tempo de desenvolvimento em 80% em novos produtos — pois não precisam reescrever código, tomar decisões e repetir o trabalho repetidamente (veja Estudo de Caso Dell com Bit).

2. **Consistência do produto**: Componentes reutilizáveis proporcionam consistência ideal no código, design e experiência do usuário em todos os produtos e experiências digitais da organização.

3. **Eficiência e ROI**: Com componentes reutilizáveis, os desenvolvedores não precisam escrever o mesmo código repetidamente, reduzindo os custos de desenvolvimento por aplicativo em até 80%. Cada componente é construído uma vez e se torna um ativo compartilhado com valor composto (veja estudo de caso sobre ROI).

4. **Equipes autônomas e entrega rápida** — Equipes especialistas em domínio podem possuir, desenvolver e enviar componentes de forma autônoma para diferentes responsabilidades de negócios (por exemplo, "UI", "Pagamentos" etc.), permitindo entrega rápida e resposta rápida a necessidades emergentes.

5. **Arquitetura escalável e mantível** — Um sistema de aplicativo componível construído com componentes é altamente modular e pode ser mais facilmente mantido e escalado. Com uma plataforma CDD, os componentes podem ser compartilhados, atualizados e orquestrados em todo o sistema.

- **Benefícios adicionais incluem um planejamento mais inteligente** — quando surgem novas necessidades, arquitetos e desenvolvedores decidem se ampliam os componentes existentes ou criam novos;
- **Produtos de Maior Qualidade** — O reuso de componentes previne a maioria dos bugs e erros, e a qualidade dos produtos de software melhora significativamente;
- **Personalizações de experiência** — cada experiência pode ser facilmente customizada com diferentes versões para otimizar diferentes jornadas do usuário, mesmo em grande escala;
- **colaboração multifuncional** — designers, desenvolvedores e todas as partes interessadas podem planejar e participar ativamente do processo de desenvolvimento diretamente sobre componentes reais do aplicativo;
- **agilidade de desenvolvimento** — CDD melhora a agilidade ao dividir decisões e entregas para o nível de componente;
- **governança e visibilidade** — os líderes obtêm uma visão de raio-x dos ativos tecnológicos disponíveis da organização e podem acompanhar o uso e o impacto dos componentes e iniciativas na organização;
- **Padronização e modernização** — com CDD, o desenvolvimento é padronizado desde as tecnologias usadas pelos componentes até seu processo de lançamento. Novos recursos podem ser adicionados a aplicativos legados em um processo sempre verde;
- **Integração mais rápida** — Integrar desenvolvedores em novos produtos é mais rápido quando eles só precisam trabalhar em componentes.

Embora o CDD possa existir em pequenos bolsões sem uma plataforma de suporte, a compostabilidade em escala requer uma variedade de soluções para maximizar o ROI e garantir uma experiência sem atritos.

O desenvolvimento de CDD e aplicativos componíveis exige uma longa lista de capacidades para ser bem-sucedido e escalável. Como as ferramentas antigas não foram criadas para desenvolvimento orientado a componentes desde o início, o esforço, o tempo, o custo e o risco de complexidade de construir e manter uma solução alternativa completa são enormes.

Embora o conjunto de ferramentas de desenvolvimento orientado a projetos do passado não ofereça as capacidades necessárias para facilitar esse novo tipo de desenvolvimento, plataformas dedicadas e cadeias de ferramentas como a Bit fornecem um conjunto completo de soluções em um único fluxo de trabalho escalável.

Uma plataforma dedicada estabelece as bases para que CDD e composabilidade sejam aplicadas e escaladas com sucesso, ao mesmo tempo em que fornece todas as capacidades necessárias em um único fluxo de trabalho. Isso reduz o tempo e o custo de construir e corrigir ferramentas para resolver uma longa lista de capacidades (que pode levar anos e milhões de dólares), e elimina o risco de enfrentar desafios e questões complexas.

**Capacidades necessárias de uma plataforma de CDD e composição de aplicativos**: Para permitir o desenvolvimento bem-sucedido de aplicações por meio de componentes componíveis e escalar esse processo de forma eficaz na organização, é necessária uma longa lista de capacidades críticas.

**Component-based** é uma abordagem de arquitetura de software onde os sistemas são construídos a partir de unidades modulares e reutilizáveis chamadas **componentes**. Cada componente é uma entidade funcional independente, encapsulando dados, lógica de negócio e comportamento, podendo ser desenvolvido, testado e mantido de forma isolada. O principal objetivo do component-based é promover reutilização, manutenção facilitada, escalabilidade e separação de preocupações. Em vez de criar sistemas como blocos monolíticos de código interdependente, o component-based permite montar aplicações como se fossem conjuntos de peças de Lego, onde cada peça realiza uma função específica e pode ser substituída ou atualizada sem impactar o todo, desde que sua interface permaneça a mesma.

Na prática, os componentes possuem interfaces bem definidas e comunicam-se entre si de forma controlada, muitas vezes por meio de eventos, injeção de dependência ou contratos formais de dados. Isso os torna altamente portáveis e adaptáveis a diferentes contextos. No front-end, esse conceito é amplamente adotado em frameworks como React, Angular e Vue, onde cada parte da interface — como botões, formulários ou tabelas — é um componente reutilizável. No back-end, esse paradigma também pode ser aplicado através de serviços encapsulados ou bibliotecas modulares que se integram em uma arquitetura maior. Em ambientes mais complexos, os componentes podem evoluir para microcomponentes ou micro frontends, refletindo a mesma filosofia de modularidade.

Além disso, o desenvolvimento baseado em componentes favorece a testabilidade e o versionamento granular, pois cada unidade pode ser testada isoladamente e evoluída de forma segura. Também incentiva a colaboração entre equipes, permitindo que diferentes grupos trabalhem em diferentes componentes sem conflitos, o que é crucial em projetos grandes e distribuídos. No entanto, adotar component-based exige disciplina em design, pois é necessário definir interfaces estáveis, evitar acoplamentos desnecessários e gerenciar bem a comunicação entre os módulos. Quando bem aplicado, o component-based resulta em sistemas mais flexíveis, organizados e fáceis de escalar, permitindo evoluções constantes sem comprometer a estrutura já existente.

<img width="629" height="442" alt="dan-abramov-on-reasons-behind-microfrontends" src="https://github.com/user-attachments/assets/a95a7d46-b849-42f6-8e7f-450a53eadefd" />

![1762133418361](https://github.com/user-attachments/assets/faa841f0-3e46-4e45-ab93-12bfeaaae932)

Voltando aos tweets de Dan Abramov, ele sugeriu que os problemas resolvidos por essa abordagem já deveriam ser resolvidos por algo mais simples, como um bom modelo de componentes, portanto deve ser sobre outra coisa. Talvez resolvendo problemas organizacionais? Concordo parcialmente com isso. Na nossa experiência, isso não resolve necessariamente problemas desse tipo, mas requer uma configuração específica em nível organizacional por design, o que pode ser benéfico para você.

<table>
  <tr>
    <td><img height="1001" alt="Microfrontends_architecture-1024x1001" src="https://github.com/user-attachments/assets/982f79e5-c34b-4f9a-afeb-99a804ba6696" /></td>
    <td><img height="1001" alt="Microfrontends_architecture-1024x1001" src="https://github.com/user-attachments/assets/d1c13573-0b72-4641-aee3-b6fb1c5c6570" /></td>
  </tr>
</table>

<img width="1024" height="576" alt="immagine-1-1024x576" src="https://github.com/user-attachments/assets/74680d33-4561-455b-b939-54e1537180ff" />

<img width="655" height="281" alt="mfe-architectures-with-bff" src="https://github.com/user-attachments/assets/e48cdf63-87b0-4ada-9b4e-186be7f014b7" />

Deixe-me mostrar o que quero dizer. Suponha uma aplicação que consiste em armazenamentos independentes dedicados a serviços backend, que são então conectados aos seus próprios serviços frontend, e então há essa camada fina de composição por cima de tudo. É assim que a arquitetura da aplicação em que estou trabalhando se parece, é claro, representada de forma muito, muito simplificada. Quando colocamos isso no contexto da nossa organização e adicionamos equipes a esse diagrama, alguns dos benefícios dessa abordagem ficam muito claros.

<img width="1280" height="1337" alt="microfrontend-app-architecture-with-teams" src="https://github.com/user-attachments/assets/9b9a56a3-d289-4812-853e-303136164b02" />

Arquitetura de aplicativos microfrontend com equipes

Como você pode ver, dada essa separação de código, áreas separadas podem ser controladas de ponta a ponta por equipes distintas. Isso significa que você pode ter equipes pequenas e autônomas, fortemente focadas no cliente. Quase todo membro de cada equipe tem algum impacto nos usuários finais reais e pode observá-lo. Isso naturalmente aumentou a dedicação, o compromisso e a satisfação desses membros da equipe.

Também permite que as equipes trabalhem com um escopo muito reduzido. Veja, no caso da nossa aplicação, o domínio empresarial ficou simplesmente grande demais para que uma pessoa só soubesse tudo. Por isso, dividimos em áreas estreitas e logicamente separadas – subdomínios – e as atribuímos a equipes separadas para serem responsáveis de ponta a ponta. Agora, desenvolvedores de cada uma dessas equipes podem realmente se tornar especialistas em sua parte do domínio. Ter um entendimento profundo dos aspectos relacionados aos negócios e técnicos da área se traduz em qualidade muito melhor do código produzido e das soluções projetadas por essa equipe.

Ambos esses benefícios, combinados com a suposição principal dessa arquitetura – que você pode implantar pequenas partes da sua aplicação para viver de forma rápida e inofensiva – impactam diretamente a velocidade e agilidade do seu desenvolvimento. Imagine que você tem uma equipe pequena e focada, cheia de especialistas no que estão fazendo, que pode enviar coisas para produção em meia hora. Esse ambiente incentiva pequenas mudanças, frequentemente iterações, experimentos – basicamente tudo o que está encapsulado no termo "desenvolvimento ágil de software". É isso que queremos – ser ágeis – então é isso que fazemos.

Além disso, tendo sua aplicação logicamente separada por design, você pode minimizar o risco que vem com a inevitável substituição de suas partes por outras totalmente novas – você conhece todas as dependências de antemão, em vez de descobri-las durante o desenvolvimento. Graças a isso, podemos refatorar nossa aplicação de forma graciosa e progressiva parte por parte, onde e quando fizer mais sentido.

Quero que você tenha algumas coisas em mente, enquanto eu me gabo de todos esses prós. A primeira coisa é o fato de que arquitetura é uma ferramenta. Ferramenta projetada para resolver e corrigir de forma eficiente certos problemas específicos. Essa ferramenta funciona para nós porque resolve os problemas que temos – ela não foi feita para ser usada por todos, em todos os lugares.

Na verdade, é bastante comum começar com o monolito em vez disso. O Monolith é um padrão de arquitetura bom, sólido, mais importante, simples, que simplesmente cumpre o seu papel. A verdade é que a maioria das aplicações criadas hoje nunca crescerá em tamanho a ponto de precisar desse escalonamento por decomposição.

Quando se trata especialmente da arquitetura microfrontend, provavelmente o problema mais comum apontado é o potencial, que prejudica a fragmentação dos processos de desenvolvimento, tecnologias, soluções e, eventualmente, da própria aplicação. O risco é que o aumento dramático da autonomia das equipes leve à diminuição da eficácia e à falta de consistência da aplicação.

O risco é válido, se você me perguntar – já passamos por esse problema em várias ocasiões diferentes. No entanto, acho que equipes autônomas e totalmente responsáveis por si mesmas é algo positivo – e nossos desenvolvedores tendem a confirmar que esse modelo funciona para eles. Existem maneiras de mitigar esse risco, principalmente padronização e automação de várias etapas nos processos de desenvolvimento de software, que serão discutidas mais adiante neste artigo. Basicamente, trata-se de encontrar um bom equilíbrio entre essa autonomia das equipes e padrões comuns compartilhados entre elas.

<img width="1548" height="854" alt="client-side-edge-side-server-side" src="https://github.com/user-attachments/assets/c2b9a93b-98b6-4e90-9a5d-46392b0fb9fe" />

Também é importante levar em conta o tamanho equilibrado e sensato de cada microfontend. Ao contrário de algumas crenças, que na minha opinião tornam esse risco de fragmentação um pouco exagerado, nem toda parte da interface precisa ser uma entidade separada. Naturalmente, quanto mais fragmentada for sua aplicação, maior o risco que vem com essa fragmentação, mas a abordagem microfrontend pode ser aplicada com diferentes níveis de fragmentação, o que é outra forma de gerenciar essa potencial responsabilidade.

Esse diagrama está mostrando **onde e como os Microfrontends (MFE)** podem ser compostos dentro de uma arquitetura — e a confusão é normal, porque aqui não é só “o que é MFE”, mas **onde eles vivem no fluxo da aplicação**.

Microfrontend, no fundo, é pegar a ideia de microsserviços (dividir o backend em partes independentes) e aplicar no frontend. Em vez de ter um único front gigante, você quebra em vários “mini-frontends”, cada um responsável por uma parte da UI e geralmente mantido por times diferentes, podendo até usar tecnologias diferentes como React, Angular ou Vue.js.

Agora, sobre a imagem: ela mostra três formas principais de compor esses MFEs.

No **client-side**, tudo acontece no navegador. O usuário carrega uma aplicação base (tipo um shell) e, a partir daí, os MFEs são carregados dinamicamente via JavaScript. Isso é muito comum com coisas como Module Federation ou frameworks de microfrontend. Aqui, o browser é quem junta tudo. A vantagem é flexibilidade e independência de deploy; a desvantagem é que pode pesar mais no cliente e impactar performance inicial.

No **edge-side**, a composição acontece antes de chegar no navegador, mas não exatamente no backend tradicional — e sim numa camada intermediária, tipo CDN inteligente ou edge functions. Ferramentas como Cloudflare ou Akamai conseguem montar partes da página vindas de diferentes MFEs e entregar já “quase pronta”. Isso melhora performance e mantém certa independência entre times.

No **server-side**, quem junta tudo é o backend. Ele busca os pedaços dos MFEs e monta a página final antes de enviar pro cliente, algo parecido com SSR (server-side rendering). Aqui você tem mais controle e performance previsível, mas perde um pouco da independência total entre os times, porque existe uma orquestração central.

O que o desenho também sugere é que os MFEs podem existir em vários níveis: na origem (cada app independente), no CDN (cacheados ou parcialmente montados) e no cliente (render final). Ou seja, não é um lugar fixo — é um **pipeline de composição**.

O ponto mais importante pra você entender de verdade é: Microfrontend não é só tecnologia, é **estratégia organizacional**. É sobre permitir que times diferentes desenvolvam, deployem e escalem partes da interface de forma independente, sem depender de um monolito frontend.

Se você quiser conectar isso com o que você já trabalha (microservices, RabbitMQ, etc.), pensa assim: cada MFE seria como um “consumer visual” de um domínio específico. Um cuida de pagamento, outro de perfil, outro de dashboard — tudo independente, mas compondo a mesma aplicação.

<img width="742" height="601" alt="mfe-architectures" src="https://github.com/user-attachments/assets/a5c52db7-8a33-4d4b-9225-a8a57037bffb" />

Aqui você já está olhando com um nível mais avançado, esse desenho já não está mais focado em “onde renderiza”, mas sim em **como os MFEs se conectam com o backend**, e aí entra forte o padrão de **BFF (Backend for Frontend)**.

O que essa imagem sugere é que você tem vários **microfrontends independentes**, mas todos eles conversam com uma camada intermediária única: um **API Gateway / GraphQL**. Esse gateway atua como ponto de entrada e faz o roteamento por domínio. Em vez de cada MFE sair chamando dezenas de microsserviços diretamente, ele fala com uma única camada que entende o contexto.

Quando você mencionou BFF, você chegou bem perto do conceito. A diferença sutil é que:

Se for um **API Gateway tradicional**, tipo Kong ou NGINX, ele normalmente só roteia, autentica, faz rate limit, etc. Ele não “entende” profundamente o frontend.

Já no modelo de BFF, cada frontend (ou grupo de MFEs) teria um backend específico, pensado exatamente para aquele domínio de UI. Isso pode ser feito com REST ou com GraphQL, que é muito comum nesse cenário.

O que esse diagrama parece mostrar é um **meio-termo moderno**: um gateway que também agrega dados — muito parecido com GraphQL — onde cada microfrontend consulta exatamente o que precisa. Isso reduz overfetching/underfetching e desacopla o frontend dos microsserviços internos.

Agora, o ponto arquitetural mais importante aqui é o seguinte: os MFEs estão separados na camada de apresentação, mas o backend ainda pode estar organizado por domínio (DDD). Então o gateway vira uma espécie de “orquestrador de domínio”, direcionando requisições para serviços específicos, como pagamentos, usuários, pedidos, etc.

Se você levar isso pro teu contexto (você já trabalha com mensageria, APIs, etc.), pensa assim: Cada MFE representa um bounded context visual, e o gateway/BFF é a camada que traduz isso para os serviços internos. Ele pode até agregar múltiplos serviços numa única resposta — algo que com GraphQL fica ainda mais natural.

Uma arquitetura comum nesse estilo seria: um MFE de “Pedidos” chamando um BFF de pedidos, que por trás conversa com microsserviços via REST ou até eventos (RabbitMQ, por exemplo), monta a resposta e devolve pro frontend.

Então sim — esse desenho está bem alinhado com BFF, mas com uma pegada mais moderna, muitas vezes usando GraphQL como “super gateway”.

## [MFE] Nx
<a alt="Nx logo" href="https://nx.dev" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/nrwl/nx/master/images/nx-logo.png" width="77" align="right"></a>

O **Nx** é um *build system* e ferramenta de gerenciamento de **monorepo** focada em projetos modernos principalmente front-end, mas também back-end. Ele nasceu dentro do ecossistema Angular, mas hoje funciona muito bem com React, Vue.js, Node.js e até stacks fullstack. É uma ferramenta de build e gerenciamento de monorepos que nasceu para facilitar o desenvolvimento de aplicações em larga escala, especialmente em ambientes com múltiplos projetos interdependentes. 

Ele oferece uma estrutura altamente modular, com foco em performance, cache inteligente, e ferramentas de linting, testing e build otimizadas. Criado inicialmente pelo time da Nrwl (formado por ex-funcionários do time Angular do Google), o Nx foi crescendo e ganhando suporte a várias tecnologias como React, Angular, Node.js, NestJS, e mais recentemente também Vite, Next.js, entre outras. Um dos pontos centrais do Nx é permitir que você tenha muitos apps e bibliotecas compartilhadas no mesmo repositório, tudo com regras de dependência bem definidas, para evitar acoplamentos indesejados e garantir escalabilidade.

A ideia central do Nx não é só “organizar código”, mas organizar como o código evolui e é construído. Ele entende dependências entre projetos, executa builds de forma inteligente (só o que mudou), faz cache de tarefas e permite escalar um código grande sem virar bagunça. Em vez de vários repositórios isolados, você tem um único repositório com múltiplos apps e libs bem estruturados.

Agora, trazendo isso pro contexto de *microfrontends*, o Nx encaixa quase que perfeitamente. Microfrontends é basicamente aplicar a ideia de microservices no front-end: dividir uma aplicação grande em partes independentes, que podem ser desenvolvidas e até deployadas separadamente. O problema é que isso pode virar um caos rápido — múltiplos repositórios, dependências duplicadas, inconsistência de versões, pipelines diferentes, etc.

Um dos maiores problemas em arquiteturas distribuídas com microsserviços é o gerenciamento de dependências entre os serviços e bibliotecas compartilhadas. Com o Nx, você consegue declarar essas dependências de forma explícita e rastreável, o que evita ciclos ou acoplamentos indesejados. Ele também fornece ferramentas como o project graph, que mostra visualmente a relação entre os serviços e bibliotecas internas, o que é extremamente útil em times grandes e em projetos de longo prazo. Outra vantagem do Nx em microsserviços é o build incremental, que garante que apenas os serviços afetados por uma mudança sejam reconstruídos ou retestados, reduzindo drasticamente o tempo de integração contínua e otimizando pipelines de CI/CD.

Além disso, o Nx é agnóstico em relação à tecnologia usada nos microsserviços. Você pode ter serviços escritos com Express, NestJS, Fastify, ou qualquer framework backend baseado em Node.js, e organizá-los lado a lado com bibliotecas internas e ferramentas utilitárias. Isso se encaixa bem tanto em arquiteturas orientadas a APIs REST quanto em GraphQL, eventos com filas (como RabbitMQ, Kafka) ou outros padrões de comunicação entre serviços. Em alguns casos, é possível até incluir microsserviços escritos em outras linguagens, como Go ou Python, embora o suporte nativo do Nx se concentre mais em ecossistemas JavaScript/TypeScript.

Portanto, o Nx é sim uma solução robusta para microsserviços, não só para front-end como em microfrontends, mas também para back-end. Ele oferece uma forma inteligente de manter muitos serviços independentes em um monorepo, com produtividade, consistência, reuso e governança. Ele não força a centralização dos microsserviços, mas fornece uma estrutura de colaboração que ajuda a manter a sanidade e a qualidade do código à medida que o sistema cresce. Para organizações que trabalham com diversos serviços interligados, o Nx é uma das ferramentas mais eficazes atualmente para escalar com segurança e eficiência.

É aí que o Nx entra como “cola arquitetural”. Com Nx, você pode ter um **monorepo contendo vários microfrontends**, por exemplo:

* um app “host” (container)
* vários apps “remotos” (features independentes)
* bibliotecas compartilhadas (UI, utilitários, estado, etc.)

E tudo isso dentro de um único workspace, com controle de dependência explícito.

Um padrão muito comum aqui é usar **Module Federation** do Webpack junto com Nx. Isso permite que os microfrontends sejam carregados dinamicamente em runtime, mantendo independência entre eles.

Um exemplo simplificado de estrutura no Nx seria algo assim:

```plaintext
apps/
  shell/           # app principal (host)
  products/        # microfrontend de produtos
  cart/            # microfrontend de carrinho

libs/
  ui/              # componentes compartilhados
  auth/            # autenticação
  utils/           # helpers
```

Aqui cada `apps/*` pode ser um microfrontend independente, mas o Nx garante:

<img width="365" height="138" align="right" src="https://github.com/user-attachments/assets/79515a5b-92e5-457b-92ba-d2ad41de3c96" />

* consistência de dependências

* compartilhamento eficiente de código

* builds otimizados (só o que mudou)

* testes e lint organizados por escopo

E tem um detalhe muito forte: o Nx entende o **grafo de dependências** do seu sistema. Ele sabe quem depende de quem. Isso é ouro em microfrontends, porque evita acoplamento acidental — um dos maiores problemas nesse tipo de arquitetura.

Outro ponto importante é que o Nx facilita o que chamam de **“incremental adoption”**. Você não precisa nascer com microfrontends. Pode começar com um monolito front-end (tipo um SPA grande) e ir quebrando em microfrontends aos poucos, mantendo tudo no mesmo repositório.

Então, conectando com tudo que você vem estudando:
se microservices podem cair no problema de nanoservices, microfrontends também podem cair no mesmo erro — fragmentação excessiva. O Nx ajuda justamente a evitar isso, porque ele incentiva organização por domínio e reutilização consciente, em vez de simplesmente sair quebrando tudo.

Resumindo no nível mais arquitetural:
o **Nx não é um framework de microfrontend**, ele é uma **plataforma de organização e orquestração de código** que torna viável escalar microfrontends sem perder controle.

Se quiser, posso te mostrar um exemplo real com Module Federation + Nx + React, incluindo como um microfrontend é carregado dinamicamente — isso fecha 100% o entendimento.


CustomMfe
✨ Your new, shiny [Nx workspace](https://nx.dev) is almost ready ✨.

[Learn more about this workspace setup and its capabilities](https://nx.dev/getting-started/tutorials/react-monorepo-tutorial?utm_source=nx_project&amp;utm_medium=readme&amp;utm_campaign=nx_projects) or run `npx nx graph` to visually explore what was created. Now, let's get you up to speed!

Finish your CI setup

[Click here to finish setting up your workspace!](https://cloud.nx.app/connect/UvOV0i1pmI)

Run tasks

To run the dev server for your app, use:

```sh
npx nx serve custom-mfe
```

To create a production bundle:

```sh
npx nx build custom-mfe
```

To see all available targets to run for a project, run:

```sh
npx nx show project custom-mfe
```

These targets are either [inferred automatically](https://nx.dev/concepts/inferred-tasks?utm_source=nx_project&utm_medium=readme&utm_campaign=nx_projects) or defined in the `project.json` or `package.json` files.

[More about running tasks in the docs &raquo;](https://nx.dev/features/run-tasks?utm_source=nx_project&utm_medium=readme&utm_campaign=nx_projects)

Add new projects

While you could add new projects to your workspace manually, you might want to leverage [Nx plugins](https://nx.dev/concepts/nx-plugins?utm_source=nx_project&utm_medium=readme&utm_campaign=nx_projects) and their [code generation](https://nx.dev/features/generate-code?utm_source=nx_project&utm_medium=readme&utm_campaign=nx_projects) feature.

Use the plugin's generator to create new projects.

To generate a new application, use:

```sh
npx nx g @nx/react:app demo
```

To generate a new library, use:

```sh
npx nx g @nx/react:lib mylib
```

You can use `npx nx list` to get a list of installed plugins. Then, run `npx nx list <plugin-name>` to learn about more specific capabilities of a particular plugin. Alternatively, [install Nx Console](https://nx.dev/getting-started/editor-setup?utm_source=nx_project&utm_medium=readme&utm_campaign=nx_projects) to browse plugins and generators in your IDE.

[Learn more about Nx plugins &raquo;](https://nx.dev/concepts/nx-plugins?utm_source=nx_project&utm_medium=readme&utm_campaign=nx_projects) | [Browse the plugin registry &raquo;](https://nx.dev/plugin-registry?utm_source=nx_project&utm_medium=readme&utm_campaign=nx_projects)


[Learn more about Nx on CI](https://nx.dev/ci/intro/ci-with-nx#ready-get-started-with-your-provider?utm_source=nx_project&utm_medium=readme&utm_campaign=nx_projects)

Install Nx Console

Nx Console is an editor extension that enriches your developer experience. It lets you run tasks, generate code, and improves code autocompletion in your IDE. It is available for VSCode and IntelliJ.

[Install Nx Console &raquo;](https://nx.dev/getting-started/editor-setup?utm_source=nx_project&utm_medium=readme&utm_campaign=nx_projects)

Useful links

Learn more:

- [Learn more about this workspace setup](https://nx.dev/getting-started/tutorials/react-monorepo-tutorial?utm_source=nx_project&amp;utm_medium=readme&amp;utm_campaign=nx_projects)
- [Learn about Nx on CI](https://nx.dev/ci/intro/ci-with-nx?utm_source=nx_project&utm_medium=readme&utm_campaign=nx_projects)
- [Releasing Packages with Nx release](https://nx.dev/features/manage-releases?utm_source=nx_project&utm_medium=readme&utm_campaign=nx_projects)
- [What are Nx plugins?](https://nx.dev/concepts/nx-plugins?utm_source=nx_project&utm_medium=readme&utm_campaign=nx_projects)

And join the Nx community:
- [Discord](https://go.nx.dev/community)
- [Follow us on X](https://twitter.com/nxdevtools) or [LinkedIn](https://www.linkedin.com/company/nrwl)
- [Our Youtube channel](https://www.youtube.com/@nxdevtools)
- [Our blog](https://nx.dev/blog?utm_source=nx_project&utm_medium=readme&utm_campaign=nx_projects)

## [MFE] Eventos e Estados
<img src="https://github.com/user-attachments/assets/d5fb1396-d940-4810-9990-e8aa4b6a9d74" align="right">

Quando você entra em microfrontends, o maior desafio deixa de ser só “dividir a aplicação” e passa a ser como essas partes conversam e compartilham estado sem virar um monolito distribuído no front-end, exatamente o mesmo problema que você já enxergou no backend com microservices vs nanoservices.

Eventos e estado são as duas formas principais de resolver isso, e cada uma tem implicações arquiteturais bem diferentes.

Começando por **eventos**, a ideia é muito parecida com o que você viu em arquiteturas orientadas a eventos no backend. Em vez de um microfrontend chamar diretamente outro, ele **emite um evento** dizendo que algo aconteceu, e quem estiver interessado reage.

Imagina um cenário simples: um microfrontend de login e outro de header.

Quando o usuário faz login, o microfrontend de auth não chama diretamente o header. Ele dispara algo como:

```javascript
window.dispatchEvent(
  new CustomEvent("user:loggedIn", { detail: user })
);
```

E o header escuta:

```javascript
window.addEventListener("user:loggedIn", (event) => {
  setUser(event.detail);
});
```

Aqui você tem um modelo desacoplado. Um microfrontend não precisa conhecer o outro, só o “contrato” do evento. Isso é basicamente pub/sub no browser.

Esse padrão escala bem, mas tem um custo: conforme o sistema cresce, você começa a ter muitos eventos, difícil rastrear quem dispara e quem consome. Sem governança, vira um “event spaghetti”.

Agora entra o segundo eixo: **estado compartilhado**.

Aqui você faz o oposto: em vez de espalhar eventos, você centraliza o estado em algum lugar e todos os microfrontends leem/escrevem nele. Isso pode ser feito com ferramentas como Redux, ou até soluções mais leves baseadas em store global.

Exemplo simplificado:

```javascript
// store.js
let state = { user: null };
let listeners = [];

export function setState(newState) {
  state = { ...state, ...newState };
  listeners.forEach((l) => l(state));
}

export function subscribe(listener) {
  listeners.push(listener);
}
```

Cada microfrontend pode consumir:

```javascript
subscribe((state) => {
  console.log("Estado atualizado:", state.user);
});
```

Aqui você tem consistência, previsibilidade, e menos “caos de eventos”. Mas também tem um risco: você criou um **acoplamento global**. Todos dependem do mesmo estado.

Agora vem o ponto mais importante — o equilíbrio entre os dois.

Microfrontends maduros geralmente não escolhem só um modelo. Eles combinam:

– **eventos para comunicação entre domínios** (ex: “pedido criado”, “usuário logado”)
– **estado compartilhado para dados realmente globais** (ex: usuário, tema, feature flags)

Isso é praticamente a mesma divisão que você vê no backend entre:

* eventos (Kafka, RabbitMQ)
* banco de dados / cache compartilhado

E existe ainda um terceiro modelo, que muita gente usa sem perceber: o **estado via URL**.

Exemplo:

```plaintext
/products?category=electronics
```

Diferentes microfrontends leem isso e reagem. Isso evita tanto evento quanto estado global, e funciona muito bem para navegação.

Outro ponto avançado: quando você usa ferramentas como Webpack com Module Federation ou Nx, você pode compartilhar dependências (como uma store do Redux) entre microfrontends. Mas isso precisa ser feito com muito cuidado, porque pode quebrar o isolamento.

Agora conectando com tudo que você vem estudando:
se você usar eventos demais, você cria algo parecido com EDA mal governado.
se usar estado global demais, você cria um monolito disfarçado.

O design correto geralmente segue essa lógica:

* microfrontends são isolados por domínio (DDD)
* compartilham o mínimo possível de estado
* comunicam mudanças importantes via eventos
* evitam dependência direta entre si

Resumo direto, no teu estilo: eventos são desacoplados, mas difíceis de rastrear; estado global é simples, mas acopla tudo. Arquitetura madura de microfrontends usa os dois com critério, senão você recria no front-end os mesmos problemas que já existem no backend distribuído.

## [MFE] Bit e Bit Cloud
<a href="https://bit.dev/"><img src="https://github.com/user-attachments/assets/bae1537b-cdba-495a-8d04-b5d2ecbdc681" align="right" height="177"></a>

A Bit e a <a href="https://bit.cloud/">Bit Cloud</a> oferecem uma solução completa para equipes inovadoras que desenvolvem produtos de software componíveis. Como a plataforma líder do setor em desenvolvimento orientado a componentes, ela impulsiona o desenvolvimento de aplicativos componíveis em larga escala para milhares de equipes e empresas da Fortune 500.

O **Bit** e o **Bit Cloud** entram exatamente naquela evolução natural que você está explorando: sair de “aplicações” e começar a pensar em **componentes como unidades independentes de software**, quase como “microservices do front-end”, só que num nível ainda mais granular e reutilizável.

o **Bit** é uma ferramenta pra tratar componentes como unidades independentes versionáveis, e o **Bit Cloud** é onde esses componentes vivem e são compartilhados. Juntos, eles levam o front-end para um nível de modularidade comparável ao que microservices fizeram no backend com os mesmos benefícios e os mesmos riscos se usados sem critério.

O Bit é uma ferramenta que permite você **criar, versionar, compartilhar e consumir componentes de forma independente**, mesmo estando dentro de um projeto maior. Em vez de tratar seu front-end como um bloco único (ou até como microfrontends grandes), você começa a tratar cada componente — botão, header, formulário, hook, lógica de negócio — como uma unidade isolada, com seu próprio ciclo de vida.

A **Bit** oferece uma plataforma de nível empresarial para implementar desenvolvimento desacoplado em micro frontends. Veja como Bit facilita esse processo: Ele permite que desenvolvedores encapsulem recursos frontend como componentes individuais, desenvolvidos de forma independente e versionados. Esse isolamento permite que as equipes atualizem e lancem novas versões sem afetar outras partes do aplicativo. Construindo uma solução escalável de micro frontends com federação de módulos e bits.

A grande sacada é que o Bit desacopla o componente do projeto. Normalmente, no React por exemplo, seus componentes vivem dentro do app. Com Bit, eles podem “viver fora”, ser versionados individualmente e reutilizados em vários projetos sem copiar código.

Agora entra o Bit Cloud.

O **Bit Cloud** é basicamente a plataforma onde esses componentes são publicados, compartilhados e consumidos — como se fosse um “GitHub + npm”, mas focado em componentes isolados. Você sobe seus componentes pra lá, e outros projetos podem importar diretamente, com versionamento controlado.

Na prática, isso muda completamente a forma de pensar arquitetura front-end.

Em vez de:

* um monolito front-end gigante
* ou vários microfrontends relativamente grandes

você pode ter algo como:

* componentes independentes versionados
* times diferentes mantendo partes específicas
* reuso extremo entre aplicações

Isso se conecta muito com o conceito de **component-driven development (CDD)**, onde a aplicação vira praticamente uma composição de peças independentes.

Agora, trazendo pro teu contexto de microfrontends e até nanoservices, o Bit pode tanto ajudar quanto virar problema — dependendo de como você usa.

Se você usar bem, ele resolve um dos maiores problemas dos microfrontends: **duplicação de código e inconsistência**. Por exemplo, todos os microfrontends podem consumir o mesmo componente de botão, autenticação, layout, etc., diretamente do Bit Cloud, mantendo consistência sem acoplamento direto.

Mas se exagerar, você cai exatamente no mesmo problema do nanoservice — só que no front-end.

Imagina isso:

* `button-component`
* `icon-component`
* `color-utils-component`
* `string-format-component`

Tudo versionado separadamente, com dependências entre si. Você criou um “nanoservice front-end”. Pequeno demais, fragmentado demais, difícil de gerenciar.

Então, o ponto chave aqui é o mesmo que você já percebeu na arquitetura distribuída: **granularidade saudável**.

O Bit brilha quando você:

* compartilha componentes de domínio (ex: auth, design system, formulários complexos)
* mantém versionamento independente
* evita duplicação entre times

Ele começa a doer quando:

* você quebra tudo em pedaços minúsculos
* cria dependência demais entre componentes
* transforma lógica simples em pacotes distribuídos

Conectando com tudo que você vem estudando, o Bit + Bit Cloud é quase como:

* Nx → organiza o monorepo e dependências
* Bit → organiza e distribui componentes isolados
* API Gateway / microservices → organiza backend

Ou seja, você começa a ter **arquitetura em todos os níveis**: backend, frontend e até no nível de componente.

Abaixo está um breve resumo das principais capacidades necessárias para uma plataforma CDD fornecido pela Bit.

1. **Conjunto de ferramentas de desenvolvimento orientado a componentes**: Para que os componentes se tornem blocos de construção e possam ser compartilhados entre produtos, eles devem ser desacoplados da implementação interna de um projeto específico. O conjunto de ferramentas orientado por projetos do passado nunca foi criado para esse propósito, o que torna esse processo extremamente difícil de alcançar.

![1_7uvrJ1kW7EMYgoT4mQNKQg](https://github.com/user-attachments/assets/ef283f6a-d7fa-49dd-9487-332d51df2dbe)

O Bit fornece um conjunto completo de ferramentas OSS para o desenvolvimento e composição de componentes componíveis, como blocos de build de aplicações "containerizados" e gerenciados, incluindo:

**Componente de bit**: Um componente de bit funciona como um "contêiner" para qualquer unidade de software. Inclui tudo o que é necessário para desenvolver, construir, usar, atualizar e gerenciar o componente de forma independente.

Um componente Bit pode ser um app, um recurso, uma micro-frontend, uma experiência do usuário, uma parte de interface ou até mesmo um serviço backend ou um script de CLI. Cada componente pode ser desenvolvido e usado em qualquer lugar.

**Espaço de trabalho de componentes**: O espaço de trabalho do Bit permite que desenvolvedores criem, gerenciem e compusam componentes. Ele pode ser gerado dentro ou fora de qualquer base de código existente. O espaço de trabalho oferece uma experiência simples e consistente para desenvolver, versionar, testar, gerenciar e compor componentes por meio de dependências, sem as limitações de um repositório e sem paralisar configurações manuais. Uma interface integrada e um servidor de desenvolvimento rápido proporcionam um feedback visual ao vivo agradável.

**Ambientes de desenvolvimento de componentes**: O Bit permite que desenvolvedores definam e reutilizem ambientes de desenvolvimento para seus diferentes componentes a fim de desenvolver, construir, testar, aplicar lint etc. de cada componente. Ambientes também são componentes, podendo ser personalizados, compartilhados e reutilizados. Cada componente tem um ciclo de vida totalmente independente do desenvolvimento, e o desenvolvimento se torna mais padronizado.

2. **Controle do código-fonte dos componentes e versionamento**: Para que o CDD seja aplicado, o código-fonte de cada componente deve ser controlado de forma independente e cada componente deve ser versionado de forma independente. No entanto, as ferramentas anteriores orientadas por projetos simplesmente não foram feitas para esse trabalho. Sem um conjunto dedicado de ferramentas CDD, uma quantidade incrível de trabalho e tempo será desperdiçada nesse processo, de uma forma inescalável.

![1_lpIYAiBnP5eZMgyp14MUBw](https://github.com/user-attachments/assets/2099d9d6-257b-49c9-aacb-fe929268d1b9)

Com o Bit, o código-fonte de cada componente é gerenciado e controlado separadamente. Cada componente é versionado de forma independente e pode ser atualizado junto com outros componentes que dependem dele. Tudo em um fluxo de trabalho simples, consistente e escalável. Recursos do Bit Cloud como "comparar componentes" e "revisão de alterações" fornecem um fluxo de trabalho completo para sugerir, revisar e colaborar em mudanças em componentes em toda a organização.

3. **Gestão de dependências: automatizada, inteligente e consistente**: À medida que a organização constrói e compartilha componentes, elas são compostas como dependências e réus. À medida que seu gráfico de componentes e dependências cresce, rapidamente se torna difícil gerenciar suas dependências e evitar problemas dolorosos.
   
![1_RRgM3Bd1BRh_1z2csQm0KQ](https://github.com/user-attachments/assets/4a27194d-b699-446e-8fc2-fa194cdd71ee)

O bit oferece um mecanismo único para definir e gerenciar dependências automaticamente de forma simples e consistente. Em vez de se afogar em arquivos de configuração e enfrentar problemas complexos como dependências ausentes ou conflitantes, o Bit oferece detecção automática de dependências, gerenciamento consistente de versões e políticas inteligentes de atualização para ajudar a agilizar e escalar o gerenciamento de dependências do workspace local para todo o sistema de aplicação.

4. **Embalagem e distribuição**: Sem uma solução dedicada, empacotar e distribuir componentes independentes é uma tarefa desafiadora e ainda mais difícil de escalar. Exige muito trabalho manual e patches para empacotar, publicar, manter e gerenciar muitos componentes pequenos.

Com o conjunto de ferramentas CDD dedicado da Bit, cada componente é versionado de forma independente e empacotado de forma integrada como parte do seu fluxo de desenvolvimento, podendo ser distribuído com artefatos construídos, entregues e armazenados. Cada componente automaticamente se torna um pacote publicado à medida que é exportado, independentemente de onde e como você o desenvolve e sua arquitetura.

5. **Plataforma central para compartilhamento e colaboração**: Uma plataforma central é fundamental para o sucesso de um CDD, desenvolvimento de aplicativos componíveis e um sistema de componentes compartilhados. Por meio do hub, os componentes são organizados, compartilhados e disponibilizados para todos na organização. Deve fornecer muitas soluções adicionais necessárias, como descoberta, um processo para sugerir e colaborar em mudanças de componentes, a orquestração de atualizações em toda a organização e análise e controle de componentes.

![1_xwhshSJ5PUa1hDsP2nv-FQ](https://github.com/user-attachments/assets/26a83fab-e947-4e6a-acee-260ca55977ad)
![1_n08N9rn4HXXmhDc5OusKbw](https://github.com/user-attachments/assets/897b50f0-2a68-4c5a-8b2e-fa15151362fc)

Construir essa plataforma é um desafio esmagador para qualquer organização. Mais de 5 anos e dezenas de milhões de dólares foram investidos no Bit Cloud, a plataforma mundial de desenvolvimento de produtos compáteis #1 completa. Ele oferece todas as capacidades necessárias para que as organizações aproveitem e escalem CDD, compartilhem componentes e colaborem — em um só lugar. Ele vem pronto para empresas com os mais altos padrões de segurança e conformidade, e impulsiona o desenvolvimento para grandes equipes globais.

Vamos explorar os principais requisitos para implementar com sucesso micro frontends em 2024. Também vamos explorar como a **Bit** and **Webpack Module Federation** pode ajudar a atender a esses requisitos e escalar arquiteturas micro frontend em grandes organizações. Este <a href="https://youtu.be/4CQEPBLxU_g">guia</a> vai guiá-lo pelos fundamentos para construir uma arquitetura de microfrontend componível, escalável e de alto desempenho em sua organização, incluindo colaboração e atualizações em diversas aplicações.

Essa abordagem pode resultar em vários problemas, como falta de escalabilidade, dificuldades na manutenção de uma grande base de código e ciclos de desenvolvimento mais lentos.

Por outro lado, aplicações de micro front-end, dividem o front-end em partes menores, independentes e que podem ser implantadas de forma separada, assim como os micro-serviços fazem para o back-end.

Por exemplo: uma aplicação monolítica tradicional, a parte de front-end geralmente é uma única base de código responsável por toda a interface do usuário (conhecido como monólito). Considere a adoção de aplicações de micro front-end para aproveitar seu potencial, adotando assim uma abordagem moderna à criação de aplicações web. Nada melhor que detalhar essa explicação com um bom exemplo. A imagem abaixo (figura 1), demonstra um ótimo cenário para entendermos melhor este conceito:

Cada parte é conhecida como um micro front-end e normalmente representa um recurso ou componente específico da interface do usuário. Esses micro front-ends podem ser desenvolvidos, testados e implantados por diferentes equipes, permitindo agilidade, flexibilidade e ciclos de desenvolvimento mais rápidos.

Benefícios das Aplicações de Micro Front-end:

1. **Escalabilidade**: aplicações micro front-end são altamente escaláveis. Você pode construir e implantar novos recursos ou atualizações em recursos existentes sem afetar toda a aplicação. Isso significa que você pode escalar sua aplicação de forma incremental, adicionando novas funcionalidades à medida que seu projeto evolui.

2. **Desenvolvimento ágil**: aplicações de micro front-end possibilitam ciclos de desenvolvimento mais rápidos. As equipes podem trabalhar em seus micro front-ends de forma independente, reduzindo gargalos e permitindo desenvolvimento em paralelo. Isso resulta em um tempo mais curto para levar novos recursos e atualizações ao mercado.

3. **Manutenção**: bases de código menores e isoladas são mais fáceis de gerenciar e manter. Cada equipe pode ser responsável por seu micro front-end, tornando mais simples entender e solucionar problemas. Essa modularidade também facilita a integração de novos desenvolvedores.

4. **Colaboração**: equipes podem trabalhar em paralelo, proporcionando um processo de desenvolvimento mais ágil e colaborativo. Cada equipe concentra-se em seu próprio micro front-end, garantindo que ele funcione corretamente e se integre ao restante da aplicação.

5. **Reutilização**: aplicações micro front-end podem ser reutilizados em diferentes partes do seu aplicativo, levando a interfaces de usuário mais consistentes e a eliminação de códigos duplicados.

6. **Tecnologia agnóstica**: Os micro front-ends podem ser desenvolvidos com diferentes tecnologias, frameworks ou linguagens de programação. Isso permite que as equipes escolham as ferramentas e tecnologias que melhor atendam às suas necessidades, garantindo que a aplicação permaneça flexível e adaptável.

Como implementar Aplicações de Micro Front-end: Para implementar aplicações de micro front-end, você pode usar várias técnicas e ferramentas, como: 

<a href="https://luiscameroon.medium.com/micro-frontends-with-module-federation-d5d9e135b0f1"><img src="https://github.com/user-attachments/assets/0b996b67-7657-4f01-a711-3a2b6482aa27" align="right" height="177"></a>

1. <a href="https://module-federation.io/">Module Federation</a>: podemos utilizar o plugin de federação de módulos do webpack para carregar micro front-ends dinamicamente. Micro-frontends com Module Federation oferecem uma abordagem escalável e modular para construir aplicações web. Ao dividir as aplicações em módulos independentes, os desenvolvedores podem trabalhar de forma autônoma e aproveitar o poder do carregamento dinâmico de módulos. Podemos utilizar Micro-frontends com Federação de Módulos e demonstrar sua implementação usando React e Vite. Comece a experimentar essa arquitetura para construir aplicações web flexíveis, manuteníveis e eficientes.

2. **Componentes da web**: usar componentes da web para criar elementos de interface reutilizáveis que podem ser incorporados em diferentes micro front-ends.

3. **Inclusões no lado do servidor (SSI)**: combinar micro front-ends no nível do servidor, possibilitando a montagem de conteúdo dinâmico.

4. **API Gateway**: implementar um gateway de API para encaminhar solicitações para o micro Front-end apropriado.

5. **Aplicações de contêiner**: construir uma aplicação de contêiner que gerencia a composição dos micro front-ends.

Principais Requisitos para a Arquitetura Micro Frontend:

**1. Desenvolvimento Desacoplado**: O desenvolvimento desacoplado em arquitetura micro frontend permite que cada micro frontend seja desenvolvido, implantado e mantido de forma independente. Cada uma, representando uma característica distinta, pode usar sua própria pilha tecnológica, cronograma de lançamento e processos. Essa autonomia reduz as dependências das equipes, permitindo inovação e iteração mais rápidas.

Em grandes empresas, frontends frequentemente se tornam monolíticos e difíceis de gerenciar, onde mudanças podem impactar todo o sistema, retardando o desenvolvimento e aumentando riscos. O desenvolvimento desacoplado divide o frontend em partes gerenciáveis, permitindo que as equipes:

- Inove Mais Rápido: Escolha as ferramentas e frameworks ideais, acelerando o desenvolvimento.
- Reduzir riscos: Isole as mudanças para minimizar o impacto na aplicação mais ampla.
- Escale de forma eficiente: Escale independentemente cada micro frontend, apoiando o crescimento orgânico.

Frameworks de microfrontend permitem criar unidades menores e independentes para sua aplicação frontend, que permitem focar no desenvolvimento de partes independentes da sua aplicação como componentes. Essas pequenas unidades podem ser desenvolvidas, testadas, versionadas e implantadas por equipes separadas. Isso ajudará você a aprimorar seu trabalho paralelo e minimizar o risco de gargalos nos pipelines de desenvolvimento.

![1_OlQsunH7kXFFctnuWb9RNw](https://github.com/user-attachments/assets/a7dc9d37-bcca-4bb4-9509-e134eb23394a)

Usaremos a Federação de Módulos e o Bit para implementar uma integração em tempo de execução de Micro Frontends. O Bit oferece modelos pré-configurados para nosso aplicativo host e módulos remotos. Também facilita incrivelmente o compartilhamento de componentes entre micro frontends.

Por exemplo, uma equipe pode atualizar uma micro frontend baseada em React enquanto outra trabalha simultaneamente em um componente Angular, com ambos gerenciados de forma independente.

> Saiba mais: Criar componentes | Bit - Um componente é um módulo reutilizável, controlado por código-fonte independente, que é armazenado em escopos e mantido em... bit.dev

Exemplo: Um componente React para uma página de perfil de usuário pode ser desenvolvido isoladamente dentro do ambiente do Bit. Ele pode ser versionado, testado e implantado independentemente do restante da aplicação, garantindo que quaisquer atualizações desse componente não atrapalhem outras micro frontends.

**Host Apps and Remote Modules**: O aplicativo host e os módulos remotos foram gerados usando modelos pré-configurados (disponibilizados pela Bit):

```sh
npx @teambit/bvm install # install Bit
bit init my-modfed-solution # create a new Bit workspace
cd my-modfed-solution
```

Adicione o seguinte ao seu para disponibilizar os templates do ModFed no seu espaço de trabalho: `workspace.jsonc`

```sh
"teambit.generator/generator": {
    "envs": [
      "frontend.module-federation/envs/mf-react-env"
    ]
  }
```

Execute os seguintes comandos:

```sh
bit install # install the workspace dependnecies
bit create modfed-remote-mfe storefront # generate a remote module
bit create modfded-remote-mfe blog
bit create modfed-host-app shell-app # generate a host app
```

> Execute para listar os modelos ModFed disponíveis: `bit templates`

Para listar os aplicativos disponíveis (e módulos remotos), execute:

```sh
bit app list
```

A saída lista os IDs dos componentes e seus nomes correspondentes de app:

<pre>
┌─────────────────────────────────────────────────┬─────────────────────┐
│ id                                              │ name                │
├─────────────────────────────────────────────────┼─────────────────────┤
│ bit-bazaar.storefront/storefront                │ storefront          │
├─────────────────────────────────────────────────┼─────────────────────┤
│ bit-bazaar.blog/blog                            │ blog                │
├─────────────────────────────────────────────────┼─────────────────────┤
│ bit-bazaar.shell-app/shell-app                  │ shell-app           │
└─────────────────────────────────────────────────┴─────────────────────┘
</pre>

Você pode rodar os apps localmente usando o nome deles:

```sh
bit run storefront
```

**Shared Dependencies**: Nossa solução consiste em muitas dependências compartilhadas configuradas para serem excluídas dos pacotes de aplicativos e carregadas como blocos separados. Essa é uma das forças da ModFed. Isso nos permite otimizar o tamanho do nosso bundle, manter a consistência e evitar conflitos entre versões do mesmo módulo.

Nossa lista de <a href="https://bit.cloud/bit-bazaar/shell-app/shared-dependencies/~code/shared-dependencies.ts">dependências compartilhadas</a> é mantida como um componente Bit compartilhado entre projetos (o aplicativo host e os módulos remotos). Isso permite que as equipes mantenham consistência enquanto trabalham de forma independente.

A lista de dependências compartilhadas consiste principalmente em libs em tempo de execução e um sistema de projeto:

![1_SDBgYqyMyiTVR3MmXrCVtw](https://github.com/user-attachments/assets/d0b70f19-bc9c-4971-ac53-54549289034d)

O componente 'dependências compartilhadas' (que lista os deps de shred) é usado pela configuração do app host e pela configuração dos módulos remotos

![1_owibIMnKJ0s749r8DEwWvw](https://github.com/user-attachments/assets/d8edd2d8-0ec3-432a-b9ec-6f0582e42c5b)

Por exemplo: https://bit.cloud/bit-bazaar/shell-app/shared-dependencies/~code/shared-dependencies.ts

```ts
/**
 * @filename: storefront.bit-app.ts
 * @component-id: bit-bazaar.storefront/storefront
*/

import { MfReact } from '@frontend/module-federation.react.apps-types.mf-rspack';
/* import the 'shared dependnecies' components */
import { shellAppSharedDependencies } from '@bit-bazaar/shell-app.shared-dependencies';


export default MfReact.from({
  name: 'storefront',
  clientRoot: './storefront.app-root.js',
  moduleFederation: {
    exposes: {
      // ...
    },
    shared: shellAppSharedDependencies,
  }
});
```

**Um Sistema de Design Compartilhado**: Nossa biblioteca de componentes e tema são baseados no Material UI. Eles são mantidos no escopo de "design" e compartilhados entre Micro Frontends.

![1_VNkzhuxM7aQiLslASgYs9A](https://github.com/user-attachments/assets/c7c58e4b-a74a-4b6b-9fad-b89e94186f90)

**Contexto Compartilhado**: O 'Provedor de Tema', 'Provedor de Autenticação' e outros componentes de contexto fazem parte do "app anfitrião" ou "app shell". Por isso, eles são mantidos pela equipe do "app shell".

![1_gzRW_UPh8FVNg6AdunoDOg](https://github.com/user-attachments/assets/1e1e225b-909c-4018-b4f3-8e7d3191e172)

Equipes que trabalham em MFEs não precisam se preocupar com autenticação, autorização ou qualquer outra funcionalidade compartilhada. A equipe "anfitriã" ou "shell" fornece tudo para eles.

Por exemplo, se o time Storefront precisar implementar funcionalidades baseadas na autenticação do usuário, eles explorariam o escopo do 'app shell' e buscariam o "SDK" correto.

![1_nygdqeWAhwyCEkAhZSH8Ww](https://github.com/user-attachments/assets/443d42a3-8d1b-45b4-99cb-319c8fef16c1)

O contexto e o gancho da "Auth"

**Roteamento e navegação**: O aplicativo shell oferece uma espécie de "sistema de plugins" onde Micro Frontends (módulos remotos) podem se integrar a ele de maneiras que vão além de um simples link. Ele faz isso fornecendo os tipos para cada "plugin".

![1_LNIly_jIcZHgyl67TluvKg](https://github.com/user-attachments/assets/6fa55e8c-2ede-4b87-a30a-96d704f2aa6d)

O tipo compartilhado de "item de navegação"

Por exemplo, um módulo remoto pode implementar uma interface de "item de navegação" que inclui suas opções de navegação.

![1_O5Z7c-movW0_IlQZ-W4kMw](https://github.com/user-attachments/assets/64104f4f-ff36-4af6-a9cc-c8eaa7451321)

Isso pode então ser exposto para o app shell (que o carregará em tempo de execução):

```ts
/**
 * @filename: blog.bit-app.ts
 * @component-id: bit-bazaar.blog/blog
*/

export default MfReact.from({
  name: 'blog',
  clientRoot: './blog.app-root.js',
  moduleFederation: {
    exposes: {
      /** 
       * the MFE navigation exposed to be loaded 
       * by the shell app at runtime
       **/
      './blognav': './navitem.js',
       /**
        * the main chunk of the 'blog' MFE
        **/
      './blog': './blog.js',
    },
    shared: shellAppSharedDependencies,
  },
  deploy: Netlify.deploy(netlifyConfig),
});
```

O roteamento é tratado no nível que se adequa ao módulo. Por exemplo, o app shell só gerencia o roteamento para e . Ele não determina o roteamento "dentro" de cada MFE (como ).`/blog/*/storefront/*storefront/products`

```ts
/**
 * @filename: shell-app.tsx
 * @component-id: bit-bazaar.shell-app/shell-app
*/

export function ShellApp() {
  return (
    <BrowserRouter>
          <Routes>
            <Route path="/" element={<Layout />}>
              <Route index element={<Homepage />} />
              <Route path="store/*" element={<Store />} />
              <Route path="blog/*" element={<Blog />} />
              <Route path="*" element={<div>Not Found</div>} />
            </Route>
          </Routes>
    </BrowserRouter>
  );
}
```

Assim, os módulos remotos, como o 'blog', não são responsáveis pelo roteamento (o roteamento para o blog MFE) — apenas para rotas aninhadas.`/blog/*`

```ts
/**
 * @filename: blog.tsx
 * @component-id: bit-bazaar.blog/blog
*/

export function Blog() {
  return (
      <Routes>
        <Route path="articles" element={<ArticlesPage />} />
        <Route path="categories" element={<CategoriesPage />} />
      </Routes>
  );
}
```

**DevX**: Para a experiência máxima de desenvolvedor, cada equipe usa um componente "Plataforma" para consumir uma versão imutável do app shell e possivelmente outros módulos remotos.

Isso fornece aos MFEs o contexto adequado para rodar em desenvolvimento. Ele garante uma experiência de desenvolvimento consistente e fluida, ao mesmo tempo em que aplica corretamente permissões e controle de acesso (por exemplo, a equipe do 'blog' não pode modificar o MFE 'loja' ou o aplicativo shell).

![1_NU2_MVKTnTMHAEfUr_5QBw](https://github.com/user-attachments/assets/8989648c-1723-4bc0-88a3-45f548d81521)

https://bit.cloud/bit-bazaar/storefront/storefront-platform/~code/shell-platform.bit-app.ts

![1_kxmzE2RnzgLq70WKtnKPSw](https://github.com/user-attachments/assets/83ac0908-ef10-469b-92d0-4e2467262aab)

O 'shell-app' como uma dependência imutável da 'plataforma de loja' usada pela equipe de 'loja de loja' para o desenvolvimento de 'loja de loja' em seu contexto completo

Por exemplo, a equipe 'storefront' consegue rodar o MFE 'storefront' em seu contexto completo (app shell e até outros MFEs) rodando o app 'platform' mantido por eles (apenas para desenvolvimento):

```sh
bit run storefront-platform
```

![1_990s5cPwdR9-tYjigxgNbw](https://github.com/user-attachments/assets/c94d8951-6415-470b-895c-9443e507b399)

Você pode gerar um componente 'Platform' usando o modelo fornecido pelo ambiente ModFed (aquele configurado como gerador no início deste blog):

```sh
bit create modfed-platform my-platform
```

**2. Ambientes de Desenvolvimento Personalizados**: O Bit suporta ambientes de desenvolvimento personalizados adaptados a diferentes pilhas tecnológicas.

Múltiplos Ambientes podem ser usados no mesmo "monorepo" e até reutilizados entre repositórios.

As equipes podem configurar ambientes específicos para React, Angular, Vue.js ou qualquer outro framework. Esses ambientes incluem todas as ferramentas necessárias, como linters, compiladores e frameworks de teste, garantindo que cada micro frontend seja desenvolvido sob condições consistentes. Saiba Mais:

React — Configure seu ambiente | Bit
Criar um novo ambiente de desenvolvimento React
bit.dev

Exemplo: Uma equipe pode usar o Bit para configurar um ambiente React personalizado com ESLint e Jest para testes, enquanto outra equipe monta um ambiente Angular com Karma para testes unitários. Esses ambientes garantem que os processos de desenvolvimento, teste e construção sejam padronizados e otimizados dentro do contexto de cada micro frontend.
4. Cápsulas para Construções Isoladas: A tecnologia Capsule do Bit permite que componentes sejam construídos em completo isolamento do restante da base de código. Esse isolamento garante que a build seja executada e que todas as dependências sejam gerenciadas corretamente, prevenindo problemas de escopo global e facilitando a identificação e correção de bugs no início do processo. As cápsulas oferecem aos desenvolvedores um campo de desenvolvimento e testes confiável antes da implantação.

**2. Controle de Versões e Gerenciamento de Dependências**: Controle de versões e gerenciamento de dependências são aspectos cruciais da arquitetura micro frontend. Em uma configuração micro frontend, cada módulo ou componente frontend é desenvolvido, versionado e mantido de forma independente.

<img width="647" height="417" alt="image" src="https://github.com/user-attachments/assets/c3cc2fac-c986-463e-bee4-2c9fc368228a" />

Essa independência significa que cada módulo pode evoluir em seu próprio ritmo, com suas dependências específicas e sistema de versionamento.

O controle de versão por componente garante que as atualizações de uma micro frontend não quebrem inadvertidamente outras partes da aplicação, enquanto um gerenciamento eficaz de dependências previne conflitos e garante que cada módulo possa funcionar conforme previsto no ecossistema maior.

Em aplicações em larga escala, gerenciar dependências e versões torna-se cada vez mais complexo à medida que mais micro frontends são introduzidos.

Sem um sistema robusto, é fácil surgir conflitos de dependências, levando a problemas como bibliotecas duplicadas, incompatibilidades de versões ou até mesmo falhas de aplicação. Controle de versões adequados e gerenciamento de dependências garantem que:

- **Estabilidade é Mantida**: Atualizações em uma micro frontend não quebram outras, mantendo a estabilidade geral da aplicação.
- **Dependências são Consistentes**: Cada micro frontend usa as versões corretas das bibliotecas compartilhadas, evitando conflitos e redundâncias.
- **Flexibilidade de Implantação**: As equipes podem atualizar ou reverter micro frontends específicos sem afetar toda a aplicação, permitindo estratégias de implantação mais flexíveis e responsivas.

A **Bit** oferece uma solução abrangente para controle de versões e gerenciamento de dependências em arquiteturas micro frontend. Veja como ele suporta esses processos:

Versionamento Independente: Bit permite que cada componente ou micro frontend seja versionado independentemente (usando regras semver). Isso permite que as equipes misturem e combinem componentes, atualizem ou revertam componentes específicos sem impactar outros, possibilitando mudanças incrementais e lançamentos para micro frontends.

![1_Yrv8YEoaGHv7oFoDxABmeQ](https://github.com/user-attachments/assets/9085f62f-ee04-499e-91cf-5a360a4ca327)

Além disso, você pode comparar mudanças entre versões dos componentes, e não apenas código, mas também prévias, documentação, testes, dependências e mais:

![1_Nvsh1bskCHSwqShLlalTGg](https://github.com/user-attachments/assets/12cdf282-55c8-4e72-911f-45e8d4ff1580)

Versionamento por micro frontend; Dependências e atualizações automatizadas

Cada alteração em um componente é rastreada e gerenciada dentro do Bit, fornecendo um histórico claro de versões e alterações. Marcar um componente vai aplicar uma versão, e bater uma versão fará com que o Bit te avise se houver outros componentes que também exigem um bump de versão como resultado. Aprender:

Exemplo: Uma equipe pode atualizar um componente de login para melhorar a segurança. Com o Bit, eles podem lançar uma nova versão desse componente enquanto outras partes do aplicativo continuam usando versões mais antigas e estáveis. Se surgirem problemas, é fácil voltar para uma versão anterior sem afetar o restante do sistema.

**Gerenciamento Automatizado de Dependências**: É aí que Bit realmente muda o jogo.

![1_c_gnpxgZuZthxCEKX6y4OA](https://github.com/user-attachments/assets/a50ab9be-ff35-454e-ab7e-955801834840)

Bit define e gerencia automaticamente as dependências de cada componente. Quando um componente é criado ou atualizado, o Bit resolve e instala todas as dependências necessárias, garantindo que cada micro frontend tenha tudo o que precisa para funcionar corretamente.

![1_lBTUSmjDP5z4lgRhK01tTA](https://github.com/user-attachments/assets/89e276d5-232c-4e5e-817c-9563e447bfa4)

> Esse processo ajuda a prevenir problemas como conflitos de dependências ou bibliotecas ausentes, que são comuns em aplicações complexas com monorepos, micro frontends e componentes compartilhados. Aqui está uma <a href="https://www.youtube.com/watch?v=vpVIw5QTlps">DEMONSTRAÇÃO em VÍDEO do autor da PNPM</a>.

Exemplo: Suponha que uma micro frontend dependa de uma versão específica de uma biblioteca como . O bit garante que a versão correta esteja instalada e que outras micro frontends usando versões diferentes não interfiram nela. Esse isolamento previne conflitos e garante que cada micro frontend permaneça estável e funcional.`lodash lodash`

1. **Dependências Compartilhadas**: O Bit também automatiza o gerenciamento de dependências compartilhadas entre micro frontends. Quando múltiplas micro frontends usam a mesma biblioteca ou componente, o Bit ajuda a gerenciar essas dependências compartilhadas para evitar duplicação e reduzir o tamanho do bundle. Dependências compartilhadas são consistentes em toda a aplicação, permitindo que **micro frontends individuais atualizem de forma independente**.

![1_x0OdtplgZVhwiIgDT5A2bg](https://github.com/user-attachments/assets/c790273e-a87b-4838-9dfd-ce7516122409)

Exemplo: Um sistema de design ou uma biblioteca utilitária usada por múltiplas micro frontends pode ser compartilhada como um componente de Bits. Esse componente compartilhado é versionado e mantido em um repositório central, facilitando para as equipes extrair a versão mais recente ou reverter para versões anteriores conforme necessário.

2. **Integração com Pipelines CI/CD**: O <a href="https://youtu.be/eOAjPnfGcbc">bit</a> se integra perfeitamente com pipelines CI/CD, automatizando o processo de teste, construção e implantação de componentes à medida que são atualizados. Essa integração garante que todas as versões de um componente sejam minuciosamente testadas antes de entrar no mercado, reduzindo o risco de introduzir bugs ou alterações quebradas no ambiente de produção.

Você pode até <a href="https://youtu.be/PZ2MhC5N6uI">automatizar atualizações de PR</a> para seus repositórios do GitHub:

Exemplo: Quando uma nova versão de um micro frontend é enviada para Bit, o pipeline CI/CD automaticamente dispara testes, constrói o componente e o prepara para implantação. Se todas as verificações passarem, a nova versão é marcada e lançada; caso contrário, a implantação é interrompida, impedindo que possíveis problemas cheguem aos usuários.

3. **Integrações e Atualizações em Tempo de Execução vs Tempo de Construção**: A decisão entre integrações em tempo de execução e em tempo de construção impacta a flexibilidade e escalabilidade das arquiteturas micro frontend. A integração em tempo de execução permite composição dinâmica e atualizações, enquanto a integração em tempo de construção envolve compilar tudo em um único pacote, o que pode limitar a flexibilidade, mas oferece alto desempenho e uma boa experiência de desenvolvimento.

Como cada componente é um pacote ou módulo independente, com sua própria versão, torna-se possível atualizar componentes específicos (e seus dependentes impactados) sem precisar atualizar o restante do projeto.

![1_Gdf4FWXtf5cpoGbe38dZGw](https://github.com/user-attachments/assets/cb4d7933-7e45-4526-b087-8400991e9f76)

<img src="https://github.com/user-attachments/assets/f09f0884-dd91-49d7-815a-8ce767c528ec" align="right">

O Bit suporta ambos os tipos de integrações e permite que você escolha qual é a mais adequada para você. Ele roda nativamente com a <a href="https://bit.dev/docs/micro-frontends/module-federation">Module-Federation</a>, assim como com todos os gerenciadores de pacotes ou registros.

Por exemplo, aqui estão algumas demonstrações de integração e atualização de componentes de Bits usando <a href="https://youtu.be/dWPp4EsScsg">Module-Federation</a>: E um mergulho nas implantações deles nesse cenário com federação de módulos:

Ao mesmo tempo, todo componente exportado para <a href="https://bit.cloud/">bit.cloud</a> já é um pacote — isso acontece automaticamente quando você marca e exporta o componente. Ou seja, você pode instalá-lo usando qualquer gerenciador de pacotes ou registro (incluindo o JFrog Artifactory), e pode encontrar esse painel em cada página de componentes, na aba "usar":

**Implantações Independentes**: Micro frontends devem ser implantáveis de forma independente, permitindo que diferentes partes da aplicação evoluam e sejam lançadas em seu próprio ritmo, sem necessidade de sincronização com outros componentes.

A arquitetura modular do Bit permite que cada componente ou micro frontend seja implantado de forma independente. O bit se integra perfeitamente com a Webpack Module Federation, permitindo que componentes sejam carregados sob demanda em tempo de execução. Isso desacopla o processo de implantação do restante da aplicação, permitindo implantações rápidas e autônomas.

6. **Micro Frontends Compartilhados via Plataforma Central**

![1_Nj2EzGOskF51B5AKuR-szw](https://github.com/user-attachments/assets/83345736-1b36-4c21-94b3-59df19e163b0)

**6.1 Plataforma central**: Bit.cloud é uma plataforma central para componentes compartilhados (por exemplo, micro frontends). Oferece hospedagem em nuvem, nuvem privada e versões baseadas em servidores locais. A Bit Cloud é uma plataforma de ponta a ponta para desenvolvimento orientado a componentes, que permite um fluxo de trabalho simplificado e completo para criar, compartilhar, descobrir, consumir, alterar e atualizar componentes. Essa é uma parte fundamental para adotar com sucesso micro frontends em um ambiente organizacional e em escala. Ele pode ser integrado e conectado às suas ferramentas e fluxos de trabalho, como GitHub ou Artifactory, assim como Figma e até suas ferramentas CI/CD.

Seus micro frontends podem ser hospedados na sua conta privada, na conta da sua organização e divididos em "Escopos" que servem como coleções de componentes com temas comuns, domínios de propriedade. Pode conferir:

**6.2 Descoberta para micro frontends**: A Bit Cloud oferece uma plataforma robusta para descobrir componentes micro frontend compartilhados, facilitando para as equipes encontrarem, entenderem e escolherem os melhores componentes para seus projetos. Ele oferece capacidades avançadas de busca, permitindo que os usuários filtrem componentes com base em critérios específicos, como tags, dependências e versões. Isso ajuda os desenvolvedores a localizar rapidamente o componente exato que precisam.

![1_Tm5yoSEOL9iI5g6sKnBZOQ](https://github.com/user-attachments/assets/71646530-344f-43b8-b15f-e058df0744c5)

Além da funcionalidade de busca, o Bit Cloud aprimora a descoberta de componentes com exemplos visuais e documentação gerada automaticamente. A página de cada componente apresenta documentação detalhada, incluindo instruções de uso, mapas de dependências e composições visuais que mostram o componente em vários estados e contextos. Essas composições simulam o comportamento do componente, ajudando desenvolvedores e não desenvolvedores (como designers) a entender como o componente funciona e como pode ser integrado a diferentes projetos.

**6.3 Análises para status, uso e adoção**: Um dos aspectos mais importantes do desenvolvimento de escalabilidade com micro frontends compartilhados ou qualquer outro tipo de componente é a capacidade de acompanhar seu uso, adoção, tech-stacks, status e todos os outros parâmetros importantes que ajudam a governar e gerenciar esses blocos de construção.

![1_ifIl5rsjLcBQMt35AgQneA](https://github.com/user-attachments/assets/30954407-481a-43f1-afcd-144656c28728)

Em Bit.Cloud você pode visualizar as dependências diretas e indiretas de cada componente (ou Scope), o uso em diferentes projetos, atualizações de versões, tecnologias usadas e mais.

![1_5e9sCgtNi0H4qw6uYUUntA](https://github.com/user-attachments/assets/a1462ac8-dfba-4a79-8f99-c4b43890fe19)

**7. Desenvolvimento Colaborativo**: Arquiteturas micro frontend eficazes exigem colaboração entre equipes e também dentro de equipes multifuncionais. Os construtores precisam ser capazes de trabalhar juntos de forma fluida, mesmo ao desenvolver diferentes partes da aplicação, enquanto trabalham juntos para planejar, revisar e lançar.

O bit é projetado para permitir colaboração.

Por exemplo, novas versões para componentes podem ser sugeridas por meio de "requests-change", onde os membros da equipe revisora podem ver alterações de código, pré-visualizações visuais, alterações em testes, dependências e muito mais. Eles podem discutir e aprovar essas mudanças diretamente na tela de solicitação de mudança.

![1_w5hNbKpy543M2JZgB_HMHA](https://github.com/user-attachments/assets/b175d89a-0a4e-4d5c-a000-5f29cb613127)

Além disso, componentes podem ser facilmente importados para o seu espaço de trabalho local para edição e alterações, o que facilita muito a colaboração em componentes, sugestões de alterações, entrega de atualizações e a sincronização.

![1_pxpN_mgePkf1ecsPn1NV0w](https://github.com/user-attachments/assets/e190ddde-acb3-4df5-8cf4-8c5c12d8bb50)

Esse ambiente colaborativo acelera o desenvolvimento e garante que todas as equipes estejam alinhadas, a tecnologia seja padronizada e a UX/UI permaneça consistente.

**8. Equipes Autônomas**: Equipes que trabalham em diferentes micro frontends devem operar de forma autônoma, com controle total sobre seus respectivos domínios. Essa autonomia é crucial para fomentar a inovação e reduzir gargalos no processo de desenvolvimento.

![1_Lj5tkND0DLFUDuUokKGyHA](https://github.com/user-attachments/assets/05fa79d6-3107-4dc6-a986-c5027f33ce2c)

As equipes possuem e entregam microfrontends orientados por domínio

A plataforma da Bit apoia equipes autônomas fornecendo as ferramentas para desenvolver, testar e implantar seus componentes de forma independente. Cada equipe pode gerenciar seus próprios fluxos de trabalho, do desenvolvimento à implantação, sem precisar coordenar com outras equipes. Essa autonomia é aprimorada pelo suporte do Bit para versionamento independente, implantação e integração em tempo de execução, permitindo que as equipes avancem rápido e inovem livremente.

**9. Múltiplas Pilhas de Tecnologia**: Micro frontends são particularmente poderosos em organizações onde diferentes equipes preferem usar stacks tecnológicos distintos. Essa flexibilidade permite que cada equipe selecione as melhores ferramentas e frameworks para os recursos específicos que está desenvolvendo. Por exemplo, uma equipe pode usar o React para um painel de usuário, outra pode optar pelo Angular para lidar com formulários complexos, enquanto outra equipe pode aproveitar Vue.js para componentes leves e de carregamento rápido, como barras de navegação.

![1_EoVFwzwDO4wwzD1Ip2HI4Q](https://github.com/user-attachments/assets/296b06fe-e909-416f-9330-4847dcd20dfd)

Muitos componentes, muitas tecnologias, uma única plataforma

O Bit desempenha um papel crucial na gestão dessas pilhas diversas por meio de seus Ambientes Componentes. Ambientes de bits são extensões que configuram e gerenciam as ferramentas e fluxos de trabalho de desenvolvimento específicos para cada framework ou pilha tecnológica. Ao trabalhar em um espaço de trabalho gerenciado por bits, as equipes podem criar ambientes personalizados para React, Angular, Vue.js ou qualquer outra pilha tecnológica que estejam utilizando. Esses ambientes garantem que cada componente seja isolado e desenvolvido em um ambiente consistente, independentemente da tecnologia subjacente.

Por exemplo, um ambiente componente React no Bit pode incluir configurações para ESLint, Jest e Webpack, enquanto um ambiente Angular pode configurar TypeScript, Karma e Angular CLI. Isso permite que cada equipe foque no desenvolvimento sem se preocupar com conflitos entre pilhas, já que a Bit cuida da integração e garante que cada componente seja compatível quando combinado em uma aplicação maior.

Além disso, ambientes de bits suportam Cápsulas, que criam ambientes de desenvolvimento isolados para componentes. Isso significa que cada componente pode ser desenvolvido, testado e construído completamente isolado do restante da base de código, garantindo que problemas como conflitos de dependência ou vazamentos globais de estado sejam detectados cedo.

**10. Shell de Aplicação**: Um **App Shell** (<a href="https://blog.bitsrc.io/application-shell-for-react-micro-frontends-daa944caa8f3?source=post_page-----28f78ce825ad---------------------------------------">Application Shell</a>) é uma estrutura estática que carrega primeiro e fornece a estrutura central de um aplicativo web, incluindo elementos de interface compartilhados como cabeçalhos e barras de navegação. Em uma arquitetura de micro frontend, o shell do aplicativo garante uma interface de usuário consistente enquanto carrega dinamicamente micro frontends.

<table>
	<tr>
		<td><img src="https://github.com/user-attachments/assets/2e9b9ef6-b8c2-4fa5-9fe3-32c412937419"></td>
		<td><img src="https://github.com/user-attachments/assets/732e7167-5a6f-4664-9aef-f0940d5d91b1"></td>
	</tr>
</table>

A interface do app serve como uma base estável, gerenciando o roteamento e o estado enquanto micro frontends são carregados de forma independente. Essa separação permite que cada micro frontend seja desenvolvido e implantado sem impactar a aplicação como um todo.

<table>
	<tr>
		<td><img src="https://github.com/user-attachments/assets/b9d70155-f659-4257-8f31-b27c0009983a"></td>
		<td><img src="https://github.com/user-attachments/assets/1802a081-ea81-4907-be4f-df3c52c3b860"></td>
		<td><img src="https://github.com/user-attachments/assets/de428084-ea2c-4521-90cf-06720ad5a944"></td>
	</tr>
</table>

A estrutura da solução ModFed. A organização de bits que mantém a solução MFEs. Os repositórios que mantêm os espaços de trabalho de bits para os componentes compartilhados, o app host e os módulos remotos

- Desenvolvimento Independente: O Bit possibilita a criação de shells de aplicativos e micro frontends como componentes separados, possibilitando que sejam desenvolvidos, versionados e implantados de forma independente.
- Integração dinâmica: Usando a Federação de Módulos do Webpack, o Bit permite que micro frontends sejam carregados dinamicamente na interface do app, garantindo integração suave em tempo de execução.
- Gestão Centralizada: O Bit Cloud centraliza o armazenamento e a gestão de shells de aplicativos e micro frontends, facilitando a descoberta, atualização e compartilhamento de componentes em toda a organização(

Em essência, o Bit suporta a integração perfeita e o gerenciamento independente de shells de aplicativos e micro frontends, garantindo consistência e flexibilidade em aplicações web complexas. Aqui está um exemplo:

## [MFE] Frameworks de Micro Frontend
À medida que as aplicações web continuam a crescer em tamanho e complexidade, os desenvolvedores estão constantemente buscando novas formas de construí-las e mantê-las de forma eficiente. 

**Agilidade e flexibilidade aumentadas**: Micro Frontends permitem mais flexibilidade e agilidade no desenvolvimento, já que cada recurso de aplicação é um módulo independente que pode ser desenvolvido, testado e implantado isoladamente. As equipes podem escolher a pilha tecnológica que melhor atenda às suas necessidades e preferências, permitindo maior flexibilidade no desenvolvimento.

**Escalabilidade Aprimorada**: Micro Frontends facilitam a escalabilidade horizontal das aplicações, já que cada módulo pode ser implantado separadamente, permitindo melhor desempenho e confiabilidade. Também permite que as equipes adicionem ou removam recursos facilmente da aplicação sem afetar o restante da aplicação, tornando-a mais escalável a longo prazo.

**Redução da Dependência e Melhoria da Manutenção**: Micro Frontends reduzem a dependência entre recursos, facilitando a manutenção da aplicação ao longo do tempo. Cada módulo pode ser desenvolvido, testado e implantado de forma independente, o que facilita a realização de atualizações ou alterações sem impactar toda a aplicação.

**Melhor Produtividade e Colaboração em Equipe**: Micro Frontends permitem que equipes trabalhem de forma independente em diferentes partes da aplicação, sem se atrapalharem, melhorando a produtividade e a colaboração. Cada equipe pode focar em sua funcionalidade ou funcionalidade específica, reduzindo conflitos e otimizando o desenvolvimento.

**Melhoria da Experiência do Usuário**: Micro Frontends permitem que desenvolvedores criem melhores experiências de usuário ao focar em recursos e funcionalidades específicas. Também permite maior personalização e personalização do aplicativo, aumentando o engajamento e a satisfação do usuário.

Quando se trata de Micro Frontends, não existe uma abordagem única para todos. De integrações inteligentes em tempo de construção a roteadores personalizados em tempo de execução, há uma infinidade de técnicas que podem ser empregadas para criar arquiteturas micro frontend eficientes e eficazes. Para facilitar o processo de desenvolvimento, várias ferramentas poderosas surgiram, cada uma com seu próprio conjunto único de benefícios e recursos. Vamos dar uma olhada mais detalhada em algumas das ferramentas mais proeminentes disponíveis para construir micro frontends:

<a href="https://single-spa.js.org/"><img src="https://github.com/user-attachments/assets/d7e2a019-69f5-4109-a18e-f4813018c30d" align="right" height="77"></a>

**Single-SPA**, ou Aplicação de Página Única, é um framework que permite aos desenvolvedores construir aplicações web como um conjunto de micro frontends. Ele permite que desenvolvedores usem diferentes frameworks e bibliotecas para diferentes partes da aplicação, facilitando a personalização e atualização da aplicação ao longo do tempo.

Como funciona o Single-SPA? Single-SPA usa um roteador para determinar qual micro frontend carregar com base na URL atual. Quando o usuário navega para uma nova página, o roteador determina qual micro frontend carregar com base no caminho da URL e a carrega dinamicamente.

Cada micro frontend é uma aplicação JavaScript independente que pode ser desenvolvida e implantada de forma independente. Isso permite maior flexibilidade e agilidade no desenvolvimento, já que cada micro frontend pode ser atualizado ou modificado sem afetar o restante da aplicação.

O Single-SPA fornece um conjunto de ganchos de ciclo de vida que permitem que micro frontends interajam entre si e com o roteador. Por exemplo, uma micro frontend pode se registrar no roteador, o que permite receber notificações quando a URL muda.
O Single-SPA também oferece um carregador de módulos que permite que micro frontends importem e exportem funcionalidades entre si. Isso facilita o compartilhamento de código e recursos entre micro frontends, reduzindo redundância e melhorando a eficiência.
Alguns Benefícios Chave do SPA Único

- ✅ Mais fácil de testar, atualizar e manter a aplicação ao longo do tempo
- ✅ Múltiplas bibliotecas para economizar tempo de desenvolvimento
- ✅ Carregamento dinâmico para reduzir os tempos de carregamento
- ✅ Maior flexibilidade no desenvolvimento
- ✅ Experiência de usuário fluida
- ✅ Possibilita escalonamento horizontal
- ✅ Manutenção fácil
- ✅ Melhor agilidade

**Piral** é um poderoso framework open-source para construir aplicações web modulares, extensíveis e escaláveis. Ele foi projetado para suportar o conceito de micro frontends, permitindo que desenvolvedores criem aplicações web como um conjunto de componentes modulares que podem ser desenvolvidos e implantados de forma independente.

Como funciona o Piral? O Piral utiliza um mecanismo de carregamento dinâmico que permite carregar e descarregar micro frontends sob demanda, melhorando o desempenho da aplicação e reduzindo os tempos de carga. Ele oferece uma arquitetura de plugins que permite aos desenvolvedores expandir e personalizar a funcionalidade do framework por meio da criação de plugins.

O Piral permite que desenvolvedores compartilhem dependências entre diferentes micro frontends, reduzindo o tamanho geral da aplicação e melhorando o desempenho. Ele oferece um sistema centralizado de gerenciamento de estado, que permite aos desenvolvedores gerenciar o estado da aplicação em um único local.

Principais Benefícios do Framework Piral:

- ✅ Arquitetura adaptável para lidar com aplicações microfrontend em grande escala
- ✅ Facilitar o compartilhamento de código e recursos entre equipes
- ✅ Reduzir a dívida técnica e melhorar a qualidade do código
- ✅ Ciclos de desenvolvimento e implantação mais rápidos
- ✅ Poderoso mecanismo de agrupamento e cache
- ✅ API flexível e extensível

**Luigi Framework** é "o framework micro frontend pronto para empresas" que ajuda a construir interfaces e aplicativos web modulares, extensíveis, escaláveis e consistentes. Segue uma abordagem declarativa para a composição de interfaces, onde cada micro frontend declara suas dependências de outros micro frontends, e o framework cuida da resolução e carregamento dessas dependências.

Como o Luigi funciona? O Luigi oferece um sistema centralizado de configuração que permite aos desenvolvedores configurar e gerenciar facilmente as micro frontends da aplicação. Ele oferece um sistema de roteamento poderoso que permite aos desenvolvedores navegar facilmente entre diferentes micro frontends. O Luigi oferece um sistema compartilhado de gerenciamento de estado, que permite aos desenvolvedores gerenciar o estado da aplicação em um único local.

Principais Benefícios do Luigi Framework:

- ✅ Construa uma interface altamente interativa e responsiva para melhorar a experiência de usuário
- ✅ Navegação fácil entre diferentes micro frontends
- ✅ Flexibilidade para atender a necessidades específicas de personalização
- ✅ Arquitetura de plugins para customização funcional
- ✅ Compartilhamento fácil de dados entre a aplicação
- ✅ Incentiva a reutilização
- ✅ Carregamento sob demanda

**OpenComponents Framework** é um framework de micro frontend com leveza e flexibilidade para construir aplicações micro frontend modulares e fáceis de manter.

Como funcionam os OpenComponents? O OpenComponents utiliza a arquitetura Web Component para criar micro frontends independentes e reutilizáveis. Cada micro frontend é encapsulado em um elemento personalizado, que pode ser facilmente reutilizado em múltiplas aplicações.

Ela fornece uma API padronizada para micro frontends se comunicarem entre si, permitindo que compartilhem dados e estados de forma fluida. Essa API garante que todos os componentes sejam compatíveis, independentemente da tecnologia de front-end usada para construí-los.

Além disso, ele suporta uma variedade de tecnologias de front-end, incluindo React, Vue, Angular e JavaScript padrão. Essa flexibilidade permite que os desenvolvedores usem a pilha tecnológica mais adequada para sua aplicação, sem comprometer a arquitetura micro 
frontend.

Principais benefícios do OpenComponents Framework:

- ✅ Crie micro frontends independentes e reutilizáveis
- ✅ API padronizada para comunicação entre si
- ✅ Adequado para uma ampla variedade de casos de uso
- ✅ Carregamento de componentes sob demanda
- ✅ Fácil colaborar

**Mosaic Framework** é uma extensão revolucionária do renomado framework Apache Spark, projetada para enfrentar os desafios impostos por conjuntos de dados geoespaciais gigantescos. Essa tecnologia de ponta permite o processamento ultrarrápido até mesmo das informações geoespaciais mais complexas, abrindo um mundo de possibilidades para organizações orientadas por dados.

Como funciona o Mosaic? Com uma arquitetura modular e escalável para construir micro frontends, que permite que as equipes criem aplicações geoespaciais robustas e escaláveis. Ele permite que desenvolvedores construam componentes como microserviços autônomos, que podem ser facilmente integrados a outros componentes para formar uma aplicação completa. Essa abordagem garante que cada micro frontend seja responsável por sua funcionalidade e não esteja fortemente acoplada a outros componentes.

O modelo de computação distribuída da Mosaic permite que micro frontends sejam implantados de forma escalável e tolerante a falhas, garantindo que a aplicação possa lidar com grandes volumes de dados geoespaciais sem comprometer desempenho ou confiabilidade. A arquitetura flexível e modular da Mosaic permite que desenvolvedores misturem e combinem diferentes componentes para criar micro frontends personalizados, possibilitando que equipes criem aplicações adaptadas às suas necessidades específicas.

A natureza open-source da Mosaic significa que possui uma comunidade grande e ativa de desenvolvedores que estão constantemente adicionando novos recursos e funcionalidades ao framework. Isso garante que a Mosaic esteja sempre atualizada com as últimas tendências e melhores práticas no processamento de dados geoespaciais.

Principais benefícios do Mosaic Framework:

- ✅ Reduz o custo e a complexidade para gerenciar e escalar aplicações geoespaciais
- ✅ Suporta uma ampla variedade de linguagens de programação e bibliotecas
- ✅ Plataforma unificada para processamento, análise e visualização de dados
- ✅ Ambiente de computação distribuída
- ✅ Interface amigável ao usuário

A **NanoFrame** está emergindo rapidamente como líder no cenário micro frontend, trazendo uma simplicidade e eficiência sem precedentes ao desenvolvimento web.

Características Únicas: Arquitetura Ultra-Leve: NanoFrame foi projetada para projetos onde minimizar a carga útil é crucial. Sua arquitetura ultra-leve garante tempos de carregamento mais rápidos e desempenho aprimorado. Composição Intuitiva de Componentes: Desenvolvedores podem compor micro frontends de forma fluida com uma abordagem intuitiva baseada em componentes, aumentando a flexibilidade e a manutenibilidade. Integração Sem Esforço: O NanoFrame simplifica a integração com sistemas existentes, permitindo que desenvolvedores incorporem micro frontends em aplicações legadas com facilidade.

Principais Benefícios:

- ✅ Desempenho Aprimorado: A natureza leve do NanoFrame contribui para renderização mais rápida e melhor experiência do usuário.
- ✅ Integração Versátil: Desenvolvedores podem utilizar o NanoFrame em um espectro de projetos, desde aplicações de pequena escala até sistemas de nível empresarial.
- ✅ Desenvolvimento Pronto para o Futuro: A adaptabilidade do NanoFrame posiciona os desenvolvedores para os requisitos futuros, tornando-o uma escolha ideal para projetos em evolução.

O **FusionFront** está causando impacto como um framework abrangente de micro frontend, oferecendo uma fusão de versatilidade e arquitetura robusta.

Características Únicas: Carregamento Dinâmico de Componentes: O FusionFront introduz o carregamento dinâmico de componentes, permitindo que as aplicações carreguem apenas os componentes necessários, reduzindo os tempos iniciais de carregamento. Gestão Integrada de Estados: Um sistema de gerenciamento de estados integrado simplifica o fluxo de dados entre micro frontends, promovendo coesão e atualizações sincronizadas. Editor de Composição Visual: O FusionFront introduz um editor visual que simplifica a composição de micro frontends, tornando-o acessível tanto para desenvolvedores quanto para designers.

Principais Benefícios:

- ✅ Utilização Otimizada de Recursos: O carregamento dinâmico do FusionFront garante a utilização ótima dos recursos, contribuindo para uma aplicação mais eficiente.
- ✅ Desenvolvimento Colaborativo: O editor de composição visual facilita a colaboração entre desenvolvedores e designers, promovendo uma interface de usuário unificada e visualmente atraente.
- ✅ Arquitetura Escalável: O gerenciamento integrado de estados e o carregamento dinâmico do FusionFront lançam as bases para aplicações escaláveis e preparadas para o futuro.
