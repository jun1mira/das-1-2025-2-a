# 📚 Primeiro Bimestre

**Bibliografia Principal:**
- Livro Eng Soft Moderna - Cap 7
- Fundamentos da Arquitetura de Software
- Livro Padrões de Projeto
- Livro Engenharia de Software - Padrões de Projeto
- [Padrões de Projeto Guru](https://refactoring.guru/design-patterns)

---

## 📍 ABSTRAÇÃO
**Conceito**: Representar elementos do mundo real no software
- **Exemplo**: Classes `entity` em Java = tabelas do banco
- **Analogia**: Mapa de uma cidade (simplifica a realidade)

**⚡ Dica rápida**: Abstração = "esconder complexidade, mostrar essência"

**O que lembrar**: Abstração simplifica o mundo real para o código

---

## 📍 PRINCÍPIOS DE PROJETO DE CÓDIGO
**Objetivo**: Código mais fácil de entender, manter e evoluir

### Organização por Camadas
```
Controller  → API Rest / HTML (entrada)
Service     → Lógica de negócio (processamento)  
Repository  → Conexão com BD (dados)
Entity      → Dados/modelos (estrutura)
Config      → Configurações (setup)
```

**⚡ Dica rápida**: "Controller recebe, Service processa, Repository salva"

**O que lembrar**: Cada camada tem uma responsabilidade específica

---

## 📍 PADRONIZAÇÃO DE CÓDIGO
**Conceito**: Convenções para código consistente
- **Java**: `CamelCase` (classes), `camelCase` (variáveis)
- **Benefício**: Facilita leitura e manutenção

**⚡ Dica rápida**: "Código padronizado = código legível"

**O que lembrar**: Convenções tornam o código mais profissional

---

## 📍 OCULTAMENTO DE INFORMAÇÃO (ENCAPSULAMENTO)
**Conceito**: Esconder detalhes internos, expor apenas o necessário
- **Como**: `private` (atributos) + `get/set` (acesso controlado)
- **Benefício**: Evita dependências desnecessárias

**⚡ Dica rápida**: "Private = segredo, Public = público"

**O que lembrar**: Encapsulamento protege a implementação interna

---

## 📍 COESÃO
**Conceito**: Elementos trabalham em torno de uma única responsabilidade
- **Alta coesão**: Uma classe = uma função específica
- **Baixa coesão**: Uma classe = várias funções misturadas

**⚡ Dica rápida**: "Coesão alta = classe focada"

**O que lembrar**: Quanto maior a coesão, mais organizado o código

---

## 📍 ACOPLAMENTO
**Conceito**: Nível de dependência entre classes/módulos
- **Baixo acoplamento**: Classes independentes ✅
- **Alto acoplamento**: Classes muito dependentes ❌

### Classe Anêmica
- Só tem: nome + atributos + getters/setters
- **Problema**: Sem lógica de negócio

**⚡ Dica rápida**: "Acoplamento baixo = independência"

**O que lembrar**: Baixo acoplamento = fácil manutenção

---

## 📍 DIAGRAMAS UML
### Tipos de Setas
- `→` (vazia contínua): **Herança** - "Cachorro É UM Animal"
- `⟶` (vazia pontilhada): **Interface** - "Professor ENSINA Aluno"  
- `⟶` (preenchida): **Associação** - "Carro USA Motor"

**⚡ Dica rápida**: "Herança = é, Interface = faz, Associação = tem"

**O que lembrar**: Cada seta tem significado específico no UML

---

## 📍 DÉBITO TÉCNICO
**Conceito**: Código mal implementado que causará problemas futuros
- **Analogia**: Dívida que precisa ser paga com juros
- **Solução**: Refatoração constante

**⚡ Dica rápida**: "Débito técnico = problema futuro"

**O que lembrar**: Código ruim hoje = dor de cabeça amanhã

---

## 📍 SOLID - PRINCÍPIOS FUNDAMENTAIS
**Objetivo**: Usar OOP corretamente (código coeso, desacoplado, flexível)

### S - Single Responsibility Principle
**Conceito**: Uma classe = uma responsabilidade
- **Problema**: Classe com múltiplas funções
- **Solução**: Dividir em classes menores

**⚡ Dica rápida**: "Uma classe = uma razão para mudar"

**O que lembrar**: Responsabilidade única = código mais limpo

### I - Interface Segregation Principle  
**Conceito**: Classe não deve implementar métodos que não usa
- **Problema**: Interface muito grande
- **Solução**: Interfaces menores e específicas

**⚡ Dica rápida**: "Interface pequena = implementação fácil"

**O que lembrar**: Interfaces específicas > interfaces genéricas

### L - Liskov Substitution Principle
**Conceito**: Classe filha deve poder substituir classe pai
- **Exemplo**: `Cachorro` pode ser usado como `Animal`
- **Benefício**: Código previsível e seguro

**⚡ Dica rápida**: "Filho deve funcionar como pai"

**O que lembrar**: Substituição sem quebrar funcionalidade

### O - Princípio Aberto/Fechado
**Conceito**: Aberto para extensão, fechado para modificação
- **Aberto**: Adicionar funcionalidades sem mexer no existente
- **Fechado**: Evitar alterações que quebrem o sistema

**⚡ Dica rápida**: "Estenda, não modifique"

**O que lembrar**: Extensão > Modificação

### D - Princípio da Inversão de Dependências
**Conceito**: Depender de abstrações, não de implementações
- **Problema**: Classe depende de classe concreta
- **Solução**: Depender de interface/contrato

**⚡ Dica rápida**: "Dependa do contrato, não da implementação"

**O que lembrar**: Abstrações > implementações concretas

---

## 📍 ARQUITETURA MVC
**Conceito**: Dividir responsabilidades em 3 camadas

```
M = Model    → Dados/Entidades
V = View     → Interface/UI  
C = Controller → Intermediário (recebe → processa → entrega)
```

**Fluxo**: `View → Controller → Model → Controller → View`

### Exemplo Prático - Swing Java
```java
// View (Janelinha.java)
public class Janelinha extends JFrame {
    private JButton botaozinho;
    private Controlador controlador;
    
    public Janelinha() {
        botaozinho = new JButton("ME CLICA");
        controlador = new Controlador();
        botaozinho.addActionListener(controlador);
        add(botaozinho);
    }
}

// Controller (Controlador.java)
public class Controlador implements ActionListener {
    @Override
    public void actionPerformed(ActionEvent e) {
        meClica();
    }
    
    private void meClica() {
        JOptionPane.showMessageDialog(null, "NAO ACREDITO");
    }
}
```

**⚡ Dica rápida**: "MVC = Modelo, Visão, Controle"

**O que lembrar**: MVC separa dados, interface e lógica

---

## 📍 COMPOSIÇÃO vs HERANÇA
**Conceito**: Prefira combinar objetos (composição) a herdar
- **Herança**: Rígida, difícil de manter
- **Composição**: Flexível, reutilizável

**⚡ Dica rápida**: "Composição = montar, Herança = copiar"

**O que lembrar**: Composição > Herança na maioria dos casos

---

## 📍 PRINCÍPIO DE DEMETER
**Conceito**: Reduzir acoplamento, evitar variáveis globais
- **Regra**: "Fale apenas com amigos diretos"
- **Benefício**: Menos dependências

**⚡ Dica rápida**: "Converse só com quem conhece bem"

**O que lembrar**: Menos acoplamento = mais flexibilidade

---

## 📍 ABSTRAÇÕES EM JAVA
### Tipos de Abstração
- **Classe**: Atributos + métodos
- **Interface**: Contrato (métodos sem implementação)
- **Classe Abstrata**: Mistura classe + interface

**⚡ Dica rápida**: "Interface = contrato, Classe = implementação"

**O que lembrar**: Cada tipo tem seu uso específico

---

## 📍 DESIGN PATTERNS
**Conceito**: Soluções reutilizáveis para problemas recorrentes
**Origem**: Gang of Four (1994)
**Referência**: [Padrões de Projeto Guru](https://refactoring.guru/design-patterns)

### Categorias
- **Criacionais**: Criação de objetos (Singleton, Factory)
- **Estruturais**: Composição (Adapter, Facade)  
- **Comportamentais**: Interação (Observer, Strategy)

**⚡ Dica rápida**: "Patterns = receitas testadas"

**O que lembrar**: 23 padrões divididos em 3 categorias

---

## 📍 FACTORY METHOD
**Problema**: Múltiplas criações de objetos similares
**Solução**: Centralizar criação em método fábrica

### Exemplo Prático
```java
// ❌ Antes (ruim)
void f() { TCPChannel c = new TCPChannel(); }
void g() { TCPChannel c = new TCPChannel(); }

// ✅ Depois (bom)  
class ChannelFactory {
  public static Channel create() { return new TCPChannel(); }
}
void f() { Channel c = ChannelFactory.create(); }
```

**⚡ Dica rápida**: "Factory = fábrica de objetos"

**O que lembrar**: Centralizar criação = fácil manutenção

---

## 📍 SINGLETON
**Problema**: Múltiplas instâncias desnecessárias
**Solução**: Garantir apenas uma instância global

### Exemplo Prático
```java
public class Logger {
    private static Logger instance;
    private Logger() {} // construtor privado
    
    public static Logger getInstance() {
        if (instance == null) {
            instance = new Logger();
        }
        return instance;
    }
}
```

**⚡ Dica rápida**: "Singleton = um só no sistema"

**O que lembrar**: Uma instância global para recursos compartilhados

---

## 📍 OBSERVER
**Conceito**: Notificar múltiplos objetos sobre mudanças
**Estrutura**: Subject (observado) + Observer (interessados)

### Exemplo Prático
```java
// Subject notifica → Observers reagem
Publisher publisher = new Publisher();
publisher.addObserver(new Subscriber("Alice"));
publisher.notifyObservers("Nova mensagem!");
```

**⚡ Dica rápida**: "Observer = sistema de notificações"

**O que lembrar**: Um para muitos = Observer pattern

---

## 📍 ARQUITETO DE SOFTWARE
### Expectativas
- **Técnica**: Decisões estruturais importantes
- **Comunicação**: Equipes Dev + Ops + Negócios  
- **Qualidade**: Performance, escalabilidade, segurança

### Decisões de Arquitetura
- **Impacto**: Moldam o futuro do sistema
- **Tipos**: Estilos, padrões, frameworks, tecnologias
- **Característica**: Difíceis de modificar depois

**⚡ Dica rápida**: "Arquiteto = decisões que definem o futuro"

**O que lembrar**: Decisões arquiteturais = impacto de longo prazo

---

## 📍 ANÁLISE CONTÍNUA
**Conceito**: Revisar periodicamente se arquitetura atende demandas
- **Objetivo**: Identificar melhorias e ajustes
- **Frequência**: Regular e proativa

**⚡ Dica rápida**: "Arquitetura = processo contínuo"

**O que lembrar**: Arquitetura evolui com o negócio

---

## 📍 ATUALIZAÇÃO CONSTANTE
**Necessidade**: Tecnologia evolui rapidamente
- **Risco**: Soluções ultrapassadas
- **Solução**: Aprendizado contínuo

**⚡ Dica rápida**: "Arquiteto atualizado = decisões assertivas"

**O que lembrar**: Tecnologia muda = arquiteto deve acompanhar

---

## 📍 DOMÍNIO DO NEGÓCIO
**Conceito**: Compreender objetivos e processos da organização
- **Benefício**: Alinhar arquitetura às metas estratégicas
- **Resultado**: Soluções com valor real

**⚡ Dica rápida**: "Arquiteto = ponte entre técnico e negócio"

**O que lembrar**: Arquitetura deve servir ao negócio

---

## 📍 DEVOPS
**Conceito**: Integração Dev + Ops para melhor colaboração
**Cultura**: Equipes compartilham práticas e ferramentas

### Benefícios
- **Ciclo mais rápido**: Entregas menores e automatizadas
- **Melhoria contínua**: Feedback constante
- **Maior colaboração**: Comunicação eficaz
- **Maior estabilidade**: Automação + monitoramento

**⚡ Dica rápida**: "DevOps = Dev + Ops trabalhando juntos"

**O que lembrar**: DevOps = cultura de colaboração

---

## 📍 ARQUITETURA vs DESIGN
### Arquitetura
- **Escopo**: Decisões estruturais importantes
- **Impacto**: Qualidade, evolução, manutenção
- **Modificação**: Difícil de mudar
- **Exemplos**: Estilos, padrões, tecnologias

### Design  
- **Escopo**: Decisões de nível baixo
- **Impacto**: Organização interna de componentes
- **Modificação**: Mais fácil de mudar
- **Exemplos**: Classes, métodos, detalhes

**⚡ Dica rápida**: "Arquitetura = estrutura, Design = detalhes"

**O que lembrar**: Arquitetura define estrutura, Design implementa detalhes

---

## 📍 ARQUITETO MODELO T
### Formação
- **Barra horizontal**: Conhecimento amplo (diversas áreas)
- **Barra vertical**: Conhecimento profundo (especialização)

### Áreas Amplas
- Linguagens, bancos, nuvem, DevOps, segurança, redes

### Especializações
- Microsserviços, performance, segurança

**⚡ Dica rápida**: "T = amplo + profundo"

**O que lembrar**: Arquiteto = amplitude + profundidade

---

## 📍 TRADE-OFF
**Conceito**: Avaliar consequências de cada escolha arquitetural
**Realidade**: Toda decisão tem ganhos e perdas

### Exemplo: Microsserviços
- **Ganhos**: Escalabilidade, flexibilidade
- **Perdas**: Complexidade operacional, custos

**⚡ Dica rápida**: "Trade-off = ganha aqui, perde ali"

**O que lembrar**: Não existe solução perfeita, apenas consciente

---

## 📍 REQUISITOS
### Funcionais
- **Definição**: Telas que podemos ver
- **Exemplo**: Login, cadastro, relatórios

### Não Funcionais  
- **Definição**: Requisitos que precisamos cumprir
- **Exemplo**: Performance, segurança, disponibilidade

**⚡ Dica rápida**: "Funcional = o que faz, Não funcional = como faz"

**O que lembrar**: Ambos são essenciais para o sistema

---

## 📍 CARACTERÍSTICAS ARQUITETURAIS
**Conceito**: Requisitos funcionais da arquitetura
**Realidade**: Impossível cumprir 100% de todas
**Objetivo**: Buscar o melhor equilíbrio possível

**⚡ Dica rápida**: "Arquitetura = equilíbrio de características"

**O que lembrar**: Foco no que é mais importante para o negócio

---

## 📍 DECISÕES DE ARQUITETURA
**Importância**: Escolher arquitetura = escolher futuro do sistema
**Responsabilidade**: Uma das decisões mais importantes
**Impacto**: Define caminho de evolução

**⚡ Dica rápida**: "Arquitetura = futuro do sistema"

**O que lembrar**: Decisão arquitetural = compromisso de longo prazo

---

## 📍 PRINCÍPIOS DO DESIGN
**Conceito**: Regras para desenvolver sistemas
**Objetivo**: Guiar desenvolvimento de forma consistente
**Aplicação**: Seguir durante todo o ciclo de desenvolvimento

**⚡ Dica rápida**: "Princípios = regras do jogo"

**O que lembrar**: Princípios orientam decisões de design

---

## 📍 PENSAMENTO ARQUITETÔNICO
**Conceito**: Abordagem sistemática para decisões arquiteturais
**Componentes**: Análise de trade-offs, consideração de contexto
**Objetivo**: Decisões conscientes e justificadas

**⚡ Dica rápida**: "Pensamento arquitetônico = decisões conscientes"

**O que lembrar**: Arquitetura requer pensamento estratégico

---

# 📚 Segundo Bimestre

## 📅 29/09/25

### 📍 CIRCUIT BREAKER PATTERN
**Conceito**: Padrão de design que protege a comunicação entre sistemas
- **Objetivo**: Lidar com falhas transitórias e evitar sobrecarga em sistemas distribuídos
- **Referência**: [Circuit Breaker pattern](https://learn.microsoft.com/pt-br/azure/architecture/patterns/circuit-breaker?wt.mc_id=AZ-MVP-5003638)

O Circuit Breaker possui três estados principais:
- **Closed (Fechado)**: Requisições são encaminhadas normalmente. Monitora falhas e muda para aberto se ultrapassar limite configurado.
- **Open (Aberto)**: Requisições são bloqueadas imediatamente, evitando chamadas ao serviço indisponível. Após timeout, muda para meio aberto.
- **Half Open (Meio aberto)**: Permite número limitado de requisições para testar se o serviço já está saudável. Se bem-sucedidas, volta para fechado. Caso contrário, volta para aberto.

**⚡ Dica rápida**: "Circuit Breaker = disjuntor que protege a comunicação entre sistemas"

**O que lembrar**: Três estados (Fechado → Aberto → Meio Aberto) protegem contra falhas em cascata

---

## 📅 06/10/25

### 📍 DEFINIÇÕES DE CARACTERÍSTICAS ARQUITETURAIS
**Conceito**: Conjunto de qualidades e decisões de design que torna um software único e funcional
- **Critérios**: Especifica consideração de design fora do domínio, influencia aspecto estrutural, é essencial para o sucesso

### Características Operacionais da Arquitetura
Envolvem capacidades como desempenho, escalabilidade, elasticidade, disponibilidade e confiabilidade.

| Termo | Definição |
| :--- | :--- |
| **Disponibilidade** | Tempo que o sistema deve ficar ativo. |
| **Continuidade** | Capacidade de recuperação de desastres. |
| **Desempenho** | Velocidade, capacidade e resposta do sistema. |
| **Recuperabilidade** | Rapidez para voltar ao ar após falhas. |
| **Confiabilidade / Segurança** | Tolerância a falhas e importância crítica. |
| **Robustez** | Resistência a erros e falhas externas. |
| **Escalabilidade** | Capacidade de crescer conforme demanda. |

### Características Estruturais da Arquitetura
Englobam qualidade do código, modularidade, acoplamento controlado, código legível e outras avaliações internas.

| Termo | Definição |
| :--- | :--- |
| **Configuração** | Facilidade de mudar ajustes pelo usuário. |
| **Extensão** | Facilidade para adicionar novas funcionalidades. |
| **Instalabilidade** | Facilidade de instalação em diferentes plataformas. |
| **Aproveitamento / Reutilização** | Uso de componentes comuns em vários sistemas. |
| **Localização** | Suporte a múltiplos idiomas e formatos regionais. |
| **Manutenção** | Facilidade de aplicar alterações no sistema |
| **Portabilidade** | Necessidade de um sistema rodar em mais de um tipo de dispositivo ou sistema operacional |
| **Suporte** | Suporte técnico necessário e as facilidades de registro necessárias para diagnosticar erros no sistema. |
| **Atualização** | A facilidade de atualizar uma versão prévia da aplicação ou solução para uma versão mais nova. |

### Características Transversais da Arquitetura
Muitas características desafiam a categorização, formando importantes restrições de design.

| Termo | Definição |
| :--- | :--- |
| **Acessibilidade** | Garante o acesso a todos os usuários, incluindo aqueles com deficiências (ex: daltonismo, perda auditiva). |
| **Armazenamento** | Define se os dados precisarão ser armazenados ou excluídos após um período de tempo. |
| **Autenticação** | Assegura que os usuários são quem afirmam ser (verificação de identidade). |
| **Autorização** | Garantem que os usuários possam acessar apenas certas funções ou áreas da aplicação. |
| **Legalidade** | Restrições legais e regulatórias sob as quais o sistema deve operar. |
| **Privacidade** | Ocultamento de transações de funcionários internos da empresa. |
| **Segurança** | Especifica a necessidade de criptografia de dados. |
| **Usabilidade / Viabilidade** | O nível de treinamento necessário para os usuários atingirem seus objetivos com a aplicação. |

### A Arquitetura menos pior
A Arquitetura de Software é um exercício de trade-offs (compensações). É impossível maximizar todos os atributos de qualidade (ex: Segurança vs. Desempenho) simultaneamente, pois melhorar um quase sempre prejudica outro.

**⚡ Dica rápida**: "Arquitetura = equilíbrio entre características conflitantes"

**O que lembrar**: Objetivo é criar a "arquitetura menos pior", não a melhor

---

### 📍 CQRS (COMMAND QUERY RESPONSIBILITY SEGREGATION)
**Conceito**: Padrão que divide operações de leitura e escrita na persistência
- **Objetivo**: Otimizar performance, escalabilidade e segurança
- **Aplicação**: Modelos separados para ler (read) e escrever (write)

Com o crescimento de uma aplicação, alguns desafios surgem:
- **Data mismatch**: A representação de leitura e escrita pode divergir
- **Lock orientation**: Operações em paralelo podem causar "lock" no mesmo conjunto de dados
- **Problemas de performance**: Abordagem tradicional pode ter efeito negativo no desempenho
- **Desafios de segurança**: Difícil gerenciar quando entidades estão sujeitas a ler e escrever operações

#### Modelos separados em uma única base de dados
Tanto o modelo de leitura quanto o de escrita compartilham o mesmo banco de dados, mas possuem lógicas independentes.

#### Modelo de Escrita
- Processa comandos que atualizam ou persistem dados
- Inclui validação e lógica de domínio para garantir integridade e consistência
- Otimizado para suportar regras de negócio e operações transacionais

#### Modelo de Leitura
- Atende consultas para recuperar dados de forma eficiente
- Gera DTOs (Data Transfer Objects) ou projeções adaptadas para a interface do usuário
- Evita lógica complexa de domínio para maximizar o desempenho das consultas

**⚡ Dica rápida**: "CQRS = separar leitura de escrita para melhor performance"

**O que lembrar**: Usar quando chega no limite da escalabilidade vertical ou há problemas de lock

---

## 📅 13/10/25 - 📅 14/10/25

### 📍 RETRY PATTERN
**Conceito**: Padrão que permite lidar com falhas ao tentar conectar com serviços ou redes
- **Objetivo**: Aumentar a estabilidade da aplicação tentando reconectar de forma suave
- **Contexto**: Aplicações na nuvem devem estar preparadas para falhas transitórias

Falhas transitórias comuns incluem:
- Perda momentânea de conectividade de rede
- Indisponibilidade temporária de um serviço
- Timeouts quando um serviço está sobrecarregado

#### Estratégias de Repetição
- **Cancelar**: Se a falha claramente não for transitória (ex: credenciais inválidas), a operação deve ser cancelada imediatamente
- **Tentar Novamente de Imediato**: Se a falha for rara ou incomum (ex: pacote de rede corrompido), nova tentativa imediata
- **Tentar Novamente Após um Atraso**: Estratégia mais comum. Atraso pode ser:
  - **Incremental**: Aumenta linearmente (ex: 2s, 4s, 6s)
  - **Exponencial (Exponential Backoff)**: Aumenta exponencialmente, eficaz para evitar sobrecarregar serviços ocupados

**⚡ Dica rápida**: "Retry = tentar novamente de forma inteligente"

**O que lembrar**: Usar backoff exponencial para evitar sobrecarga de serviços

---

### 📍 FUNDAMENTOS DOS PADRÕES DE ARQUITETURA
**Conceito**: Estilos de arquitetura descrevem relação nomeada de componentes que cobrem várias características

**A Grande Bola de Lama**  
Confusão de código espaguete mal estruturado, desleixado e unido com fita adesiva e arame. Mostra sinais inequívocos de crescimento desregulado e reparos rápidos e repetidos.

**Arquitetura Unitária**  
Quando o software iniciou, havia apenas o computador e o software que rodava nele. Durante a evolução do hardware e software, os dois iniciaram como uma entidade e se dividiram conforme aumentava a necessidade de capacidades mais sofisticadas.

**Cliente/Servidor**   
Divide a funcionalidade técnica em duas partes lógicas: o front-end (Cliente) e o back-end (Servidor). Base para abordar a complexidade e necessidade de particionamento dos sistemas de software.

**Desktop + Servidor de Banco de Dados**  
Dividia o sistema entre a aplicação Cliente (Desktop), que tratava da interface do usuário e lógica de apresentação, e o Servidor de Banco de Dados, responsável pelo processamento de dados robusto e de alta complexidade.

**Navegador + Servidor Web**  
Com o desenvolvimento web moderno, a divisão comum tornou o navegador web conectado ao servidor web (que por sua vez conectava um servidor de banco de dados). Separação das responsabilidades lembrava a variante de desktop, mas com clientes ainda mais leves.

**⚡ Dica rápida**: "Arquitetura evolui de monolítica para distribuída"

**O que lembrar**: Cada estilo surgiu para resolver limitações do anterior

---

## 📅 20/10/25 - 📅 21/10/25

### 📍 ESTILO DE ARQUITETURA EM CAMADAS (N-TIER)
**Conceito**: Estilo mais comum e tradicional para desenvolvimento de aplicações
- **Popularidade**: Simplicidade, baixo custo, familiaridade entre desenvolvedores
- **Alinhamento**: Com estrutura organizacional das equipes (UI, backend, banco de dados), conforme a Lei de Conway

#### Características
- Componentes são agrupados em camadas lógicas horizontais
- Cada camada tem uma função específica
- Camadas padrão:
  - **Apresentação**: Interface do usuário (UI)
  - **Comercial**: Regras de negócio
  - **Persistência**: Acesso aos dados
  - **Banco de Dados**: Armazenamento dos dados

**Problema**: A aplicação é dividida por função técnica, não por domínio de negócio. Isso dificulta mudanças em funcionalidades específicas (ex: "cliente"), pois elas se espalham por todas as camadas.

#### Camada aberta vs. fechada
- **Camada fechada**: Uma requisição deve passar pela camada imediatamente abaixo, sem pular etapas. Cria isolamento e torna o sistema menos frágil.
- **Camada aberta**: Permite que uma requisição "pule" camadas. Oferece flexibilidade, mas aumenta risco de criar sistema fortemente acoplado.

#### Sinkhole
Descreve situação em que as camadas agem apenas como "atravessadoras", passando a solicitação para a camada seguinte sem realizar processamento significativo.

**⚡ Dica rápida**: "Camadas = separação por função técnica, não por domínio"

**O que lembrar**: Camada fechada = isolamento, Sinkhole = camadas inúteis

---

## 📅 27/10/25

### 📍 ESTILO DE ARQUITETURA PIPELINE
**Conceito**: Arquitetura baseada na divisão de funcionalidade em partes distintas
- **Origem**: Princípio inerente por trás dos shells de terminal Unix (como Bash)
- **Paralelos**: Linguagens funcionais e modelos como MapReduce
- **Uso**: Robusta para aplicações de nível comercial, não apenas baixo nível

#### Topologia e Componentes
Consiste em **Filtros (Filters)** conectados por **Canais (Pipes)** em um fluxo unidirecional e ponto a ponto.

- **Filtros**: Componentes de processamento. Devem ser autônomos, independentes, geralmente sem estado e realizar apenas uma tarefa (responsabilidade única).
- **Canais**: Formam o caminho de comunicação. Tipicamente unidirecionais e ponto a ponto, transportando payloads de dados (preferencialmente menores para otimizar desempenho).

#### Tipos de filtros
1. **Produtor**: Ponto de partida (origem), responsável por criar e emitir dados
2. **Transformador**: Recebe, executa modificação ou enriquecimento dos dados (análogo ao map)
3. **Verificador**: Recebe, testa um ou mais critérios e opcionalmente emite saída, filtrando os dados (semelhante ao reduce ou filter)
4. **Consumidor**: Ponto de término (destino), que persiste o resultado final (ex: em banco de dados) ou o exibe

**⚡ Dica rápida**: "Pipeline = filtros conectados por canais unidirecionais"

**O que lembrar**: Cada filtro faz uma coisa bem feita (responsabilidade única)

---

## 📅 03/11/25

### 📍 ESTILO DE ARQUITETURA MICROKERNEL
**Conceito**: Padrão consolidado para aplicações baseadas em produto e software comercial personalizado
- **Estrutura**: Monolítica simples projetada para facilitar extensão, adaptação e isolamento de funcionalidades
- **Ideal para**: Aplicações empacotadas para instalação no cliente

#### Topologia e Componentes
A arquitetura é composta por dois elementos principais:

- **Sistema Central (Core System)**: Define funcionalidade mínima necessária para o sistema operar. Representa o "caminho feliz" ou fluxo de processamento geral. Responsável por localizar e chamar os plug-ins apropriados. Isola complexidade e lógica de processamento altamente volátil, delegando-as aos plug-ins. Pode ser implementado como monolítico modular ou arquitetura em camadas. Tipicamente gerencia banco de dados compartilhado pela aplicação.

- **Componentes de Plug-in**: Módulos autônomos e independentes que contêm processamento especializado, recursos adicionais e código personalizado. Objetivo principal é isolar código volátil, facilitando manutenção e testabilidade. Idealmente são independentes entre si e gerenciados pelo Sistema Central através de um Registro que mapeia os plug-ins disponíveis e seus detalhes de acesso.

#### Comunicação e Implementação
A comunicação entre o Sistema Central e os plug-ins é geralmente ponto a ponto (chamadas de método ou função), implementada por meio de bibliotecas compartilhadas (JARs, DLLs), namespaces ou pacotes.

Alternativamente, os plug-ins podem ser acessados remotamente via REST ou mensageria, sendo implementados como serviços independentes. Isso melhora desacoplamento e escalabilidade, mas transforma a arquitetura em distribuída (pode complicar implantação em produtos locais de terceiros).

**Contratos**: Os contratos entre os plug-ins e o Sistema Central (definindo comportamento e dados de entrada/saída) são cruciais e geralmente padronizados. Adaptadores são usados para integrar plug-ins de terceiros com contratos personalizados.

**⚡ Dica rápida**: "Microkernel = sistema central + plug-ins independentes"

**O que lembrar**: Sistema Central gerencia, plug-ins fazem o trabalho específico

---

## 📅 10/11/25

### 📍 MICROSSERVIÇOS
**Conceito**: Estilo arquitetural centrado em alto desacoplamento, domínios independentes e unidades pequenas de implementação
- **Origem**: Cada serviço roda em seu próprio processo (VM, container etc.)
- **Influência**: Deriva fortemente dos conceitos do DDD (Domain-Driven Design), especialmente o Contexto Delimitado (Bounded Context)
- **Histórico**: Termo popularizado em 2014 por Martin Fowler e James Lewis

### Contexto Delimitado
Cada serviço representa um domínio ou fluxo de trabalho, contendo todo o necessário para operar:
- Código
- Banco de dados
- Dependências internas

Isso reduz acoplamento e favorece duplicação quando necessário.

### Desacoplamento > Reutilização
1. Reutilizar aumenta acoplamento
2. Microsserviços preferem duplicação para manter autonomia

### Topologia e Distribuição
Cada serviço roda em seu próprio processo (VM, container etc.).  
Isso melhora isolamento e escalabilidade, mas reduz performance devido às chamadas de rede.  
A granularidade correta é fundamental — serviços pequenos demais criam excesso de comunicação.

### Granularidade
A definição dos limites de serviços deve considerar:
- **Finalidade**: Cada serviço faz algo coeso
- **Transações**: Evitar transações distribuídas
- **Coreografia**: Não exigir comunicação exagerada

Granularidade exige iteração: dificilmente fica correta na primeira tentativa.

### Isolamento dos Dados
Cada microsserviço deve ter seu banco dedicado, evitando esquemas compartilhados.

**Consequências:**
1. Não existe mais uma "única fonte de verdade" global
2. Pode exigir replicação, cache ou coordenação entre domínios
3. Permite liberdade para escolher tecnologias diferentes por serviço

### Comunicação
Os serviços podem se comunicar de forma:

#### Síncrona
- REST
- gRPC
Menos tolerante a falhas.

#### Assíncrona
- Eventos
- Mensagens
Maior desacoplamento e resiliência.

O ecossistema é heterogêneo: diferentes serviços podem usar linguagens e tecnologias distintas.

**⚡ Dica rápida**: "Microsserviços = serviços independentes, cada um com seu banco"

**O que lembrar**: Desacoplamento > reutilização, granularidade correta é fundamental

---
  
