# Desafio - Semelhante a um banco imobiliário

## [Desafio](DESAFIO.md)

## Instalação
### 1º Instale o gerenciador de dependências
> comando
```shell
❯ make pkg_install_poetry
```
> resultado
```shell
curl -sSL https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py | python -
Retrieving Poetry metadata

# Welcome to Poetry!

This will download and install the latest version of Poetry,
a dependency and package manager for Python.

It will add the `poetry` command to Poetry's bin directory, located at:

$HOME/.poetry/bin

This path will then be added to your `PATH` environment variable by
modifying the profile file located at:

$HOME/.profile

You can uninstall at any time by executing this script with the --uninstall option,
and these changes will be reverted.

Installing version: 1.1.4
  - Downloading poetry-1.1.4-linux.tar.gz (57.03MB)

Poetry (1.1.4) is installed now. Great!

To get started you need Poetry's bin directory ($HOME/.poetry/bin) in your `PATH`
environment variable. Next time you log in this will be done
automatically.

To configure your current shell run `source $HOME/.poetry/env`
```

### 2º Instação do ambiente - Dev
> comando
```shell
❯ make pkg_install_dev
```
> resultado
```shell
poetry install
Installing dependencies from lock file

No dependencies to install or update

Installing the current project: banco-imobiliario
poetry shell
```

### 3º Rodar o projeto
> comando
```shell
❯ make run
```
> resultado
```shell
make[1]: Entering directory '/home/mabm2/Documents/banco-imobiliario'
make -C src run_main
make[2]: Entering directory '/home/mabm2/Documents/banco-imobiliario/src'
python -m main
#################################################
Quantas partidas terminam por tempo esgotado(timeout): 
        Número de timeouts: 32
        
Quantos turnos em média demora uma partida:
        As partidas demoram em média: 129.1
        
Qual o comportamento que mais venceu:
        O perfil IMPULSIVE Venceu: 111
        
Qual a porcentagem de vitórias por comportamento dos jogadores
  *   IMPULSIVE: 37%
  *   DEMANDING: 28%
  *   CAUTIOUS: 25%
  *   RANDOMER: 10%
#################################################
make[2]: Leaving directory '/home/mabm2/Documents/banco-imobiliario/src'
make[1]: Leaving directory '/home/mabm2/Documents/banco-imobiliario'
```
### 4º Rodar os testes
> comando
```shell
❯ make run_test
```
> resultado
```shell
make[1]: Entering directory '/home/mabm2/Documents/banco-imobiliario'
make -C src run_main_test
make[2]: Entering directory '/home/mabm2/Documents/banco-imobiliario/src'
flake8 banco_imobiliario/*.*
isort **/*.py
pytest --cov-append --cov=banco_imobiliario tests/
================================================================= test session starts =================================================================
platform linux -- Python 3.8.10, pytest-5.4.3, py-1.10.0, pluggy-0.13.1
rootdir: /home/mabm2/Documents/banco-imobiliario, inifile: setup.cfg
plugins: cov-2.11.1
collected 11 items                                                                                                                                    

tests/test_board.py .....                                                                                                                       [ 45%]
tests/test_player.py ......                                                                                                                     [100%]

---------- coverage: platform linux, python 3.8.10-final-0 -----------
Name                                          Stmts   Miss  Cover
-----------------------------------------------------------------
banco_imobiliario/__init__.py                     1      0   100%
banco_imobiliario/board/__init__.py               0      0   100%
banco_imobiliario/board/base.py                  28      8    71%
banco_imobiliario/board/card_patrimony.py        11      2    82%
banco_imobiliario/board/factory.py               18      3    83%
banco_imobiliario/board/game_board.py            77     24    69%
banco_imobiliario/board/game_statistics.py       16     16     0%
banco_imobiliario/board/player_cautious.py        7      1    86%
banco_imobiliario/board/player_demanding.py       7      0   100%
banco_imobiliario/board/player_impulsive.py       5      0   100%
banco_imobiliario/board/player_random.py          8      1    88%
banco_imobiliario/config.py                       4      0   100%
-----------------------------------------------------------------
TOTAL                                           182     55    70%


================================================================= 11 passed in 0.08s ==================================================================
make[2]: Leaving directory '/home/mabm2/Documents/banco-imobiliario/src'
make[1]: Leaving directory '/home/mabm2/Documents/banco-imobiliario'

```

## Extra
> comando
```shell
❯ make run_test_to_html
```
> resultado
```shell
make[1]: Entering directory '/home/mabm2/Documents/banco-imobiliario'
make -C src run_main_test
make[2]: Entering directory '/home/mabm2/Documents/banco-imobiliario/src'
flake8 banco_imobiliario/*.*
isort **/*.py
pytest --cov-append --cov=banco_imobiliario tests/
=========================================================================================== test session starts ===========================================================================================
platform linux -- Python 3.8.10, pytest-5.4.3, py-1.10.0, pluggy-0.13.1
rootdir: /home/mabm2/Documents/banco-imobiliario, inifile: setup.cfg
plugins: cov-2.11.1
collected 11 items                                                                                                                                                                                        

tests/test_board.py .....                                                                                                                                                                           [ 45%]
tests/test_player.py ......                                                                                                                                                                         [100%]

---------- coverage: platform linux, python 3.8.10-final-0 -----------
Name                                          Stmts   Miss  Cover
-----------------------------------------------------------------
banco_imobiliario/__init__.py                     1      0   100%
banco_imobiliario/board/__init__.py               0      0   100%
banco_imobiliario/board/base.py                  28      8    71%
banco_imobiliario/board/card_patrimony.py        11      2    82%
banco_imobiliario/board/factory.py               18      3    83%
banco_imobiliario/board/game_board.py            77     24    69%
banco_imobiliario/board/game_statistics.py       16     16     0%
banco_imobiliario/board/player_cautious.py        7      1    86%
banco_imobiliario/board/player_demanding.py       7      0   100%
banco_imobiliario/board/player_impulsive.py       5      0   100%
banco_imobiliario/board/player_random.py          8      1    88%
banco_imobiliario/config.py                       4      0   100%
-----------------------------------------------------------------
TOTAL                                           182     55    70%


=========================================================================================== 11 passed in 0.07s ============================================================================================
make[2]: Leaving directory '/home/mabm2/Documents/banco-imobiliario/src'
make -C src run_main_test_to_html
make[2]: Entering directory '/home/mabm2/Documents/banco-imobiliario/src'
rm -rf htmlcov
pytest --cov-report html --cov=banco_imobiliario tests/
=========================================================================================== test session starts ===========================================================================================
platform linux -- Python 3.8.10, pytest-5.4.3, py-1.10.0, pluggy-0.13.1
rootdir: /home/mabm2/Documents/banco-imobiliario, inifile: setup.cfg
plugins: cov-2.11.1
collected 11 items                                                                                                                                                                                        

tests/test_board.py .....                                                                                                                                                                           [ 45%]
tests/test_player.py ......                                                                                                                                                                         [100%]

---------- coverage: platform linux, python 3.8.10-final-0 -----------
Coverage HTML written to dir htmlcov


=========================================================================================== 11 passed in 0.09s ============================================================================================
make[2]: Leaving directory '/home/mabm2/Documents/banco-imobiliario/src'
make[1]: Leaving directory '/home/mabm2/Documents/banco-imobiliario'

# banco-imobiliario
