---
name: supermarket-price-checker
description: "Compara preços de produtos em supermercados de uma cidade e identifica a opção mais barata. Use para: encontrar o menor preço de um item específico, comparar ofertas entre diferentes redes de supermercados, economizar em compras de mercado."
---

# Supermarket Price Checker

Esta skill permite que o Manus pesquise e compare preços de produtos em supermercados brasileiros, utilizando agregadores e sites oficiais para encontrar a melhor oferta.

## Fluxo de Trabalho

### 1. Coleta de Informações
- Solicite ao usuário o **nome do produto** (incluindo marca ou peso, se possível) e a **cidade ou endereço** de referência.
- Se o usuário não fornecer a cidade, pergunte antes de iniciar a busca.

### 2. Pesquisa de Preços
Utilize o navegador para consultar as seguintes fontes em ordem de prioridade:

| Fonte | Vantagem | Como Usar |
| :--- | :--- | :--- |
| **iFood Mercado** | Agrega várias lojas locais | Navegue até `ifood.com.br/mercado`, defina o endereço e busque o produto. |
| **Rappi** | Agrega várias lojas locais | Navegue até `rappi.com.br`, defina o endereço e busque o produto. |
| **Google Shopping** | Ampla cobertura | Busque por `[produto] [cidade] supermercado` e filtre por lojas locais. |
| **Sites de Nota Fiscal** | Preços reais e oficiais | Consulte `menorpreco.notaparana.pr.gov.br` (PR) ou similares para outros estados. |

### 3. Extração e Comparação
- Extraia os preços de pelo menos **3 a 5 estabelecimentos** diferentes.
- Certifique-se de comparar itens de **mesma unidade de medida** (ex: preço por kg ou por litro).
- Considere taxas de entrega se o usuário mencionar que deseja delivery.

### 4. Apresentação dos Resultados
Apresente os resultados em uma tabela comparativa:

| Supermercado | Produto | Preço Unitário | Observação |
| :--- | :--- | :--- | :--- |
| Nome da Loja | Nome do Item | R$ X,XX | Ex: Promoção, Frete Grátis |

**Destaque claramente qual é a opção mais barata.**

## Dicas para Melhores Resultados
- **Especificidade**: Se o usuário pedir "leite", pesquise por "leite integral 1L" para garantir comparações justas.
- **Data da Consulta**: Sempre informe que os preços são referentes ao momento da consulta e podem variar.
- **Localização**: Use o endereço exato se fornecido para obter preços de lojas que entregam naquela região específica.

## Referências
- Consulte `/home/ubuntu/skills/supermarket-price-checker/references/search_urls.md` para uma lista completa de URLs e padrões de busca.
