"""Класс Zoo, демонстрирующий композицию и управление коллекцией."""

from typing import List, Optional
from src.animal import Animal


class Zoo:
    """
    Класс Zoo, управляющий коллекцией животных.
    """

    def __init__(self, name: str, location: str) -> None:
        self._name = name
        self._location = location
        self._animals: List[Animal] = []

    @property
    def name(self) -> str:
        """Получить название зоопарка."""
        return self._name

    @property
    def location(self) -> str:
        """Получить локацию зоопарка."""
        return self._location

    @property
    def animals(self) -> List[Animal]:
        """Вернуть копию списка животных."""
        return self._animals.copy()

    def add_animal(self, animal: Animal) -> None:
        """Добавить животное в зоопарк."""
        self._animals.append(animal)
        print(f"{animal.name} добавлен(а) в зоопарк.")

    def remove_animal(self, animal: Animal) -> bool:
        """Удалить животное из зоопарка. Возвращает True если удалено."""
        if animal in self._animals:
            self._animals.remove(animal)
            print(f"{animal.name} удалён(а) из зоопарка.")
            return True
        return False

    def get_animal_count(self) -> int:
        """Получить количество животных в зоопарке."""
        return len(self._animals)

    def find_animal_by_name(self, name: str) -> Optional[Animal]:
        """Найти животное по имени."""
        for animal in self._animals:
            if animal.name == name:
                return animal
        return None

    def get_species_count(self, species: str) -> int:
        """Получить количество животных определённого вида."""
        return sum(1 for a in self._animals if a.species == species)

    def get_all_sounds(self) -> List[str]:
        """Получить звуки всех животных."""
        return [animal.make_sound() for animal in self._animals]

    def feed_all(self, food: str = "standard food") -> None:
        """Накормить всех животных."""
        print("\n--- Кормление всех животных ---")
        for animal in self._animals:
            animal.eat(food)

    def exercise_all(self, minutes: int = 30) -> None:
        """Физическая нагрузка для всех животных."""
        print(f"\n--- Физическая нагрузка ({minutes} минут) ---")
        for animal in self._animals:
            animal.exercise(minutes)

    def display_animals(self) -> None:
        """Отобразить информацию обо всех животных."""
        print(f"\n--- Животные в {self._name} ---")
        for animal in self._animals:
            print(animal.get_info())

    def __str__(self) -> str:
        return f"Zoo '{self._name}' в {self._location} ({len(self._animals)} животных)"
