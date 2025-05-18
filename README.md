from tkinter import *

def converter():
    real = float(entrada.get())  # Pega o valor digitado
    
    # Cotações (atualize esses valores conforme necessário!)
    dolar = real / 5.30
    euro = real / 5.80
    libra = real / 6.90
    bitcoin = real / 250_000  
    
    # Atualiza os resultados
    resultado.config(text=(
        f"US$ {dolar:.2f}\n"
        f"€ {euro:.2f}\n"
        f"£ {libra:.2f}\n"
        f"₿ {bitcoin:.6f}"  # 6 casas decimais para Bitcoin
    ))

# Configuração da Janela
janela = Tk()
janela.title("Super Conversor de Moedas 💱")

# Widgets (elementos da interface)
Label(janela, text="Valor em R$:", font=("Arial", 12)).pack(pady=5)
entrada = Entry(janela, font=("Arial", 12))
entrada.pack(pady=5)

Button(janela, text="Converter", command=converter, bg="#4CAF50", fg="white").pack(pady=10)

resultado = Label(janela, text="", font=("Arial", 12, "bold"), justify=LEFT)
resultado.pack()

janela.mainloop()                   
