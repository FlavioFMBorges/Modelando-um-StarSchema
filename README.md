# Modelando um StarSchema com Power BI
 Modelando um StarSchema com Power BI Utilizando Fórmulas DAX

![StarSchema Flavio Borges](https://github.com/FlavioFMBorges/Modelando-um-StarSchema/blob/main/StarSchema_FB.png)

Passo a Passo

Foi importado o arquivo Financial Sample.xlsx que contém a tabela financials que foi usada para a construção das tabelas dimensão e tabela fato que para diferenciação foram usadas as letras D e F no seu nome.
A tabela financials também teve seu nome modificado para financials - original para que fossem duplicados outras tabelas a partir dela e não houvesse confusão no uso das tabelas.

- Tabelas criadas -  | 
D_Produtos | 
D_Descontos | 
F_Vendas | 
D_Produtos_Detalhes | 
D_Detalhes

- Colunas da tabela financials-original -  | 
Segment | 
Country | 
Product | 
Discount | 
Band | 
Units Sold | 
Manufacturing Price | 
Sale Price | 
Gross Sales | 
Discounts | 
Sales | 
COGS | 
Profit | 
Date | 
Month Number | 
Month Name | 
Year

Depois de duplicada a tabela original, foram agrupadas as colunas e realizadas uma operação por nova coluna expressando nos seus nomes o significado das operações e, logo após, foram criados os ids dos produtos através da coluna condicional e excluído as colunas que não iriam ser usadas.

Na coluna Detalhes de produto foi deletado as colunas que não eram necessárias e com a coluna produto foi mesclado com a tabela D_

Em F_Vendas foram excluídas as colunas "Manufacturing Price", "COGS", "Month Number" por não serem necessárias a esta tabela, acrescentando uma coluna de id_produto e uma sk_id (Surrogate Key)
