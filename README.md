
class GameCharacter:
    def __init__(self, name, health, attack_power):
        self.name = name
        self.health = health
        self.attack_power = attack_power

    def attack(self, target):
        damage = self.attack_power
        target.take_damage(damage)
        print(f"{self.name} attacks {target.name} and deals {damage} damage!")

    def take_damage(self, damage):
        self.health -= damage
        if self.health <= 0:
            print(f"{self.name} has been defeated!")

# Example usage:
player = GameCharacter(name="Hero", health=100, attack_power=20)
enemy = GameCharacter(name="Monster", health=50, attack_power=15)

print(f"{player.name}'s health: {player.health}")
print(f"{enemy.name}'s health: {enemy.health}")

player.attack(enemy)

print(f"{player.name}'s health: {player.health}")
print(f"{enemy.name}'s health: {enemy.health}")
