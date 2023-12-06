# Cycle-Time-Measurin
Cycle Time Measurin

import tkinter as tk
from tkinter import ttk

def criar_grafico(tempo_maquina, tempo_operador, titulo):
    plt.bar(['Operador'], [tempo_operador], label='Operador', color='orange')
    plt.bar(['Máquina'], [tempo_maquina], bottom=[tempo_operador], label='Máquina', color='blue')

    plt.xlabel('Componentes')
    plt.ylabel('Tempo (segundos)')
    plt.title(titulo)
    plt.legend()
    plt.show()

def criar_interface_grafica():
    def plotar_grafico():
        tempo_maquina = float(entry_maquina.get())
        tempo_operador = float(entry_operador.get())
        titulo = entry_titulo.get()
        criar_grafico(tempo_maquina, tempo_operador, titulo)

    root = tk.Tk()
    root.title("Interface Gráfica")

    # Labels e Entry para Máquina 1
    ttk.Label(root, text="Tempo da Máquina 1 (segundos):").grid(row=0, column=0)
    entry_maquina = ttk.Entry(root)
    entry_maquina.grid(row=0, column=1)

    # Labels e Entry para Operador 1
    ttk.Label(root, text="Tempo do Operador 1 (segundos):").grid(row=1, column=0)
    entry_operador = ttk.Entry(root)
    entry_operador.grid(row=1, column=1)

    # Labels e Entry para o Título
    ttk.Label(root, text="Título do Gráfico:").grid(row=2, column=0)
    entry_titulo = ttk.Entry(root)
    entry_titulo.grid(row=2, column=1)

    # Botão para plotar o gráfico
    ttk.Button(root, text="Plotar Gráfico", command=plotar_grafico).grid(row=3, column=0, columnspan=2)

    root.mainloop()

# Chamar a função para criar a interface gráfica
criar_interface_grafica()
