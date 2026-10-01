# Jogo de Jokenpô em Python 🎮

Projeto desenvolvido com o objetivo de praticar e consolidar conceitos fundamentais de lógica de programação em Python, como estruturas de repetição (`while`), condicionais (`if/elif/else`), manipulação de listas e uso da biblioteca nativa `random`.

## 🎯 Sobre o Jogo

Este é o clássico jogo "Pedra, Papel e Tesoura" (Jokenpô), onde o usuário joga contra o computador. O sistema valida as jogadas, sorteia a escolha da máquina, determina o vencedor de cada rodada, contabiliza o resultado e permite que o usuário decida quando deseja encerrar a partida.

## 🚀 Funcionalidades

* **Menu Interativo:** O usuário pode jogar quantas rodadas quiser de forma fluida.
* **Validação de Entrada:** O programa trata entradas incorretas e espaços extras caso o utilizador digite algo inválido.
* **Sorteio Automatizado:** A máquina escolhe aleatoriamente entre pedra, papel e tesoura a cada rodada.
* **Encerramento Controlado:** O utilizador pode escolher sair a qualquer momento da partida.

## 🛠️ Tecnologias Utilizadas
* **Python 3.x** (Conceitos aplicados: Listas, Loops, Condicionais e o módulo `random`).

## 💻 Exemplo de Código em Destaque

Uma amostra da lógica principal implementada para gerorar as jogadas e validar os resultados:

```python
import random

opcoes = ["pedra", "papel", "tesoura"]

while True:
    cpu = random.choice(opcoes)
    jogador = input("\nEscolha pedra, papel ou tesoura (ou digite 'sair'): ").lower().strip()

    if jogador == "sair":
        print("Obrigado por jogar! Até a próxima.")
        break

    if jogador not in opcoes:
        print("Opção inválida! Escolha apenas pedra, papel ou tesoura.")
        continue  

    # Verifica o resultado do jogo
    if jogador == cpu:
        print(f"Empate! Ambos escolheram {cpu}.")
    elif (
        (jogador == "pedra" and cpu == "tesoura") or
        (jogador == "papel" and cpu == "pedra") or
        (jogador == "tesoura" and cpu == "papel")
    ):
        print(f"Você venceu! {jogador} vence {cpu}.")
    else:
        print(f"Você perdeu! {cpu} vence {jogador}.")
        
    break
