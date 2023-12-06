# Cycle-Time-Measurin
Cycle Time Measurin


import matplotlib.pyplot as plt
import numpy as np

# Função para criar um gráfico de colunas empilhadas
def criar_grafico(tempo_maquina, tempo_operador, titulo):
    # Criar o gráfico de colunas empilhadas
    plt.bar(['Operador'], [tempo_operador], label='Operador', color='orange')
    plt.bar(['Máquina'], [tempo_maquina], bottom=[tempo_operador], label='Máquina', color='blue')

    # Configurar rótulos e título
    plt.xlabel('Componentes')
    plt.ylabel('Tempo (segundos)')
    plt.title(titulo)
    plt.legend()

    # Exibir o gráfico
    plt.show()

# Obter os tempos de trabalho da Máquina 1 e Operador 1 a partir do usuário
tempo_maquina1 = float(input("Digite o tempo da Máquina 1 (em segundos): "))
tempo_operador1 = float(input("Digite o tempo do Operador 1 (em segundos): "))

# Criar o primeiro gráfico
criar_grafico(tempo_maquina1, tempo_operador1, 'Tempo de Trabalho da Máquina 1 e Operador 1 ')

# Obter os tempos de trabalho da Máquina 2 e Operador 2 a partir do usuário
tempo_maquina2 = float(input("Digite o tempo da Máquina 2 (em segundos): "))
tempo_operador2 = float(input("Digite o tempo do Operador 2 (em segundos): "))

# Criar o segundo gráfico
criar_grafico(tempo_maquina2, tempo_operador2, 'Tempo de Trabalho da Máquina 2 e Operador 2')



# Configurar rótulos e título para o segundo gráfico
plt.xlabel('Componentes')
plt.ylabel('Tempo (segundos)')
plt.title('Tempo de Trabalho da Máquina 2, Operador 2 ')
plt.legend()

# Exibir o segundo gráfico
plt.show()

