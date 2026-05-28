# RESUMO “CÓDIGO LIMPO”

# CAPÍTULO 2

 ## O capítulo 2 do livro Código Limpo apresenta a importância da escolha de nomes significativos no desenvolvimento de software. Como os nomes estão presentes em variáveis, funções, métodos, classes, arquivos e pacotes, a forma como são definidos influencia diretamente a legibilidade, compreensão e manutenção do código.
## Os nomes devem revelar claramente seu propósito, indicando o que representam, qual sua função e como são utilizados. Quando um nome precisa de comentários para ser entendido, significa que ele não está adequado. Exemplo:
## String n;

## Nesse caso, o nome n não informa seu significado nem sua finalidade. Para melhorar a compreensão, o autor sugere nomes mais descritivos, como:
## String nomeUsuario;
## double nota;
## double notaMedia;

## Outro ponto abordado é a necessidade de evitar informações erradas ou confusas. O autor explica que algumas abreviações podem gerar interpretações equivocadas. Por exemplo, utilizar hp como nome de variável pode causar confusão por também representar nomes de plataformas Unix. Da mesma forma, utilizar o nome accountList quando o armazenamento não for realmente uma List pode induzir o desenvolvedor ao erro. Nesse caso, nomes como accounts ou accountGroup seriam mais adequados. O capítulo também enfatiza a importância de fazer distinções significativas. Apenas alterar nomes com números ou palavras genéricas não resolve o problema da clareza. O uso de nomes como “int a1”, “int a2” e “int a3”, não transmite qualquer informação útil sobre o propósito das variáveis. Exemplos mais adequados seriam:
## int quantidadeAlunos;
## int quantidadeProfessores;

## Da mesma forma, o texto critica o uso de palavras vagas como Info, Data ou Object. Classes chamadas Product, ProductInfo e ProductData não deixam clara a diferença entre elas. Um exemplo mais significativo seria:
## class Produto;
## class ProdutoEstoque;
## class ProdutoHistoricoVendas;

## O autor também recomenda o uso de nomes pronunciáveis. Como a programação é uma atividade social, os desenvolvedores precisam conversar sobre o código constantemente. Pode-se comparar:
## double pdp = 100;
## com
## double precoDoProduto = 100;

## O segundo exemplo é mais claro, fácil de pronunciar e compreender durante discussões da equipe.
## Outro aspecto importante é utilizar nomes passíveis de busca. Variáveis compostas por apenas uma letra ou números isolados dificultam sua localização no código. Constantes e informações importantes devem possuir nomes específicos e descritivos. 
## Exemplo:
## int MAXIMO_ALUNOS_POR_TURMA = 30;
## Esse tipo de nome facilita buscas no sistema e reduz a possibilidade de erros.

## O capítulo também orienta evitar codificações desnecessárias e mapeamentos mentais. O leitor não deve precisar traduzir mentalmente o significado de uma variável. Embora letras como i e j sejam aceitáveis em pequenos laços de repetição, nomes genéricos dificultam a leitura em contextos maiores.
## Além disso, o texto apresenta regras para nomes de classes e métodos. Classes devem possuir substantivos, como:
## class Cliente;
## class Conta;
## class Endereco;

## Já os métodos devem utilizar verbos que indiquem ação, como:
## salvar();
## excluirPagina();
## postarPagamento();

## Métodos de acesso podem seguir o padrão JavaBeans com prefixos como get, set e is.

## O capítulo também orienta evitar nomes considerados “espertinhos”, piadas ou trocadilhos, pois podem dificultar a compreensão do sistema. Nomes objetivos e diretos tornam o código mais acessível para qualquer desenvolvedor que precise trabalhar nele futuramente.
## É importante também manter consistência nos termos utilizados. Empregar palavras diferentes para representar a mesma ação, como obter, pegar e recuperar, pode causar confusão. O ideal é definir um único padrão e mantê-lo em todo o projeto. Recomenda-se também utilizar nomes relacionados ao domínio da solução, aproveitando termos técnicos conhecidos na área da computação.

## A conclusão do capítulo 2 demonstra que a escolha de bons nomes é fundamental para a produção de códigos mais organizados, legíveis e fáceis de manter. Utilizar nomes claros, objetivos e consistentes melhora a comunicação entre desenvolvedores e contribui para a qualidade do software a longo prazo.

# CAPÍTULO 4

## O capítulo 4 do livro Código Limpo discute o uso de comentários no desenvolvimento de software e apresenta a ideia de que, embora alguns comentários sejam úteis, muitos acabam se tornando desnecessários ou prejudiciais. Comentários são considerados um “mal necessário”, utilizados principalmente quando o código não consegue expressar claramente sua intenção.
## O texto destaca que comentários envelhecem rapidamente. Conforme o código sofre alterações, os comentários podem deixar de representar corretamente o funcionamento do sistema, tornando-se enganosos.

## Comentários frequentemente são usados para justificar códigos ruins. Em vez de explicar um código confuso com comentários, é preferível reorganizá-lo e torná-lo mais claro. Um exemplo apresentado compara duas abordagens:
## Código com comentário:
## // Verifica se o funcionário tem direito a todos os benefícios
## if ((employee.flags & HOURLY_FLAG) &&
## (employee.age > 65))

## Código mais limpo e expressivo:
## if (employee.isEligibleForFullBenefits())

## Nesse caso, o próprio nome da função deixa clara a intenção do código, eliminando a necessidade do comentário.

