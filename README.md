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
D_Detalhes | 

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
Year | 

Depois de duplicada a tabela original, foram agrupadas as colunas e realizadas uma operação por nova coluna expressando nos seus nomes o significado das operações e, logo após, foram criados os ids dos produtos através da coluna condicional ou índices e excluído as colunas que não iriam ser usadas.

![Tabelas Agrupadas](https://github.com/FlavioFMBorges/Modelando-um-StarSchema/blob/main/agrupamento.png)

Na tabela F_Vendas foram excluídas as colunas "Manufacturing Price", "COGS", "Month Number" por não serem necessárias a esta tabela, acrescentando uma coluna de id_produto e uma sk_id (Surrogate Key).
No editor de modelos do Power Bi foram excluídas as dependencias automáticas e criado as que gerariam o modelo estrela.

Faltou falar do calendário com DAX


- Foi calculada a porcentagem de lucro de USA em relação ao lucro total

1 - Profit (que já temos)
  
2 - Lucro de USA usando função DAX CALCULATE que permite filtrar os dados com uma condição, e neste caso é filtrar o lucro do país "United States of America"  
![Lucro de USA](https://github.com/FlavioFMBorges/Modelando-um-StarSchema/blob/main/lucro_USA.png)

3 - Para descobrir a porcentagem foi usada a função DIVIDE, em que dividimos o lucro de USA pelo lucro Total  
![Porcentagem USA](https://github.com/FlavioFMBorges/Modelando-um-StarSchema/blob/main/porcentagem_lucro_USA.png)

4 - Tranformamos a medida criada em porcentagem  
![Medida em Porcentagem](https://github.com/FlavioFMBorges/Modelando-um-StarSchema/blob/main/medida%20em%20porcentagem.png)

