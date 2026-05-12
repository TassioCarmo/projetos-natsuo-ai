\# Linguagens de Programação na Prática: Java, Haskell, Python, C, TypeScript e Zig



Como especialista em Ciência da Computação, frequentemente me perguntam quais linguagens valem a pena estudar e em quais contextos cada uma brilha. Neste artigo, vamos além dos manuais — apresento seis linguagens que representam paradigmas distintos e nichos importantes: \*\*Java\*\* (orientação a objetos clássica), \*\*Haskell\*\* (funcional pura), \*\*Python\*\* (scripting/multiuso), \*\*C\*\* (programação de sistemas), \*\*TypeScript\*\* (web/mobile) e \*\*Zig\*\* (emergente/nicho). Para cada uma, explico o que é, para que realmente serve (com casos reais) e trago curiosidades que surpreendem até mesmo programadores experientes.







\## 1. Java – Orientação a Objetos Clássica



\### O que é

Java é uma linguagem compilada (para bytecode) que roda sobre a \*\*Máquina Virtual Java (JVM)\*\*. Sua filosofia é “write once, run anywhere”: o mesmo código compilado executa em qualquer sistema que tenha uma JVM. Ela é \*\*fortemente tipada\*\* e adota o modelo de orientação a objetos de forma clássica (tudo deve pertencer a uma classe), com herança simples, interfaces e tratamento de exceções verificado. A JVM cuida do gerenciamento de memória por garbage collection e fornece um ecossistema de bibliotecas gigantesco.



\### Para que serve (casos de uso reais)

\- \*\*Sistemas corporativos em grande escala\*\*: Plataformas bancárias, ERPs, sistemas de folha de pagamento e governo eletrônico rodam tradicionalmente em Java EE / Jakarta EE ou Spring Framework. Exemplo: grande parte do backend de bancos como Nubank foi construída em Java (hoje com migração para Kotlin, mas a base é JVM).

\- \*\*Aplicações Android\*\*: Por muitos anos, Java foi a linguagem oficial do Android e ainda está presente em milhões de apps na Play Store.

\- \*\*Ecossistema Big Data\*\*: Ferramentas como Apache Hadoop, Apache Spark, Apache Kafka e Apache Flink são construídas em Java (ou Scala, rodando na JVM). O pipeline de dados de empresas como Twitter e LinkedIn dependem profundamente dessa stack.

\- \*\*Infraestrutura de nuvem\*\*: Serviços de back-end em arquiteturas de microsserviços, frequentemente com Spring Boot, são o pão de cada dia na AWS, Azure e GCP. A Netflix, por exemplo, tem uma parcela significativa de serviços Java.



\### Curiosidades (origem, particularidades, fatos pouco conhecidos)

\- \*\*Projeto Oak para TV a cabo\*\*: Java nasceu na Sun Microsystems nos anos 90, originalmente chamado Oak, com o objetivo de criar uma linguagem para decodificadores de TV interativa. A ideia não vingou, mas o time percebeu que o bytecode portável resolveria um problema maior: a internet.

\- \*\*O mascote Duke\*\*: Criado pela equipe de marketing, Duke é um personagem que aparecia em applets nos primeiros navegadores, mas seu design evoluiu para um ícone de cultura pop entre desenvolvedores.

\- \*\*Java pode ser “rápido”\*\*: O mito de lentidão vem das primeiras versões. Hoje, com JIT (Just-In-Time compilation) avançada, threading eficiente e garbage collectors de baixa latência (ZGC, Shenandoah), Java alcança desempenho comparável a linguagens nativas em workloads de longa duração.

\- \*\*O curioso caso do `public static void main`\*\*: A assinatura rígida do ponto de entrada é uma herança da decisão de projeto de sempre usar classes e de a JVM invocar métodos estáticos sem instanciar objetos.

\- \*\*Verbosa, mas com meta-programação “oculta”\*\*: Apesar da fama de verbosidade, Java possui um ecossistema de anotações que geram código em tempo de compilação (Lombok, MapStruct, Jakarta Persistence), o que aproxima a linguagem de uma abordagem declarativa.

\- \*\*O legado do Oracle vs. Google\*\*: A disputa judicial sobre o uso das APIs Java no Android marcou a história do direito autoral em software e influenciou como sistemas de API pública são encarados legalmente.



\---



\## 2. Haskell – Funcional Pura



\### O que é

