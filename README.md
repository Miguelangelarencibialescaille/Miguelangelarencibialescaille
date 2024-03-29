from abc import ABC, abstractmethod

class Jaula:
    def init(self, jaula, patio):
        self.jaula = jaula
        self.patio = patio

class Animal(ABC):
    def init(self, nombre_cientifico, nombre_comun, periodo_gestacion, procedencia, cantidad, jaula, patio):
        self.nombre_cientifico = nombre_cientifico
        self.nombre_comun = nombre_comun
        self.periodo_gestacion = periodo_gestacion
        self.procedencia = procedencia
        self.cantidad = cantidadVi
        self.jaula = Jaula(jaula, patio)

    def mostrar_info(self):
        print(f"Especie: {self.especie})
        print(f"Nombre común: {self.nombre_comun}")
        print(f"Nombre científico: {self.nombre_cientifico}")
        print(f"Cantidad: {self.cantidad}")
        print(f"Período de gestación: {self.periodo_gestacion}")
        print(f"Región de procedencia: {self.procedencia}")
        print(f"Jaula: {self.jaula.jaula} - Patio: {self.jaula.patio}")

    @abstractmethod    
    def mostrar(self):
        pass

class Reptil(Animal):
    def init(self, nombre_cientifico, nombre_comun, periodo_gestacion, procedencia, cantidad, jaula, patio):
        super().init(nombre_cientifico, nombre_comun, periodo_gestacion, procedencia, cantidad, jaula, patio)

    def mostrar(self):
        print("Es un reptil.")

class Ave(Animal):
    def init(self, nombre_cientifico, nombre_comun, periodo_gestacion, procedencia, cantidad, jaula, patio):
        super().init(nombre_cientifico, nombre_comun, periodo_gestacion, procedencia, cantidad, jaula, patio)

    def mostrar(self):
        print("Es un ave.")

class Mamifero(Animal):
    def init(self, nombre_cientifico, nombre_comun, periodo_gestacion, procedencia, cantidad, jaula, patio):
        super().init(nombre_cientifico, nombre_comun, periodo_gestacion, procedencia, cantidad, jaula, patio)

    def mostrar(self):
        print("Es un mamífero.")

class Pez(Animal):
    def init(self, nombre_cientifico, nombre_comun, periodo_gestacion, procedencia, cantidad, jaula, patio):
        super().init(nombre_cientifico, nombre_comun, periodo_gestacion, procedencia, cantidad, jaula, patio)

    def mostrar(self):
        print("Es un pez.")

class Zoo:
    def init(self):
        self.animales = []

    def agregar_animal(self, animal):
        self.animales.append(animal)

    def listar_animales(self):
        for animal in self.animales:
            animal.mostrar()

def llenar_zoo():
       zoo=Zoo()

    while True:
        opcion = input("¿Desea agregar un animal al zoológico? (s/n): ")
        if opcion.lower() != 's':
            break
        
        datos_animal = ingresar_datos_animal()
        tipo_animal = input("Ingrese el tipo de animal (reptil/ave/mamifero/pez): ")
        
        if tipo_animal.lower() == 'reptil':
            animal = Reptil(*datos_animal)
        elif tipo_animal.lower() == 'ave':
            animal = Ave(*datos_animal)
        elif tipo_animal.lower() == 'mamifero':
            animal = Mamifero(*datos_animal)
        elif tipo_animal.lower() == 'pez':
            animal = Pez(*datos_animal)
        else:
            print("Tipo de animal no válido. Intente de nuevo.")
        zoo.agregar_animal(animal)

    zoo.listar_animales()

if name == "main":
    llenar_zoo()
