# Documentação do Projeto: FaturAki

## 1. Nome do Sistema e Estrutura
* **Nome do Repositório / Pastas:** `FaturAki`
* **Nome Alternativo (Futuro):** "Kotas" (para expansão do ecossistema).

## 2. Breve Descrição
O **FaturAki** é uma aplicação web leve e responsiva (*mobile-first*) desenvolvida para ajudar pequenos prestadores de serviços, freelancers, eletricistas, mecânicos e comerciantes informais em Moçambique a gerar orçamentos e faturas (proforma) de forma rápida e profissional.

A plataforma permite criar documentos em PDF e enviá-los diretamente aos clientes via WhatsApp, sem necessidade de configurações ou sistemas complexos.

## 3. Objetivos do Sistema
* Facilitar e agilizar a criação de orçamentos para profissionais que trabalham muito no terreno.
* Transmitir maior profissionalismo, organização e credibilidade aos negócios informais perante os seus clientes.
* Reduzir o uso de papel, blocos de faturas físicos e anotações desorganizadas.
* Criar uma transição tecnológica (digitalização) suave para os pequenos negócios locais.

## 4. Definição do MVP (Fase Inicial)
O MVP será uma aplicação leve, rápida e que resolve o problema principal em poucos cliques.

O que o MVP irá fazer na fase inicial:
* Capturar os dados essenciais do prestador e do cliente no ecrã principal.
* Inserir os serviços prestados com cálculo automático do valor total na moeda local (Metical - MZN).
* Gerar imediatamente um PDF com visual limpo e profissional.
* Fornecer um botão de partilha que abre automaticamente o WhatsApp com uma mensagem pré-formatada anexando o orçamento.

## 5. Requisitos Funcionais (RF)
* **RF01:** O sistema deve permitir a inserção de dados do emissor (Nome do prestador/negócio, Contacto e NUIT opcional).
* **RF02:** O sistema deve permitir a inserção de dados do recetor (Nome do cliente e Contacto).
* **RF03:** O sistema deve incluir uma secção dinâmica para adicionar, editar ou remover itens/serviços (Descrição, Quantidade, Preço Unitário).
* **RF04:** O sistema deve calcular automaticamente o Subtotal e o Valor Total Final.
* **RF05:** O sistema deve salvar os dados do prestador no navegador (via `localStorage`) ou gerir o estado de forma persistente.
* **RF06:** O sistema deve exportar os dados preenchidos e convertê-los num ficheiro PDF.

## 6. Requisitos Não Funcionais (RNF)
* **RNF01 (Usabilidade):** A interface tem de ser otimizada para telemóveis (*mobile-first*), com botões grandes e leitura clara, já que será o principal dispositivo usado no terreno.
* **RNF02 (Desempenho):** A aplicação deve ser rápida, responsiva e leve.
* **RNF03 (Estética):** O design deve ser construído de forma modular e limpa utilizando *Tailwind CSS*.

## 7. Regras de Negócios
* **RN01:** A moeda padrão e fixa do sistema, nesta fase, é o Metical Moçambicano (MZN).
* **RN02:** No MVP gratuito, todos os documentos PDF gerados devem incluir, obrigatoriamente, uma marca d'água discreta no rodapé (ex: *"Gerado gratuitamente via FaturAki"*).
* **RN03:** Não é exigida autenticação nem verificação de documentos fiscais reais para emissão de orçamentos simples.

## 8. Perguntas Frequentes (Para potenciais utilizadores/clientes)
* **P: Tenho de pagar para criar os meus orçamentos?**
  **R:** Não, a ferramenta é totalmente gratuita nesta versão.
* **P: Tenho de baixar a aplicação na PlayStore ou consome espaço no telemóvel?**
  **R:** Não, basta acederes ao site através do navegador do teu telemóvel (ex: Chrome) e podes começar a usar na hora.
* **P: Se eu fechar o site, perco a informação do meu negócio?**
  **R:** Não, o teu nome e contacto ficam guardados para a próxima vez que abrires a ferramenta.

## 9. Perguntas e Pesquisas (Para o Desenvolvedor - Plano de Estudo)
* **P: Como integrar Python com o ecossistema web escolhido?**
  **R:** Python pode ser usado no backend (com frameworks como FastAPI ou Flask) caso decidamos transitar para uma arquitetura híbrida ou para a criação de rotinas de automação/histórico nas fases seguintes, mantendo o front-end em HTML, Tailwind e JavaScript.
* **P: Como faço o botão de WhatsApp abrir sozinho com o texto e o ficheiro?**
  **R:** Pesquisar a *"WhatsApp URL Scheme"* (`wa.me`) e explorar se a partilha nativa do telemóvel (*Web Share API*) consegue anexar diretamente o PDF.
* **P: Qual a posição da Autoridade Tributária (AT) de Moçambique sobre faturas não certificadas?**
  **R:** É recomendado usar sempre o termo "Orçamento" ou "Fatura Proforma" nestes documentos para evitar atritos legais com facturação fiscal que exige software certificado.

## 10. Considerações Adicionais (Tech Stack & Roadmap)
* **Stack Tecnológica Oficial (`FaturAki`):**
  * **Front-end:** HTML5, Tailwind CSS (via CDN) e JavaScript puro (Vanilla JS) para a interatividade imediata no navegador.
  * **Back-end / Suporte:** Python (para suporte a lógica adicional, rotinas de dados ou API futura, caso necessário).
* **Roadmap de Evolução e Monetização:**
  * **Fase 1 (Meses 1-3):** Lançamento grátis da aplicação web para validação e captação de utilizadores.
  * **Fase 2 (Meses 4-6):** Introdução de contas de utilizador, histórico de faturas e painel web robusto.
  * **Fase 3 (Meses 7+):** Lançamento do plano "Pro" (Subscrição mensal de 150 a 300 MZN) que permite remover a marca d'água, adicionar o logótipo da empresa do prestador e enviar recibos de pagamento automáticos.