## Alguns comentários podem de fato ser úteis. Entre eles estão os comentários legais, utilizados para informar direitos autorais, licenças e autoria de arquivos. Também existem comentários informativos, que explicam rapidamente o propósito de métodos ou padrões utilizados.
## Outro tipo considerado válido é o comentário de explicação da intenção, usado para registrar o motivo de determinada decisão no código. O exemplo apresentado ocorre em um método compareTo, no qual um comentário explica por que certos objetos são considerados “superiores” a outros:

## return 1; // somos superiores porque somos o tipo certo

## Comentários esclarecedores também podem ser úteis quando um trecho de código depende de bibliotecas externas ou estruturas difíceis de alterar. Nesses casos, o comentário ajuda a traduzir informações obscuras para algo mais compreensível.

## O texto ainda menciona comentários de alerta sobre consequências, utilizados para avisar outros programadores sobre riscos ou impactos de determinadas ações. Um exemplo é um teste que consome muito tempo e recursos:
## // Não execute a menos que você tenha tempo disponível
public void testWithReallyBigFile()

## Também são apresentados os comentários TODO, usados como lembretes temporários para tarefas futuras. 
## Exemplo:
## // TODO: remover implementação provisória

## Esses comentários indicam alterações pendentes, mas não devem servir como desculpa para manter códigos ruins indefinidamente.

## Outro uso aceitável é o destaque de informações importantes. O texto mostra um comentário explicando por que a função trim() é necessária:
## // A função trim remove espaços iniciais importantes
## String listItemContent = match.group(3).trim();

## Esse comentário ajuda a evitar alterações que poderiam comprometer o funcionamento do código.

## Em seguida, o capítulo aborda os chamados comentários ruins. Comentários enganadores são especialmente perigosos, pois podem transmitir informações incorretas e levar outros programadores ao erro. Também são criticados comentários longos, excessivos e “ruidosos”, que apenas repetem o que já está evidente no código.
## Além disso, é desencorajado explicar códigos inteiros através de comentários. O ideal é que o próprio código seja suficientemente claro. Comentários em HTML também são considerados inadequados, pois dificultam a leitura no editor e tornam o código visualmente poluído. Há ainda o alerta para informações excessivas e conexões pouco claras entre comentário e código. Um comentário deve possuir relação direta e evidente com o trecho que descreve, caso contrário apenas aumenta a confusão.

## Por fim, conclui-se que o código deve ser a principal fonte de verdade dentro de um sistema. Comentários só devem ser utilizados quando realmente agregarem valor e não puderem ser substituídos por um código mais claro, organizado e expressivo. Dessa forma, reduzir comentários desnecessários contribui para a criação de softwares mais limpos, compreensíveis e fáceis de manter.

# CAPÍTULO 5

## O capítulo 5 do livro Código Limpo destaca a importância da formatação no desenvolvimento de software, enfatizando que um código bem organizado transmite profissionalismo, clareza e atenção aos detalhes. A formatação é apresentada como uma forma de comunicação entre desenvolvedores, influenciando diretamente a legibilidade, manutenção e evolução do sistema.
## O texto ressalta que a funcionalidade de um software pode mudar constantemente, mas a legibilidade do código continuará impactando futuras alterações. Por isso, manter um padrão consistente de formatação facilita a compreensão e reduz a complexidade durante a manutenção do projeto.

## Na formatação vertical, é recomendado utilizar arquivos menores e organizados, pois são mais fáceis de entender do que arquivos extensos e desorganizados. O código deve seguir uma estrutura semelhante à de um artigo de jornal: as informações mais importantes e gerais devem aparecer primeiro, enquanto os detalhes surgem gradualmente ao longo da leitura.
## O capítulo também enfatiza a importância do espaçamento vertical entre conceitos. Linhas em branco ajudam a separar ideias diferentes, tornando o código visualmente mais claro e organizado. Da mesma forma, elementos relacionados devem permanecer próximos verticalmente, facilitando a identificação de relações entre variáveis, funções e métodos.

## Outro princípio importante é manter variáveis e funções próximas de seus locais de uso. Variáveis locais devem ser declaradas perto de onde serão utilizadas, enquanto variáveis de instância devem permanecer em locais previsíveis dentro da classe. Além disso, funções dependentes devem ficar próximas umas das outras, criando um fluxo natural de leitura de cima para baixo.
## Também é abordado  a afinidade conceitual, indicando que funções ou estruturas relacionadas por propósito devem permanecer agrupadas. Isso melhora a organização lógica do sistema e facilita a navegação pelo código.

## Já na formatação horizontal, recomenda-se manter linhas curtas para melhorar a leitura e evitar excesso de informações em uma única linha. O espaçamento horizontal deve ser utilizado para destacar relações e prioridades entre operadores e expressões, contribuindo para uma visualização mais clara da lógica do programa.

## A endentação é apresentada como um dos elementos mais importantes da formatação. Ela torna visível a hierarquia dos blocos, métodos e estruturas condicionais, permitindo que o desenvolvedor compreenda rapidamente a organização do código. Sem endentação adequada, o sistema se torna difícil de interpretar e manter.

## Há o alerta para evitar estruturas excessivamente compactas, pois podem esconder erros e reduzir a clareza do código. Mesmo em blocos pequenos, a organização visual deve ser mantida. Outro ponto relevante é a padronização dentro das equipes de desenvolvimento. Embora cada programador possua preferências individuais, todos devem seguir o mesmo estilo de formatação para garantir consistência em todo o projeto. Um sistema com padrões diferentes de escrita transmite desorganização e dificulta a leitura coletiva do código.

## O capítulo conclui que a formatação não possui apenas função estética, mas também organizacional e comunicativa. Um código bem formatado melhora significativamente sua legibilidade, facilita a manutenção e contribui para a criação de softwares mais compreensíveis e profissionais.


