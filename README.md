# juego-piedra-papel-tijeras-lagarto-spock
"""
Proyecto basico en pyton para el juego Piedra, Paple, Lagarto, Spock
"""
import random


def jugar():
    usuario = input("Escoge una opción: 'pi' para piedra, 'pa' para papel, 'ti' para tijera, 'la' para lagarto 'sp' para spock.\n").lower()
    computadora = random.choice(['pi', 'pa', 'ti', 'la', 'sp'])
    
    print(f"La computado escogio: {computadora}")

    if usuario == computadora:
        return '¡Empate!'

    if ganó_el_jugador(usuario, computadora):
        return '¡Ganaste!'

    return '¡Perdiste!'


def ganó_el_jugador(jugador, oponente):
    # Retornar True (verdadero) si gana el jugador.
    # Tijera gana a Papel (ti > pa).
    # Papel gana a Piedra (pa > pi).
    # Piedra gana a lagarto (pi > la)
    # Lagarto gana a Spock (la > sp)
    # Spock gana a tijeras (sp > ti)
    # tijeras gana a lagarto (ti > la)
    # Lagarto gana a papel (la > pa)
    # Papel gana a Spock (pa > sp)
    # Spock gana a piedra (sp > pi)
    # Piedra gana a tijeras (pi > ti)
    if ((jugador == 'ti' and oponente == 'pa')
        or (jugador == 'pa' and oponente == 'pi')
        or (jugador == 'pi' and oponente == 'la')
        or (jugador == 'la' and oponente == 'sp')
        or (jugador == 'sp' and oponente == 'ti')
        or (jugador == 'ti' and oponente == 'la')
        or (jugador == 'la' and oponente == 'pa')
        or (jugador == 'pa' and oponente == 'sp')
        or (jugador == 'sp' and oponente == 'pi')
        or (jugador == 'pi' and oponente == 'ti')):
        return True
    else:
        return False


print(jugar())
