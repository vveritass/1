#include <iostream>
using namespace std;

const int LNAME = 25;
class STUDENT {
private:
    char name[LNAME];      // имя
    int age;                         // возраст
    float grade;                  // рейтинг
public:
    STUDENT() {
        setlocale(LC_ALL, "Russian");
        for (int i = 0; i <= 24; i++) {
            name[i] = 0;
        }
        age = 0;
        grade = 0;
    }
    char* GetName() { // получение имени
        return name;
    }
    int GetAge() const { // получение возраста
        return age;
    }
    float GetGrade() const { // получение рейтинга
        return grade;
    }
    void SetName(char* name) {  // установка имени 
        int i = 0;
        while (*name != 0) { //посимвольный перебор всего имени
            this->name[i] = *name; //присваивание его массиву
            name++;
            i++;
        }
    }
    void SetAge(int age) { // установка возраста
        this->age = age;
    }
    void SetGrade(float grade) { // установка рейтинга
        this->grade = grade;
    }
    void Set(char* name, int age, float grade) {   // установка всех трех полей
        int i = 0;
        while (*name != '\0') {
            this->name[i] = *name;
            name++;
            i++;
        }
        this->age = age;
        this->grade = grade;
    }
    void Show() {       // отображение информации о студенте
        cout << "Имя: " << name << endl;
        cout << "Возраст: " << age << endl;
        cout << "Рейтинг: " << grade << endl;
    }
};
    int main() {
        setlocale(LC_ALL, "Russian");
        STUDENT student; // Создание объекта класса STUDENT.
        char name[25];
        int age;
        float grade;
        cout << "Введите имя." << endl;
        cin >> name;
        cout << "Введите возраст." << endl;
        cin >> age;
        cout << "Введите рейтинг." << endl;
        cin >> grade;
        student.Set(name, age, grade);
        student.Show();

        return 0;
}