Haskell é uma linguagem \*\*puramente funcional\*\*: todas as computações são expressas como avaliação de funções, sem efeitos colaterais explícitos a menos que encapsulados em estruturas como a mônada `IO`. Sua avaliação é \*\*preguiçosa\*\* (lazy), só calcula valores quando estritamente necessário, e possui um sistema de tipos estático forte com poderosa inferência. O mantra é “evitar sucesso a todo custo”, indicando que a comunidade prioriza a exploração de ideias inovadoras, mesmo que isso mantenha a adoção limitada.



\### Para que serve (casos de uso reais)

\- \*\*Compiladores e ferramentas de linguagens\*\*: O próprio compilador Glasgow Haskell Compiler (GHC) é majoritariamente escrito em Haskell. O Pandoc, conversor universal de documentos, é um projeto Haskell de enorme sucesso.

\- \*\*Sistemas de prova de teoremas e verificação formal\*\*: Haskell é terreno fértil para assistentes de prova e DSLs para verificação de hardware/software, como Cryptol (usado pela NSA) e linguagens inspiradas em Haskell para FPGA (Clash, Bluespec).

\- \*\*Finanças quantitativas\*\*: Bancos como Standard Chartered usam Haskell em sistemas de risco e precificação de derivativos, graças à segurança de tipos e à facilidade de expressar regras matemáticas complexas.

\- \*\*Processamento de dados em pipelines funcionais\*\*: Empresas como a Meta têm usado Haskell para manipulação de grandes bases de regras de negócio (ex.: Sigma, anti-abuso).

\- \*\*Educação e pesquisa\*\*: Universidades de ponta (Cambridge, Oxford, MIT) utilizam Haskell para ensinar programação funcional e raciocínio sobre programas.



\### Curiosidades (origem, particularidades, fatos pouco conhecidos)

\- \*\*Nome em homenagem a Haskell Curry\*\*: O matemático e lógico cujo trabalho na lógica combinatória influencia o paradigma funcional. A correspondência Curry-Howard, que conecta programas e provas matemáticas, é um dos pilares teóricos.

\- \*\*Mônadas vieram da matemática e salvaram o Haskell\*\*: No início, a pureza tornava as entradas/saídas um pesadelo. A adoção das mônadas (inspiradas na teoria das categorias) para encapsular efeitos colaterais foi a solução elegante que manteve a linguagem funcional pura e prática.

\- \*\*Estruturas de dados infinitas\*\*: Graças à lazy evaluation, você pode definir uma lista de todos os números primos `primes = sieve \[2..]` e o programa calculará apenas o segmento que realmente precisar. Isso é natural e eficiente.

\- \*\*A “frase do mal” de Simon Peyton Jones\*\*: Um dos pais da linguagem, ele disse que o objetivo de Haskell era ser “a melhor linguagem para gerar artigos acadêmicos” — uma alfinetada bem-humorada à própria comunidade.

\- \*\*A versão “1.0” demorou 30 anos\*\*: Haskell 98 foi um padrão, mas só em 2010 surgiu o Haskell 2010. A comunidade opera com extensões do GHC, que tornam a linguagem imensamente flexível, mas levantam debates sobre estabilidade.



\---



\## 3. Python – Scripting / Multiuso



\### O que é

Python é uma linguagem interpretada, dinâmica, com tipagem forte e dinâmica, amplamente conhecida por sua \*\*sintaxe limpa e indentação obrigatória\*\*. Embora não tenha sido projetada exclusivamente para scripting, seu amplo uso em automação e prototipação a consolida nesse papel. É multiparadigma: suporta programação procedural, orientada a objetos e funcional.



\### Para que serve (casos de uso reais)

\- \*\*Ciência de dados e IA/ML\*\*: O eco-ecossistema NumPy, pandas, scikit-learn, Matplotlib, TensorFlow, PyTorch e Jupyter fazem do Python a língua franca de cientistas de dados. A OpenAI treina e serve modelos usando Python, e o AlphaFold da DeepMind tem código Python.

\- \*\*Desenvolvimento web\*\*: Frameworks como Django (usado pelo Instagram) e Flask (usado pela Netflix para microsserviços) permitem construir desde MVPs até sistemas robustos.

\- \*\*Automação, DevOps e scripting\*\*: Ferramentas como Ansible, SaltStack e scripts de glue em pipelines CI/CD são geralmente em Python. O gerenciamento de infraestrutura em empresas como Dropbox e Google depende de Python.

\- \*\*Educação e prototipação\*\*: Python é a porta de entrada de milhões de programadores (Codecademy, Coursera) e a ferramenta predileta para prototipar algoritmos antes de implementar em produção com outra linguagem.

\- \*\*Computação científica e engenharia\*\*: Simulações, processamento de imagens (OpenCV via Python) e bioinformática (Biopython) o utilizam pesadamente.



