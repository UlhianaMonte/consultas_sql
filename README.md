# consultas_sql
Repositório com consultas SQL básicas e intermediárias, focadas em análise de dados corporativos.
## Buscar tudo
SELECT *
FROM nome_da_tabela;

## Buscar colunas específicas
SELECT id, nome, data_criacao
FROM nome_da_tabela;

## Filtro simples
SELECT *
FROM nome_da_tabela
WHERE status = 'Ativo';

## Filtro com número
SELECT *
FROM nome_da_tabela
WHERE valor > 100;

## Filtro por data
SELECT *
FROM nome_da_tabela
WHERE data_criacao >= '2025-01-01';

## Operadores mais usados
=   -- igual
<>  -- diferente
>   -- maior
<   -- menor
>=  -- maior ou igual
<=  -- menor ou igual

## Exemplo:
SELECT *
FROM pedidos
WHERE quantidade <> 0;

## Filtros combinados (AND / OR)
AND (todas as condições)
SELECT *
FROM pedidos
WHERE status = 'Finalizado'
  AND valor > 500;

## OR (uma condição ou outra)
SELECT *
FROM pedidos
WHERE status = 'Pendente'
   OR status = 'Em análise';

## LIKE (muito usado para texto)
Contém
SELECT *
FROM clientes
WHERE nome LIKE '%Maria%';

## Começa com
SELECT *
FROM clientes
WHERE nome LIKE 'João%';

## Termina com
SELECT *
FROM clientes
WHERE nome LIKE '%Silva';

## IN (lista de valores)
SELECT *
FROM pedidos
WHERE status IN ('Pendente', 'Cancelado', 'Em análise');

## BETWEEN (intervalos)
Datas
SELECT *
FROM pedidos
WHERE data_pedido BETWEEN '2025-01-01' AND '2025-01-31';

## Valores
SELECT *
FROM pedidos
WHERE valor BETWEEN 100 AND 500;

## Ordenar resultados (ORDER BY)
Crescente
SELECT *
FROM pedidos
ORDER BY data_pedido ASC;

## Decrescente
SELECT *
FROM pedidos
ORDER BY valor DESC;

## Limitar quantidade de linhas
SQL Server
SELECT TOP 10 *
FROM pedidos;

## MySQL / PostgreSQL
SELECT *
FROM pedidos
LIMIT 10;

## Contar registros (MUITO USADO EM BI)
SELECT COUNT(*) AS total_registros
FROM pedidos;

## Com filtro:
SELECT COUNT(*) AS total_finalizados
FROM pedidos
WHERE status = 'Finalizado';

## Agrupar dados (GROUP BY)
Contar por status
SELECT status, COUNT(*) AS total
FROM pedidos
GROUP BY status;

## Soma por mês (exemplo)
SELECT mes, SUM(valor) AS total_valor
FROM vendas
GROUP BY mes;

## HAVING (filtro após o GROUP BY)
SELECT status, COUNT(*) AS total
FROM pedidos
GROUP BY status
HAVING COUNT(*) > 10;


