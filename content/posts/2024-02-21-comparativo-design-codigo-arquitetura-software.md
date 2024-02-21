+++
title = "Existem diferenças entre design de código e arquitetura de software"
date = 2024-02-21T12:00:00-03:00
draft = false

[taxonomies]
tags=["engernharia-de-software"]

[extra]
toc=true
+++

# Resumindo

- Arquitetura: Visão de mais alto nível. Separação de camadas, pastas da aplicação.
- Design: Visão de mais baixo nível. Como escrever cada classe, quais padrões aplicar.

# Segundo o [ChatGpt](https://chat.openai.com)

## O que é design de código?

O design de código, também conhecido como design de programação ou design de código-fonte, refere-se à prática de escrever código de forma clara, organizada e eficiente. Assim como o design de arquitetura de software se concentra na estrutura e organização de um sistema como um todo, o design de código se concentra na estrutura interna e na implementação detalhada dos componentes individuais de software.

Alguns aspectos importantes do design de código incluem:

1. Clareza e legibilidade: Escrever código que seja fácil de entender para outros desenvolvedores (e para o próprio autor) é essencial. Isso envolve o uso de nomes significativos para variáveis, funções e classes, bem como a formatação consistente e a documentação adequada.

2. Modularidade: Dividir o código em unidades independentes e reutilizáveis, como funções, métodos e classes, facilita a manutenção e a evolução do software.

3. Eficiência: Escrever código que seja eficiente em termos de uso de recursos computacionais, como memória e processamento, é importante para garantir o desempenho adequado do sistema.

4. Robustez: Escrever código que seja robusto e seguro, lidando adequadamente com erros e exceções, garantindo assim a confiabilidade do software.

5. Flexibilidade e extensibilidade: Projetar o código de forma a facilitar futuras alterações e expansões do sistema, permitindo assim que ele se adapte a novos requisitos e cenários de uso.

6. Coerência e consistência: Manter um estilo de codificação consistente em todo o projeto contribui para a legibilidade e manutenibilidade do código.

Em resumo, o design de código é uma parte fundamental do processo de desenvolvimento de software, pois influencia diretamente na qualidade, na manutenibilidade e na evolução do sistema ao longo do tempo. Um bom design de código é essencial para garantir que o software seja fácil de entender, modificar e manter.

## O que é arquitetura de software?

Arquitetura de software refere-se ao design estrutural de um sistema de software, que define a forma como os componentes de software interagem entre si para alcançar os objetivos do sistema. É a disciplina que trata das decisões de alto nível sobre a organização do software, incluindo a escolha de padrões, tecnologias, componentes e interfaces.

A arquitetura de software define a estrutura fundamental do sistema, incluindo:

1. Componentes: Os elementos fundamentais do sistema de software, como módulos, bibliotecas, classes, etc.

2. Relacionamentos: As formas como os componentes se comunicam e interagem entre si.

3. Padrões: Conjuntos de práticas estabelecidas para resolver problemas comuns de design e implementação.

4. Restrições: Limitações impostas pelo ambiente de desenvolvimento, como restrições de desempenho, segurança, etc.

5. Decisões de Design: Escolhas fundamentais sobre como o sistema será estruturado para atender aos requisitos funcionais e não funcionais.

A arquitetura de software é crucial para o sucesso de um projeto de desenvolvimento de software, pois fornece uma estrutura sólida que facilita a compreensão, manutenção, evolução e extensibilidade do sistema ao longo do tempo. Uma arquitetura bem projetada pode contribuir significativamente para a eficiência, escalabilidade, confiabilidade e segurança do software.

# Fazendo uma analogia com uma casa

Quando falamos na construção de uma casa, temos profissionais de arquitetura e profissionais de design. Um arquiteto, ele faz a planta da casa, já um designer de interiores define como os móveis vão estar dispostos dentro da casa, como será a iluminação, que tipo de material deve ser utilizado em cada partezinha da casa.
Existe uma certa semelhança entre arquitetura e design, um arquiteto, por exemplo, pode se especializar em design de interiores.

# Trazendo para TI

Se a gente para e pensa nessas definições, e nesses conceitos para a tecnologia da informação e desenvolvimento de software, a arquitetura de software é uma visão de mais alto nível, ou seja, como vamos organizar as pastas, namespaces, pacotes, etc. do projeto. Para isso temos estudos de [Clean Architecture](https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html), [Arquitetura Hexagonal](<https://en.wikipedia.org/wiki/Hexagonal_architecture_(software)>), Onion Architecture, dentre outras. Pode-se afirmar que a arquitetura de software é uma visão de alto nível de como vamos modelar nosso sistema. Por exemplo: vamos ter uma camada de domínio, que vai se comunicar de alguma forma com uma camada de infraestrutura.

Já quando vamos para um nível mais baixo, quando falamos mais de código, como por exemplo:

- como essa minha classe se relaciona com outra;
- essa classe está muito acoplada?
- essa classe tem muitos atributos?

Nesses casos entramos em outro tipo de estudos como princípios de programação orientada à objetos, [SOLID](https://pt.wikipedia.org/wiki/SOLID), [DRY](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself), [KISS](https://pt.wikipedia.org/wiki/Princ%C3%ADpio_KISS), [DDD](https://en.wikipedia.org/wiki/Domain-driven_design), [Padrões de projeto](https://en.wikipedia.org/wiki/Design_Patterns), etc.
