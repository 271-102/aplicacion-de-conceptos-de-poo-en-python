# aplicacion-de-conceptos-de-poo-en-python
casandra
# archivo: mascotas.py

# Clase Base
class Mascota:
    def __init__(self, nombre, edad):
        self.nombre = nombre
        self.edad = edad

    def hacer_sonido(self):
        return "Esta mascota hace un sonido."


# Clase Derivada
class Perro(Mascota):
    def __init__(self, nombre, edad, raza):
        super().__init__(nombre, edad)
        self.raza = raza 
        self.__vacunado = False  # Encapsulamiento (atributo privado)

    # Encapsulación: métodos para acceder al atributo privado
    def esta_vacunado(self):
        return self.__vacunado

    def vacunar(self):
        self.__vacunado = True

    # Polimorfismo: sobrescritura del método hacer_sonido
    def hacer_sonido(self):
        return "¡Guau!"


# Otra Clase Derivada
class Gato(Mascota):
    def __init__(self, nombre, edad, color):
        super().__init__(nombre, edad)
        self.color = color

    # Polimorfismo: sobrescritura del método hacer_sonido
    def hacer_sonido(self):
        return "¡Miau!"


# Función que demuestra polimorfismo con diferentes tipos de mascotas
def hacer_hablar_mascotas(mascotas):
    for mascota in mascotas:
        print(f"{mascota.nombre} dice: {mascota.hacer_sonido()}")


# Código principal
if __name__ == "__main__":
    perro1 = Perro("Manchas", 4, "Bulldog")
    gato1 = Gato("Bella", 3, "Gris")

    print("Vacunación antes:", perro1.esta_vacunado())
    perro1.vacunar()
    print("Vacunación después:", perro1.esta_vacunado())

    print("\n--- Mascotas Hablando ---")
    lista_mascotas = [perro1, gato1]
    hacer_hablar_mascotas(lista_mascotas)
