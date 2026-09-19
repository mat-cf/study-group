### Notas
#### Intro
Uso intensivo de dados = core do business é dados. Isso define o tom do livro como um todo e para onde iremos por aqui. 
Gosto de como o autor dá praticamente uma receita de como fazer uma aplicação à prova de falhas, levantando maneiras e práticas que sistemas com uso intensivo de dados usam, sendo elas:
- Armazenamento de dados (**Database**)
- Lembrança dos resultados (**Cache**)
- Mecanismo de busca (**Indexes**)
- Tratamento de fluxos (**ETLs**)
- Processamento periódico (**Batch processing**)
#### Database
Um ponto curioso foi que entendi finalmente o porquê de usarem _transaction_ para falar de uma gravação. Softwares dos primeiros dias de processamento de dados usavam essa palavra pois correspondia a uma transação comercial. 

Também achei interessante a abordagem entre **OLTP** x **OLAP**. Não tive tanto contato contato com esse tipo de terminologia, mas ler e entender consolidou um pouco mais esse conhecimento. Em especial a **tabela 1.1**, que exemplifica bem as diferenças entre _sistemas analíticos_ e _sistemas operacionais_: 

| Sistemas Operacionais | Sistemas Analíticos     |
| --------------------- | ----------------------- |
| Backend               | Negócios                |
| Infra                 | Read-only               |
| Modifica dados        | Processamento e analise |
| Gigabytes             | Terabytes               |

Além dessas diferenças, também é explorada as funções das áreas de _Engenharia de Dados_ e _Engenharia de Analytics_. 
Entendo que, eventualmente essas duas áreas acabam mesclando muitas funções dentro de um negócio que escala. 
> Em geral, é bom que cada S.O tenha a sua própria DB

#### Data Warehouses e Data Lakes
Novamente, por mais que eu tivesse um contato indireto com áreas que trabalham mais diretamente com esses tópicos, o máximo que eu sabia sobre a diferença entre essas duas era sobre o volume e tipo dos dados que lidavam. 

Data Warehouses utilizam mais dados estruturados e Data Lakes podem guardar qualquer tipo de dado. Isso é refletido também na carga de trabalho e função que desempenham: Warehouses são melhores para ML, código especializado. Lakes funcionam bem para guardar dados em geral e são uma opção mais barata. O **AWS S3** é um exemplo de Data Lake. Já mexi em trabalhos e estudos. 

> O processo de ingestão de dados também ficou mais claro. ETL ou **Extract Transform Load** é o padrão para isso

 A parte de sistemas de registro e dados derivados foi esclarecedora também.
#### Nuvem x Self-Host
Aqui entra uma das partes em que mais me interessei. Gosto muito de Cloud e eventualmente pretendo mergulhar mais nisso, com algum curso ou terminar a certificação da AWS, mas auto-hospedar serviços é algo que gosto muito. Sinto que consigo ter mais autonomia dos meus dados e acabo com um conhecimento mais profundo sobre cada parte do geral. 

Aqui, o capítulo aborda de um jeito que faz mais sentido para o mercado corporativo e define bem quando deve-se optar pelas soluções: Serviços triviais e rotineiros podem ser delegados para Cloud, enquanto tecnologias e ideias proprietárias/diferenciais prefere-se hospedar internamente. Cada uma dessas escolhas possui riscos, como perder os dados ou maior aprofundamento técnico, mas isso é bem abordado na página 32.

> Na era da Cloud, otimização de desempenho é otimização de custo.

Na parte das desvantagens foi onde consegui me identificar bem. Já tive problemas com quase todos os pontos levantados. Bom saber que não estou sozinho e que é um sentimento geral. 
#### Microsserviços
No meio corporativo, é o que mais faz sentido e o trade-off fica interessante. Operações escalam de maneiras diferentes, e criam-se necessidades diferentes baseadas em um tipo de produto. Com isso, faz mais sentido dividir entre pequenas partes que fazem o todo. 
**Microsserviços representam uma resposta técnica para um problema humano**

Acho que a maioria dos sistemas grandes que mexi tem uma arquitetura baseada em Microsserviços (muitos deles usando Java e Spring Boot). 

Apesar da implementação e testes serem mais difíceis, não vejo como um drawback muito forte, visto que sistemas que usam essa arquitetura geralmente contam também com documentações claras sobre como testar ou mexer. Não é a regra, mas em geral comigo foi assim.
#### Segurança dos dados e Leis
Essa é uma seção curta mas profundamente interessante, estou animado para aprofundar mais nesse tópico, já que é algo que vou mexer no trabalho. Mas o ponto principal é a **minimização de dados**, termo utilizado em resposta ao Big Data, que é sobre guardar o máximo de dados possíveis. 

-----

#### Resumo
Um video complementar que assisti em partes é a introdução aos Sistemas Distribuídos do MIT [Lecture 1: Introduction](https://www.youtube.com/watch?v=cQP8WApzIQQ&t=2s), que aborda parte dos tópicos discutidos nesse capítulo, também de forma mais superficial, mas que acho um bom adendo. Vou ver isso depois. 
Em geral, esse capítulo serviu para relembrar algumas das coisas que já vi tanto no trabalho quanto na faculdade (em aulas de Sistemas de Informação e outras das áreas de dados), consolidando alguns outros conhecimentos. 
Ainda não está muito claro pra mim se as diferenças entre sistemas OLTP e OLAP são tão explicitas ou se é ok fazer consultas e processamento no mesmo sistema, mas acredito que é algo que depende do volume de dados, discutido no começo desse livro. 
