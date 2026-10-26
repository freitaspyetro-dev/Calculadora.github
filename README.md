print("=== CALCULADORA DE PROBABILIDADE ===")

try:
    casos_favoraveis = int(input("Digite o número de casos favoráveis: "))
    casos_possiveis = int(input("Digite o número de casos possíveis: "))

    if casos_possiveis <= 0:
        print("Erro: O número de casos possíveis deve ser maior que zero.")
    elif casos_favoraveis < 0:
        print("Erro: O número de casos favoráveis não pode ser negativo.")
    elif casos_favoraveis > casos_possiveis:
        print("Aviso: Os casos favoráveis não podem ser maiores que os casos possíveis.")
    else:
        probabilidade = (casos_favoraveis / casos_possiveis) * 100
        print(f"A probabilidade é: {probabilidade:.2f}%")

except ValueError:
    print("Erro: Por favor, digite apenas números inteiros válidos.")
