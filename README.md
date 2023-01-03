# Raku DSL::Russian

## In brief

This Raku package facilitates the specification computational workflows using 
natural language commands in Russian.

Using the Domain Specific Languages (DSLs) executable code is generated for different
programming languages: Julia, Python, R, Raku, Wolfram Language.

Translation to other natural languages is also done: Bulgarian, English, Korean, Spanish.

------

## Data query (wrangling) workflows

Translate Russian data wrangling specifications to different natural and programming languages:

```perl6
use DSL::English::DataQueryWorkflows;

my $command = '
загрузить набор данных iris;
возьми элементы от 1 до 120 шаг 3;
сгруппировать по столбцу Species;
показать подсчеты
';
for <Bulgarian English Python::pandas Raku::Reshapers Spanish> -> $t {
   say '=' x 60, "\n", $t, "\n", '-' x 60;
   say ToDataQueryWorkflowCode($command, $t, language => 'Russian', format => 'code');
}
```
```
# ============================================================
# Bulgarian
# ------------------------------------------------------------
# зареди таблицата: "iris"
# вземи елементите от 1 до 120 със стъпка 3
# групирай с колоните: Species
# покажи броя
# ============================================================
# English
# ------------------------------------------------------------
# load the data table: "iris"
# take elements from 1 to 120 with step 3
# group by the columns: Species
# show the count(s)
# ============================================================
# Python::pandas
# ------------------------------------------------------------
# obj = example_dataset('iris')
# obj = obj.iloc[1-1:120:3]
# obj = obj.groupby(["Species"])
# print(obj.size())
# ============================================================
# Raku::Reshapers
# ------------------------------------------------------------
# my $obj = example-dataset('iris') ;
# $obj = $obj[ (1 - 1), (1 + 3 - 1) ... (120 - 1) ] ;
# $obj = group-by($obj, "Species") ;
# say "counts: ", $obj>>.elems
# ============================================================
# Spanish
# ------------------------------------------------------------
# cargar la tabla: "iris"
# tomar los elementos de 1 a 120 con el paso 3
# agrupar con columnas: "Species"
# mostrar recuentos
```

-------

## References

### Articles

[AA1] Anton Antonov,
["Introduction to data wrangling with Raku"](https://rakuforprediction.wordpress.com/2021/12/31/introduction-to-data-wrangling-with-raku), 
(2021),
[RakuForPrediction at WordPress](https://rakuforprediction.wordpress.com).

[Wk1] Wikipedia entry,
[UNIX-philosophy rules](https://en.wikipedia.org/wiki/Unix_philosophy).

### Packages

[AAp1] Anton Antonov,
[DSL::Russian, Raku package](https://github.com/antononcube/Raku-DSL-Russian),
(2022),
[GitHub/antononcube](https://github.com/antononcube).

[AAp2] Anton Antonov,
[DSL::Shared, Raku package](https://github.com/antononcube/Raku-DSL-Shared),
(2018-2022),
[GitHub/antononcube](https://github.com/antononcube).

[AAp3] Anton Antonov,
[Grammar::TokenProcessing, Raku project](https://github.com/antononcube/Raku-Grammar-TokenProcessing)
(2022),
[GitHub/antononcube](https://github.com/antononcube).

[AAp4] Anton Antonov,
[DSL::English::ClassificationWorkflows, Raku package](https://github.com/antononcube/Raku-DSL-General-ClassificationWorkflows),
(2018-2022),
[GitHub/antononcube](https://github.com/antononcube).

[AAp5] Anton Antonov,
[DSL::English::DataQueryWorkflows, Raku package](https://github.com/antononcube/Raku-DSL-English-DataQueryWorkflows),
(2020-2022),
[GitHub/antononcube](https://github.com/antononcube).

[AAp6] Anton Antonov,
[DSL::English::LatentSemanticAnalysisWorkflows, Raku package](https://github.com/antononcube/Raku-DSL-General-LatentSemanticAnalysisWorkflows),
(2018-2022),
[GitHub/antononcube](https://github.com/antononcube).

[AAp7] Anton Antonov,
[DSL::English::QuantileRegressionWorkflows, Raku package](https://github.com/antononcube/Raku-DSL-General-QuantileRegressionWorkflows),
(2018-2022),
[GitHub/antononcube](https://github.com/antononcube).

[AAp8] Anton Antonov,
[DSL::English::QuantileRegressionWorkflows, Raku package](https://github.com/antononcube/Raku-DSL-General-RecommenderWorkflows),
(2018-2022),
[GitHub/antononcube](https://github.com/antononcube).
