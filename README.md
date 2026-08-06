# Realme Analytics Dashboard

Dashboard executivo para análise de vendas e performance de produtos.

## 📁 Estrutura de Arquivos

```
├── index.html          # Dashboard principal
├── realme.jpg          # Logo da marca
├── dados/              # Diretório com dados mensais
│   ├── _ordem.json     # Ordem de exibição dos períodos
│   ├── mai2026.json    # Dados de Maio 2026
│   ├── abr2026.json    # Dados de Abril 2026
│   ├── mar2026.json    # Dados de Março 2026
│   ├── fev2026.json    # Dados de Fevereiro 2026
│   ├── jan2026.json    # Dados de Janeiro 2026
│   ├── dez2025.json    # Dados de Dezembro 2025
│   ├── nov2025.json    # Dados de Novembro 2025
│   └── out2025.json    # Dados de Outubro 2025
```

## 🚀 Como Usar

1. Abra o arquivo `index.html` em um navegador moderno
2. O dashboard carregará automaticamente os dados da pasta `dados/`
3. Use o seletor de período no topo para alternar entre meses

## 📊 Funcionalidades

- **Visão Geral**: KPIs, gráficos de pizza e barras, tabela detalhada
- **Categorias**: Performance por categoria de produto
- **Comparativo**: Evolução mensal e tendências
- **Filtros e Busca**: Filtro por categoria e busca textual
- **Exportação**: Impressão/PDF via botão no menu

## 📝 Adicionando Novo Mês

1. Copie um arquivo existente (ex: `fev2026.json`)
2. Renomeie para o novo mês (ex: `mar2026.json` - no formato `mesano.json`)
3. Edite o conteúdo:
   - `label`: Nome exibido no seletor (ex: "Março 2026")
   - `total`: Soma total de itens vendidos
   - `data`: Array de produtos com `name`, `quantity`, `percentage`
4. Abra `dados/_ordem.json` e adicione a nova chave no início do array `_ordem_exibicao`
5. Recarregue o dashboard

### Formato dos Dados

```json
{
  "label": "Nome do Mês",
  "total": 100,
  "data": [
    {
      "name": "NOME DO PRODUTO",
      "quantity": 10,
      "percentage": 0.1
    }
  ]
}
```

**Nota**: O campo `percentage` deve ser um número decimal (ex: 10% = 0.1). A soma de todas as percentages != 1.

## 🔧 Tecnologias Utilizadas

- HTML5 + CSS3 (Tailwind via CDN)
- JavaScript (ES6+)
- Chart.js (gráficos)
- Lucide Icons

## 📋 Notas Técnicas

- Os dados são carregados dinamicamente via `fetch()`
- A ordem de exibição é controlada por `_ordem.json`
- Categorias são determinadas automaticamente pela função `getCategory()`
- O dashboard é responsivo e funciona em desktop e mobile
