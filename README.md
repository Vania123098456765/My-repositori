# My-repositori
    Генератор обьектов класса "Robot" by A_Q_U_A_R_I_U_F
    continuation_request = input("Start programs?(print yes, else program will end)>>>")
    while continuation_request == "Yes" or continuation_request == "yes":

    # Coздание класса "Robot"
    class Robot:
        # Обьявление динамических атрибутов класса "Robot"
        model = None
        age = None
        work = None

        # Создание метода для записи данных в обьект
        def set_data(self, model, age, work):
            self.model = model
            self.age = age
            self.work = work

        # Создание метода для вывода данных обьекта
        def get_data(self):
            print("Robot model:", self.model, "Robot age:", self.age, "Robot work:", self.work)

        # Создание конструктора для работы методов в нём
        def init(self, model=None, age=None, work=None):
            self.set_data(model, age, work)
            self.get_data()


    # Запрос на создание обьекта класса "Robot"
    qestion = input("Do you want make object, class Robot?(print yes, else program will end)>>>")

    if "Yes" in qestion or "yes" in qestion:
        # Запрос на количество создаваемых обьектов
        try:
            more_object = int(input("How many?>>>"))
        except ValueError:
            q = True
            while True:
                try:
                    more_object = int(input("How many?\033[31m Enter number>>> \033[0m"))
                except ValueError:
                    q = q
                else:
                    q = False

        c = 0

        while c != more_object:
            # Создание обьекта
            name_object = input(f"Enter name object{c + 1}, class robot>>>")
            robot_model = input("Enter robot model>>>")
            try:
                robot_age = int(input("Enter robot age>>>"))
            except ValueError:
                q = True
                while q:
                    try:
                        robot_age = int(input("\033[31m Enter correct robot age>>>\033[0m"))
                    except ValueError:
                        q = q
                    else:
                        q = False
            robot_work = input("Enter work robot(Yes or No)>>>")
            if "Yes" in robot_work or "No" in robot_work:
                q = False
            else:
                q = True
                while q:
                    robot_work = input("Enter work robot(Yes or No)>>>")
                    if "Yes" in robot_work or "No" in robot_work:
                        q = False
                    else:
                        q = True
            print("Name object:",name_object)
            name_object = Robot(robot_model, robot_age, robot_work)
            c += 1
        continuation_request = input("Continue program(print yes, else program will end)>>>")
    else:
        continuation_request = input("Continue program(print yes, else program will end)>>>")
