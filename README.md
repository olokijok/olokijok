import random

# Tworzenie klas dla YouTuberów
class Youtuber:
    def __init__(self, name, health, attack_power):
        self.name = name
        self.health = health
        self.attack_power = attack_power

    def attack(self, opponent):
        damage = random.randint(1, self.attack_power)
        opponent.health -= damage
        print(f"{self.name} atakuje {opponent.name} i zadaje {damage} obrażeń!")

# Tworzenie obiektów dla YouTuberów
youtuber1 = Youtuber("Youtuber1", 100, 20)
youtuber2 = Youtuber("Youtuber2", 100, 15)

# Rozgrywka
while True:
    # Tura Youtubera 1
    youtuber1.attack(youtuber2)
    print(f"{youtuber2.name} ma teraz {youtuber2.health} punktów życia.")
    if youtuber2.health <= 0:
        print(f"{youtuber2.name} został pokonany! Wygrał {youtuber1.name}!")
        break

    # Tura Youtubera 2
    youtuber2.attack(youtuber1)
    print(f"{youtuber1.name} ma teraz {youtuber1.health} punktów życia.")
    if youtuber1.health <= 0:
        print(f"{youtuber1.name} został pokonany! Wygrał {youtuber2.name}!")
        break