\### Curiosidades (origem, particularidades, fatos pouco conhecidos)

\- \*\*Nascido nas férias de Natal\*\*: Guido van Rossum iniciou o projeto em dezembro de 1989, como um hobby para se ocupar enquanto seu escritório no CWI (Holanda) estava fechado. O nome não veio da cobra, mas do grupo de comédia Monty Python — os tutoriais são recheados de referências como “spam” e “eggs”.

\- \*\*O Zen do Python\*\*: Digite `import this` no interpretador e leia os 19 princípios da filosofia de design. Um deles (“Deve existir apenas uma maneira óbvia de fazer algo”) reflete a obsessão pela legibilidade.

\- \*\*Guido, o Ditador Benevolente Vitalício (BDFL)\*\*: Até 2018, Guido tinha a palavra final em decisões de evolução da linguagem. Ele se demitiu do cargo após a controvérsia sobre a PEP 572 (o operador “walrus” `:=`), demonstrando a paixão da comunidade.

\- \*\*A quebra do Python 3\*\*: A transição do Python 2 para o 3 levou mais de uma década. Grandes empresas como o Google adiaram ao máximo a migração. A “death clock” do Python 2 foi um marco em 2020.

\- \*\*Easter eggs escondidos\*\*: Além do Zen, há a piada do antigravity (`import antigravity`, que abre um quadrinho do xkcd sobre Python) e o `\_\_hello\_\_`. A comunidade adora essas brincadeiras.

\- \*\*GIL, o vilão incompreendido\*\*: O Global Interpreter Lock impede que threads Python executem bytecode simultaneamente, o que gera debates calientes. Na prática, muitas workloads contornam isso com multiprocessing ou integração com extensões em C que liberam a GIL.



\---



\## 4. C – Linguagem de Sistema



\### O que é

C é uma linguagem \*\*compilada, procedural e de médio nível\*\*, que oferece controle direto sobre a memória através de ponteiros. Foi projetada para escrever sistemas operacionais e se mantém como a base sobre a qual grande parte da infraestrutura de software moderna é erguida. Seu padrão ANSI/ISO evoluiu em várias edições, sendo a C17 a mais recente amplamente adotada.



\### Para que serve (casos de uso reais)

\- \*\*Sistemas operacionais e kernels\*\*: O kernel Linux, o núcleo do Windows (em grande parte), o macOS e o iOS (baseados em XNU) e incontáveis RTOS embarcados são escritos em C. Sem C, não haveria Unix.

\- \*\*Drivers e firmware\*\*: Quando o hardware precisa de comunicação de baixo nível, C é a escolha. Praticamente todo dispositivo, de roteadores a controladores de voo, tem firmware em C.

\- \*\*Engines de jogos e softwares de tempo real\*\*: A série Doom (id Tech), Quake e muitos motores atuais possuem núcleos críticos em C, onde cada microssegundo importa.

\- \*\*Compiladores, interpretadores e runtimes\*\*: O CPython (Python), o YARV (Ruby), o motor V8 (C++ mas base C-like) e o próprio GCC são majoritariamente escritos em C.

\- \*\*Bibliotecas criptográficas e servidores de alto desempenho\*\*: OpenSSL, SQLite, Redis e Nginx têm suas implementações de referência em C, primando por desempenho e controle fino de recursos.



\### Curiosidades (origem, particularidades, fatos pouco conhecidos)

\- \*\*Dennis Ritchie e o casamento com Unix\*\*: Criada em 1972 no Bell Labs, a linguagem evoluiu a partir do B (que veio de BCPL) para reescrever o Unix, até então em assembly. O livro “The C Programming Language” (K\&R) virou uma bíblia.

\- \*\*O primeiro “Hello, World!” público\*\*: O exemplo canônico de programa surgiu nesse livro e se tornou o ritual de iniciação de todo programador.

\- \*\*Comportamento indefinido não é erro do programador (às vezes)\*\*: C é famosa por permitir códigos cujo resultado é imprevisível (UB). Isso possibilita otimizações extremas pelo compilador, mas é fonte de bugs insidiosos. O clássico “o compilador pode literalmente fazer qualquer coisa, inclusive fazer o jogo da velha funcionar” tornou-se um meme didático.

\- \*\*Char pode não ter 8 bits\*\*: O padrão define que `char` tem tamanho “um byte”, mas o byte pode ter mais de 8 bits em arquiteturas exóticas (DSPs, mainframes). Isso é uma armadilha para hardware moderno que assume 8 bits.

