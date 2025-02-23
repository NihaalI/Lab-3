# Lab-3
class Character:
    def __init__(self, name, max_health, attack_power):
        self.name = name
        self.max_health = max_health
        self.health = max_health  # Initialize health to max health
        self.attack_power = attack_power
        self.pouch = None  # Initially, the pouch is empty
    
 def __repr__(self):
        return f"{self.name}\nHP: {self.health}\nAP: {self.attack_power}\nPouch: {str(self.pouch)}"

    def attack(self, target):
        if not isinstance(target, Character):
            raise ValueError("Target must be a Character instance.")
        target.health -= self.attack_power
        if target.health < 0:
            target.health = 0  # Ensure health doesn't drop below zero

    def add_to_pouch(self, item):
        if isinstance(item, HealingPotion) and item.num_uses > 0:
            self.pouch = item

    def use_item(self, target):
        if self.pouch and isinstance(self.pouch, HealingPotion):
            if self.pouch.num_uses > 0:
                self.pouch.apply_effect(target)
                self.pouch.num_uses -= 1
                if self.pouch.num_uses == 0:
                    self.pouch = None  # Remove the item if it's fully used
                    
