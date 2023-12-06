import matplotlib.pyplot as plt
import numpy as np
import tkinter as tk
from tkinter import ttk

def criar_grafico(tempo_maquina1, tempo_operador1, tempo_maquina2, tempo_operador2, titulo):
    fig, ax = plt.subplots()

    ax.bar(['Operador 1'], [tempo_operador1], label='Operador 1', color='orange')
    ax.bar(['Máquina 1'], [tempo_maquina1], bottom=[tempo_operador1], label='Máquina 1', color='blue')
    ax.bar(['Operador 2'], [tempo_operador2], label='Operador 2', color='green')
    ax.bar(['Máquina 2'], [tempo_maquina2], bottom=[tempo_operador2], label='Máquina 2', color='red')

    ax.set_xlabel('Componentes')
    ax.set_ylabel('Tempo (segundos)')
    ax.set_title(titulo)
    ax.legend()
    plt.show()

def criar_interface_grafica():
    def plotar_grafico():
        tempo_maquina1 = float(entry_maquina1.get())
        tempo_operador1 = float(entry_operador1.get())
        tempo_maquina2 = float(entry_maquina2.get())
        tempo_operador2 = float(entry_operador2.get())
        titulo = entry_titulo.get()
        criar_grafico(tempo_maquina1, tempo_operador1, tempo_maquina2, tempo_operador2, titulo)

    root = tk.Tk()
    root.title("Interface Gráfica")

    # Máquina 1
    ttk.Label(root, text="Tempo da Máquina 1 (segundos):").grid(row=0, column=0)
    entry_maquina1 = ttk.Entry(root)
    entry_maquina1.grid(row=0, column=1)

    # Operador 1
    ttk.Label(root, text="Tempo do Operador 1 (segundos):").grid(row=1, column=0)
    entry_operador1 = ttk.Entry(root)
    entry_operador1.grid(row=1, column=1)

    # Máquina 2
    ttk.Label(root, text="Tempo da Máquina 2 (segundos):").grid(row=2, column=0)
    entry_maquina2 = ttk.Entry(root)
    entry_maquina2.grid(row=2, column=1)

    # Operador 2
    ttk.Label(root, text="Tempo do Operador 2 (segundos):").grid(row=3, column=0)
    entry_operador2 = ttk.Entry(root)
    entry_operador2.grid(row=3, column=1)

    # Título
    ttk.Label(root, text="Título do Gráfico:").grid(row=4, column=0)
    entry_titulo = ttk.Entry(root)
    entry_titulo.grid(row=4, column=1)

    # Botão para plotar o gráfico
    ttk.Button(root, text="Plotar Gráfico", command=plotar_grafico).grid(row=5, column=0, columnspan=2)

    root.mainloop()

# Chamar a função para criar a interface gráfica
criar_interface_grafica()
