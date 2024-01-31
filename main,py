import customtkinter as ctk

class ContaBancaria:
    def __init__(self, saldo, cpf):
        self._saldo = saldo
        self._cpf = cpf  

    def depositar(self, valor, cpf_digitado):
        if self._verificar_cpf(cpf_digitado):
            if valor > 0:
                self._saldo += valor
                return f'Depósito de {valor} realizado. Novo saldo: {self._saldo}'
            else:
                return 'Valor de depósito inválido.'
        else:
            return 'CPF inválido. Operação não autorizada.'

    def sacar(self, valor, cpf_digitado):
        if self._verificar_cpf(cpf_digitado):
            if valor > 0 and valor <= self._saldo:
                self._saldo -= valor
                return f'Saque de {valor} realizado! seu Novo saldo: {self._saldo}'
            else:
                return 'Valor de saque inválido.'
        else:
            return 'O conta CPF como  inválido. Operação não autorizada.'

    def _verificar_cpf(self, cpf_digitado):  
        return cpf_digitado == self._cpf

    def _verificar_saldo(self):  
        return f'Saldo atual: {self._saldo}'

 
conta1 = ContaBancaria(1000, "123.456.789-00")

def depositar():
    cpf_digitado = cpf_entry.get()
    valor = float(valor_entry.get())
    resultado = conta1.depositar(valor, cpf_digitado)
    resultado_label.config(text=resultado)

def sacar():
    cpf_digitado = cpf_entry.get()
    valor = float(valor_entry.get())
    resultado = conta1.sacar(valor, cpf_digitado)
    resultado_label.config(text=resultado)

# Create the GUI
app = ctk.CTk()

cpf_label = ctk.CTkLabel(app, text="CPF:")
cpf_label.pack()

cpf_entry = ctk.CTkEntry(app)
cpf_entry.pack()

valor_label = ctk.CTkLabel(app, text="Valor:")
valor_label.pack()

valor_entry = ctk.CTkEntry(app)
valor_entry.pack()

depositar_button = ctk.CTkButton(app, text="Depositar", command=depositar)
depositar_button.pack()

sacar_button = ctk.CTkButton(app, text="Sacar", command=sacar)
sacar_button.pack()

resultado_label = ctk.CTkLabel(app, text="")
resultado_label.pack()

app.mainloop()
