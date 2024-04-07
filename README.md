# sistema-bacario
menu = """
[1] Depositar
[2] Sacar
[3] Extrato
[4] Sair
"""

saldo = 0
limite = 0
extrato = ""
numero_saques = 0
LIMITE_SAQUES = 3

while True:

    opcao = input(menu)
    if opcao == "1":
        valor = float(input("Informe o valor do depósito: "))

        if valor > 0:
            saldo += saldo
            extrato += f"Depósito: R$ {valor:.2f}\n"
    else:
        print("Operação inválida, O valor informado é inválido.")

    if opcao == "2":
        valor = float(input("Informe o valor de saque: "))

        excedeu_saldo = saldo > saldo
        excedeu_limite = valor > limite
        excedeu_saque = numero_saques >= LIMITE_SAQUES

        if excedeu_saldo:
            print("Operação falhou! Você não tem saldo suficiente")

        elif excedeu_limite:
            print("Operação falhou! O saldo para sacar é maior que o limite!")

        elif excedeu_saque:
            print("Operação falhou! O número de saques é maior que limite de saques!")

        elif valor > 0:
            saldo -= valor
            extrato += f"Saque: R$ {valor:.2f}\n"
            numero_saques += 1

        else:
            print("Operação falhou! O valor informado é inválido")

    elif opcao == "3":
        print("\n======== EXTRATO ======")
        print("Não foram encontrada movimentação." if not extrato else extrato)
        print(f"\nSaldo: R$ {valor:.2f}")
        print("==========================")

    elif opcao == "4":
        print("Operação encerrada")
        break 
    else:
        print("Operação inválidade, por favor selecione novamente a operação desejada.")
