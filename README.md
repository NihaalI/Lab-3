# Lab-3
class Character:
    def __init__(self, name, max_health, attack_power):
        self.name = name
        self.max_health = max_health
        self.health = max_health  # Initialize health to max health
        self.attack_power = attack_power
        self.pouch = None  # Initially, the pouch is empty
    