\- \*\*C não tem especificação de performance, mas…\*\*: O padrão C não faz promessas sobre velocidade. O desempenho está atrelado à qualidade do compilador e ao hardware. Ainda assim, o baixo nível de abstração normalmente oferece o melhor potencial de otimização.

\- \*\*“C é uma navalha afiada”\*\*: Apesar de pequena (a especificação tem cerca de 700 páginas, muito menos que C++ ou Java), sua simplicidade combinada com o poder dos ponteiros é traiçoeira. Aprender a aparar a memória exige disciplina e ferramentas como Valgrind e AddressSanitizer.



\---



\## 5. TypeScript – Web / Mobile



\### O que é

TypeScript é um \*\*superset tipado do JavaScript\*\* desenvolvido pela Microsoft. Todo código JavaScript válido é também TypeScript, mas o TS adiciona \*\*tipagem estática opcional, interfaces, tipos genéricos, enums e uma análise de código muito mais sofisticada\*\*. Ele é transcompilado para JavaScript puro, podendo rodar em qualquer navegador, Node.js, Deno ou React Native.



\### Para que serve (casos de uso reais)

\- \*\*Desenvolvimento front-end escalável\*\*: Angular foi construído em TypeScript desde o início, e React e Vue oferecem suporte de primeira classe. O portal do Azure, o Visual Studio Code (escrito em TS/Electron) e o site do Airbnb usam TypeScript para garantir manutenabilidade.

\- \*\*Back-end com Node.js e Deno\*\*: Frameworks como NestJS (Node) e os módulos nativos do Deno incentivam fortemente o uso de TypeScript, permitindo compartilhar tipos entre front e back-end (monorepo). Grandes serviços da Microsoft e do Slack migraram seus back-ends para TS.

\- \*\*Aplicações mobile\*\*: React Native e NativeScript suportam TypeScript, trazendo tipagem segura para apps iOS e Android. Empresas como Shopify e Walmart construíram apps mobile com essa stack.

\- \*\*Ferramentas de linha de comando e CLIs\*\*: TypeScript é a escolha por trás de muitos CLIs modernos (ex.: tsc, o compilador do próprio TS, e a CLI do Angular) devido à fácil distribuição via npm e à robustez de tipos.

\- \*\*Sistemas de tipagem como documentação viva\*\*: Em projetos com centenas de desenvolvedores (Microsoft 365, Google), os tipos auto-documentam contratos de APIs e previnem regressões silenciosas que seriam comuns em JS puro.



\### Curiosidades (origem, particularidades, fatos pouco conhecidos)

\- \*\*Anders Hejlsberg, o criador prolífico\*\*: O pai do TypeScript também criou Turbo Pascal, Delphi e C#. Sua experiência com tipagem estática em ambientes corporativos é um dos motivos do design elegante e pragmático do TS.

\- \*\*“JavaScript que escala”\*\*: Esse slogan capta exatamente o propósito. TypeScript não tenta reinventar o ecossistema, mas sim tornar aplicações JS grandes mais seguras e gerenciáveis, inclusive adicionando refatoração confiável.

\- \*\*O compilador é auto-hospedado\*\*: O TypeScript compiler (tsc) foi reescrito em… TypeScript. Isso demonstra confiança na linguagem e obriga a equipe a lidar com as mesmas dores dos usuários.

\- \*\*Tipos são apagados em tempo de execução\*\*: O navegador nunca vê TypeScript. Não há overhead de runtime; os tipos servem apenas para verificação em tempo de compilação. Isso mantém a performance idêntica ao JavaScript puro.

\- \*\*Tipagem estrutural, não nominal\*\*: Ao contrário de Java ou C#, dois tipos são compatíveis se possuem a mesma forma (estrutura), e não se compartilham explicitamente o mesmo nome. Isso se alinha com o espírito dinâmico do JS.

\- \*\*O nascimento do .d.ts\*\*: A comunidade criou o DefinitelyTyped, um repositório com milhares de arquivos de declaração de tipos para bibliotecas JavaScript não escritas em TS. É um dos maiores exemplos de colaboração open-source em massa.



\---



\## 6. Zig – Emergente / Nicho



\### O que é

Zig é uma linguagem de \*\*programação de sistemas compilada\*\* que se apresenta como uma alternativa moderna ao C. Ela oferece \*\*controle fino sobre memória\*\* sem garbage collector, porém com alocadores explícitos e um sistema de erros robusto (sem exceções). Seu diferencial está no suporte a \*\*execução em tempo de compilação (comptime)\*\*, na \*\*ausência de fluxo de controle oculto\*\* e na capacidade de compilar código C/C++ diretamente, servindo como um toolchain completo e cross-compilador sem dependências externas.



