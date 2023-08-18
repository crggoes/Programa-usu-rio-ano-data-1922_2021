# Programa-usu-rio-ano-data-1922_2021
Programa que recebe do usuário nome completo e ano de nascimento que seja entre 1922 e 2021

Desenvolva um programa que recebe do usuário nome completo e ano de nascimento que seja entre 1922 e 2021.
A partir dessas informações, o sistema mostrará o nome do usuário e a idade que completou, ou completará, no ano atual (2022).

Caso o usuário não digite um número ou apareça um inválido no campo do ano, o sistema informará o erro e continuará perguntando até que um valor correto seja preenchido.
############################################################################################################################

import datetime

def calcular_idade(ano_nascimento):
    ano_atual = datetime.datetime.now().year
    idade = ano_atual - ano_nascimento
    return idade

def obter_ano_nascimento():
    while True:
        try:
            ano_nascimento = int(input("Digite o ano de nascimento (entre 1922 e 2021): "))
            if ano_nascimento >= 1922 and ano_nascimento <= 2021:
                return ano_nascimento
            else:
                print("Ano inválido! Digite um ano entre 1922 e 2021.")
        except ValueError:
            print("Entrada inválida! Digite um valor numérico.")

nome_completo = input("Digite o nome completo: ")
ano_nascimento = obter_ano_nascimento()
idade = calcular_idade(ano_nascimento)

print("Nome: ", nome_completo)
print("Idade: ", idade)

