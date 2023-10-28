import json

#Создание родительского класса
class Product:

    def __init__(self, id, name_maker, model):
        self._id = id
        self._name_maker = name_maker
        self._model = model

    def getInf(self):
        print("Id: ", self._id, "Name_maker:", self._name_maker, "Model:", self._model)


#Созданеи дочернего класса Laptop
class Laptop(Product):
    def __init__(self, id, name_maker, model, cpu, batteryMAH):

        self.cpu = cpu
        self.batteryMAH = batteryMAH

        if not isinstance(cpu, str):
            try:
                self.cpu = str(cpu)
            except ValueError:
                raise MyException(f"CPU must be a string, but got {type(cpu).__name__}")

        if not isinstance(batteryMAH, int):
            try:
                self.batteryMAH = int(batteryMAH)
            except ValueError:
                raise MyException(f"batteryMAH must be an int, but got {type(batteryMAH).__name__}")

        super(Laptop, self).__init__(id, name_maker, model)  # Вызываем конструктор родительского класса

    def getInf(self):
        super().getInf()
        print("CPU: ", self.cpu, " batteryMAH: ", self.batteryMAH)



#Создание класса под телики
class TV(Product):

    def __init__(self, id, name_maker, model, type_m, diagonal):
        self.diagonal = diagonal
        self.type_m = type_m
        Product.__init__(self, id, name_maker, model)  # Вызываем конструктор родительского класса



#Моё исключенеи
class MyException(Exception):
    def __init__(self, message="Invalid input"):
        self.message = message
        super().__init__(self.message)


# Функция чтения JSON файла
def readJSON(filename):
    with open(filename, 'r') as file:
        return json.load(file)


# Функция записи JSON файла
def WriteJSON(data, filename):
    data = json.dumps(data)
    data = json.loads(str(data))
    with open(filename, 'w') as file:
        json.dump(data, file, indent=4)

def CreateLaptop():
    print("ID ")
    id = input()

    print("Name maker ")
    name_maker = input()

    print("model ")
    model = input()

    print("CPU ")
    cpu = input()

    print("batteryMAH ")
    batteryMAH = input()

    laptop = Laptop(int(id), name_maker, model, cpu, batteryMAH)
    return laptop

def CreateTV():
    print("ID ")
    id = input()

    print("Name maker ")
    name_maker = input()

    print("model ")
    model = input()

    print("Diagonal ")
    diagonal = input()

    print("type matrix ")
    type_m = input()

    tv = TV(int(id), name_maker, model, type_m, int(diagonal))
    return tv

#Проверка чтения из файла
new_data_base = readJSON('laptops.json')
print(new_data_base)
num1 = Laptop(new_data_base['Product'][0]['_id'], new_data_base['Product'][0]['_name_maker'], new_data_base['Product'][0]['_model'], new_data_base['Product'][0]['cpu'], new_data_base['Product'][0]['batteryMAH'])
num1.getInf()


#Создание объектво
laptop1 = Laptop(1, "Lenovo", "ThinkBook 15", "i5-13400", 100000)
laptop2 = Laptop(2, "MSI", "Gaming", "i7 - 13800", 200000)
tv1 = TV(3, "Sony", "M-123", "IPS", 27)

tovari = [laptop1, laptop2, tv1]

bd = {
    "Product": []  # в массив добавляем обьекты
}

laptops = [laptop1, laptop2]
tvs = [tv1]

print("Хотите ли вы создать обьект? (Y/N)")
answer_user = input()
if (answer_user == "y"):
    print("Хотите ли вы создать обьект Laptop или TV? (laptop/tv)")
    answer_user = input()

    if (answer_user == "laptop"):
        object = CreateLaptop()
        bd['Product'].append(object.__dict__)
        #object.getInf()

    if (answer_user == "tv"):
        object = CreateTV()
        bd['Product'].append(object.__dict__)
        #object.getInf()



for i in range(len(tovari)):
    bd['Product'].append(tovari[i].__dict__)
WriteJSON(bd, 'DateBase.json')
test = TV(0, 'test', 'test1', 'test2', 123)
test.id = 15
