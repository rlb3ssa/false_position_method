# Visão geral
Este projeto implementa o método de false position (regula falsi) para encontrar uma raiz real de uma função contínua em um intervalo [a, b] onde ocorre mudança de sinal e com uma tolerância de erro absoluto especificada. O método atualiza o intervalo usando interpolação linear pelos pontos (a,f(a))(a,f(a)) e (b,f(b))(b,f(b)), calculando a aproximação c=a f(b)−b f(a)f(b)−f(a)c=f(b)−f(a)af(b)−bf(a) e mantendo a raiz sempre enclausurada pelo teste de sinal.

# Pré‑requisitos
Python 3.8+ instalado.

Ambiente virtual recomendado para isolar dependências.

NumPy instalado no ambiente do projeto.

## Configuração do ambiente
```bash
python -m venv .venv
```
### macOS/Linux
```bash
source .venv/bin/activate 
```
### Windows (PowerShell)
```bash
.venv\Scripts\Activate.ps1
```
```bash
pip install numpy
```

# Exemplos de Uso

# Exemplo 1: raiz de f(x) = x**3 - 20*x**2 no intervalo [18, 21]
def f(x):
    return x**3-20*x**2
print(false_position_a(f,18,21,1.0e-5))

# Exemplo 2: analisando a condição de parada em um intervalo maior [10, 40]
def f(x):
    return x**3-20*x**2
print(false_position_a(f,10,40,1.0e-5))

# Exemplo 3: f(x) = x**3 + 4*x**2 - 10 em [1, 2]
def f(x):
    return x**3 + 4*x**2 - 10
print(false_position_a(f, 1.0, 2.0, 1.0e-5))

# Exemplo 4: f(x) = np.sin(x) em [3, 4] (raiz próxima de pi)
import numpy as np
def f(x):
    return np.sin(x)
print(false_position_a(f, 3.0, 4.0, 1.0e-6))

# Exemplo 5: f(x) = x - 2**(-x) em [0, 1]
def f(x):
    return x - 2**(-x)
print(false_position_a(f, 0.0, 1.0, 1.0e-6))

# Exemplo 6 (intervalo inválido ou sem mudança de sinal)
# Deve retornar mensagem de erro conforme as validações
def f(x):
    return -x**2
print(false_position_a(f, 1.0, 2.0, 1.0e-4))

# Exemplo 7 (tolerância inválida)
# Deve retornar mensagem informando que o procedimento não se aplica
def f(x):
    return x**2 - x
print(false_position_a(f, 0.0, 1.0, 0))

