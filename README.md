# Painel Gerencial de E-Commerce - Power BI

## 📌 Visão Geral
Este repositório contém um painel gerencial desenvolvido em Power BI para análise de métricas de vendas de um e-commerce, com integração de dados de compras e clientes para suporte à decisão estratégica.

## 🛠️ Ferramentas Utilizadas
- **Power BI** (versão recomendada: 2023 ou superior)
- **Microsoft Excel** (para tratamento inicial de dados)
- **Power Query** (para ETL)
- **DAX** (para medidas avançadas)

## 📊 Fontes de Dados
O projeto utiliza duas bases principais relacionadas por `cliente_Log`:

### Base de Compras
| Coluna | Tipo | Descrição | Observações |
|--------|------|-----------|-------------|
| idcompra | Texto/Número | Identificador único da compra | Chave primária |
| idcanalvenda | Texto | Canal de venda (Site, App, Marketplace) | Categorizar |
| bandeira | Texto | Bandeira do cartão (Visa, Mastercard, etc) | |
| Data | Data | Data completa da compra | Formato DD/MM/YYYY |
| Preço | Decimal | Valor líquido da compra | 2 casas decimais |
| Preço_com_frete | Decimal | Valor total pago pelo cliente | |
| Nome_Departamento | Texto | Categoria do produto | Hierarquia disponível |
| estado | Texto | UF do destinatário | Sigla de 2 letras |

### Base de Clientes
| Coluna | Tipo | Descrição | Observações |
|--------|------|-----------|-------------|
| cliente_Log | Texto/Número | ID único do cliente | Chave de relacionamento |
| Idade | Inteiro | Idade em anos completos | Validar faixas etárias |
| uf_nascimento | Texto | Estado de nascimento | Comparar com estado de entrega |
| Renda | Decimal | Renda mensal declarada | Segmentar por faixas |

## 🔍 Métricas Principais
O painel calcula e apresenta:

**Indicadores de Vendas:**
- Ticket médio (com/sem frete)
- Vendas por canal
- Variação mensal (MoM)
- Top departamentos
- Distribuição geográfica

**Análise de Clientes:**
- Perfil demográfico
- Renda vs. gasto médio
- Fidelidade (compras recorrentes)
- Mapa calor de origem vs. destino

## ⚙️ Configuração do Ambiente

### Pré-requisitos
1. Power BI Desktop instalado
2. Acesso às pastas com arquivos fonte
3. Permissões para importação de dados

### Instalação
```powershell
# Clone o repositório
git clone https://github.com/seu-repositorio/painel-ecommerce.git

# Os arquivos de dados devem ser colocados na pasta /data
# Estrutura recomendada:
/painel-ecommerce
│   /assets
│   /data
│   │   base_compras.xlsx
│   │   base_clientes.xlsx
│   /docs
│   Ecommerce_Analytics.pbix
```

## 🎯 Como Usar
1. **Atualização de Dados**:
   - Atualize os arquivos Excel na pasta `/data`
   - No Power BI, clique em "Atualizar" no menu Home

2. **Filtros Interativos**:
   - Seletor de período temporal
   - Filtro por estado/região
   - Segmentação por canal de venda
   - Faixas de renda e idade

3. **Visualizações**:
   - Abas separadas para visão macro e micro
   - Tooltips com detalhes sob demanda
   - Modo detalhado ao clicar em gráficos

## 📈 Exemplos de Análises
1. **Performance por Bandeira**:
   - Compare a aceitação por tipo de cartão
   - Analise o ticket médio por operadora

2. **Migração Cliente**:
   - Cruzamento UF nascimento vs. entrega
   - Identifique padrões de migração

3. **Sazonalidade**:
   - Gráfico de linhas com variação mensal
   - Comparativo anual (YOY)

## 📝 Notas de Versão
### v1.0.0 (2023-11-20)
- Versão inicial do painel
- Conexão com arquivos Excel locais
- 10 visualizações principais
- 15 medidas DAX calculadas

## 🤝 Contribuição
1. Faça um fork do projeto
2. Crie sua branch (`git checkout -b feature/nova-analise`)
3. Commit suas mudanças (`git commit -m 'Adiciona análise X'`)
4. Push para a branch (`git push origin feature/nova-analise`)
5. Abra um Pull Request

## ✉️ Contato
Renan Torres - nantorres0@gmail.com

---
![Dashboard Preview](https://github.com/user-attachments/assets/e91a375f-ddfa-4a57-bb36-7501aba81045)
*Visão consolidada de vendas por canal e região*
