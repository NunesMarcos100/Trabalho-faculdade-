#Desenvolva um algoritmo FILA em Python, obedecendo as regras a seguir:
#O programa deve ser iniciado exibindo um menu com 3 opções: Adicionar número, excluir número e sair.
#As adições devem ser feitas sempre na primeira posição, jogando os números já existentes, a direita.
#Os números da estrutura devem ser exibidos após qualquer operação.
#A exclusão deve ser feita no primeiro número adicionado.
#Se for escolhida a opção de exclusão e nenhum número existir, deverá ser exibida uma mensagem.
#As estruturas não devem conter um limite.
#O menu deve ser obrigatoriamente exibido após cada operação da estrutura.

#Python

from collections import deque #Usando a biblioteca collections para utilizar a estrutura de dados deque, que implementa uma fila em Python.

fila = deque()

def menu(): #Exibe o menu com as opções para o usuário e retorna a opção escolhida.#
    print("-------------------")
    print("     Fila em Python   ")
    print("-------------------")
    print("1. Adicionar número")
    print("2. Excluir número")
    print("3. Sair")
    print("-------------------")
    opcao = int(input("Digite a sua opção: "))
    return opcao

def adicionar_numero(): #Adiciona um número à fila, utilizando o método appendleft() para inserir o elemento na primeira posição.
    numero = int(input("Digite o número a ser adicionado: "))
    fila.appendleft(numero)
    print(f"Número {numero} adicionado com sucesso!")

def excluir_numero(): #Exclui um número da fila, utilizando o método popleft() para remover o elemento da primeira posição.
    if len(fila) == 0:
        print("Fila vazia! Nenhum número a ser excluído.")
    else:
        numero_excluido = fila.popleft()
        print(f"Número {numero_excluido} excluído com sucesso!")

def exibir_fila(): #Exibe os elementos da fila, utilizando um loop para iterar sobre a estrutura.
    if len(fila) == 0:
        print("Fila vazia!")
    else:
        print("Elementos da fila:", fila)

while True: #Garante que o programa continue funcionando até que o usuário escolha a opção de sair.
    opcao = menu()
    if opcao == 1:
        adicionar_numero()
    elif opcao == 2:
        excluir_numero()
    elif opcao == 3:
        print("Saindo do programa...")
        break
    else:
        print("Opção inválida! Tente novamente.")
    exibir_fila() #Mostrar os elementos da fila para o usuário.
