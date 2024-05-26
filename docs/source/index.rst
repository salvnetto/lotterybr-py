lotterybr
==========

The goal of the package is to provide a function to automatically import data from the lotteries of Caixa Economica Federal into the Python environment. Data from the lotteries of Caixa Economica Federal includes information on various games such as Mega-Sena, Lotofacil, Quina, among others. They are downloaded from the official website of the Federal Savings Bank at <https://loterias.caixa.gov.br/>.

Installation
============

You can install the development version of lotterybr like so:

.. code-block:: shell

   pip install lotterybr

Example
=======

Downloading Lotofacil winners data:

.. code-block:: python

   from lotterybr import get_data

   lotofacil = get_data(game="lotofacil", type="winners")

get_data
========

The function can be used in the following way:

.. code-block:: python

   quina_ganhadores = get_data("quina", "winners")
   lotofacil_dezenas = get_data("lotofacil", "numbers")

Format
======

Each game has two datasets, numbers and winners, with the following columns:

**numbers**

- **date**: Date type, the date that the game occurred.
- **course**: Integer type, which course the game took place.
- **accumulated**: Char type, if the game prize is accumulated "yes" or not "no".
- **numbers**: Factor type with 60 levels, the drawn numbers.

**winners**

- **date**: Date type, the date that the game occurred.
- **course**: Integer type, which course the game took place.
- **accumulated**: Char type, if the game prize is accumulated "yes" or not "no".
- **match**: Char type, the possible match.
- **winners**: Integer type, the number of winners of each possible match.
- **prize**: Integer type, the prize for each type.

Some games, like "duplasena" or "diadesorte", may contain additional columns since each game has a different way of drawing numbers. Therefore, a brief explanation of each game is as follows:

Game Descriptions
=================

**maismilionaria**

Maismilionaria involves selecting five numbers from one pool and one additional number from another pool, with the potential to win multimillion-dollar jackpots.

**megasena**

Six numbers are drawn from a pool of 60, with players aiming to match as many as possible for substantial prizes.

**lotofacil**

Lotofacil involves picking 15 numbers from a pool of 25, with prizes awarded for varying levels of matches.

**quina**

Players select five numbers from a pool of 80, aiming to match as many as possible for prizes.

**lotomania**

Lotomania involves selecting 50 numbers from a pool of 100, with prizes awarded for matching a certain number of drawn numbers.

**duplasena**

Dupla-Sena involves two separate draws, each with six numbers drawn from a pool of 50, offering double the chances to win.

**diadesorte**

In Dia de Sorte, players choose seven numbers and a month, with prizes awarded for matching numbers and/or the month drawn.