\### Para que serve (casos de uso reais)

\- \*\*Desenvolvimento de sistemas de baixo nível\*\*: Kernels experimentais, drivers e sistemas operacionais (como o microkernel Redox, que utiliza Rust mas Zig está sendo explorada para ferramentas). A promessa de “sem hidden allocations” atrai quem faz software para embarcados e consoles de jogos.

\- \*\*Ferramentas de linha de comando e build systems\*\*: O próprio compilador do Zig é usado como ferramenta para compilar C/C++ com cross-compilation automatizada. Projetos como Bun (runtime JavaScript) incorporam Zig para partes críticas de desempenho.

\- \*\*Desenvolvimento de jogos e engines\*\*: A comunidade está criando bindings e engines em Zig, valorizando sua interoperabilidade com C (SDL, OpenGL) e a performance previsível, sem pausas de GC.

\- \*\*Segurança cibernética e sistemas criptográficos\*\*: Zig incentiva lidar com erros explicitamente (`try`, `catch`, `errdefer`), reduzindo vulnerabilidades de controle de fluxo. Alguns desenvolvedores de ferramentas de segurança migram partes de C para Zig em busca de maior expressividade e menor superfície de bugs.

\- \*\*Aprender como compiladores funcionam\*\*: A filosofia de “nada escondido” e a implementação auto-hospedada (escrita em Zig) tornam a linguagem um excelente objeto de estudo para quem quer compreender compiladores modernos.



\### Curiosidades (origem, particularidades, fatos pouco conhecidos)

\- \*\*Começou como um projeto de um único desenvolvedor\*\*: Andrew Kelley iniciou Zig em 2015, insatisfeito com ferramentas C/C++ e querendo “uma linguagem simples para manter software robusto e ótimo”. Ainda não atingiu a versão 1.0, mas já é usada em produção para toolchains internos.

\- \*\*“Nenhum fluxo de controle oculto”\*\*: Não há sobrecarga de operadores imprevisível, não há exceções que podem saltar camadas, e o gerenciamento de memória nunca chama funções inesperadas. Isso faz com que `@import("std").debug.print` seja tão transparente quanto um printf, mas sem riscos mágicos.

\- \*\*Comptime é a “super-macro”\*\*: Enquanto C depende de macros pré-processador frágeis e C++ de templates, Zig permite executar qualquer função em tempo de compilação (`comptime`) e gerar tipos ou valores. O famoso `std.testing.expect` tira proveito disso para reflexão.

\- \*\*Cross-compilação sem esforço\*\*: Você pode compilar para qualquer alvo (Windows, macOS, Linux, FreeBSD, ARM, RISC-V) apenas passando `-target`, sem instalar toolchains específicos. O compilador trata formatos de objeto e linkagem diretamente.

\- \*\*A filosofia do “Zig Zen”\*\*: A comunidade adotou um conjunto de princípios, como “comunique intenção precisamente”, “memória é um recurso; seja explícito” e “trate os erros com respeito”. Não é apenas marketing; o design da linguagem reflete isso.

\- \*\*Zig como toolchain para C/C++\*\*: Um dos maiores “branch” de uso é a compilação de projetos C/C++ com o comando `zig cc` ou `zig c++`, que substitui o GCC/Clang e oferece cross-compilation, ressaltando que Zig não quer matar C, mas complementá-lo.



\---



\## Conclusão



Cada linguagem aqui apresentada incorpora um pedaço da história e das necessidades da computação:



\- \*\*Java\*\* mostra como a portabilidade e o ecossistema dominam o mundo corporativo.

\- \*\*Haskell\*\* prova que a pureza funcional pode resolver problemas reais com elegância, mesmo que fora do mainstream.

\- \*\*Python\*\* é a cola universal que conecta dados, inteligência artificial e automação com uma sintaxe que prioriza humanos.

\- \*\*C\*\* permanece como o alicerce sobre o qual tudo executa — insubstituível quando é preciso tocar no metal.

\- \*\*TypeScript\*\* transforma o caos criativo do JavaScript em engenharia previsível para aplicações de milhões de usuários.

\- \*\*Zig\*\* acena com uma nova forma de fazer sistemas: segura, explícita e sem os acúmulos históricos que dificultam a manutenção.



Conhecer profundamente essas linguagens não é apenas adquirir sintaxe, mas expandir seu repertório de pensamento computacional. Cada uma é uma janela para um paradigma e uma comunidade com valores próprios — eis a verdadeira riqueza da Ciência da Computação.

