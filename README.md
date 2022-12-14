class AbstractAcademy {
    public:
        string Name;
        int NumberOfStudents;
        int NumberOfTeachers;
        bool IsFree;
        
        virtual void teach()=0;
        void getDescription() {
            cout << "This is a description for abstract academy" << endl;
        }
};

class Subject {
    public:
        string Name;
        int PassingGrade;
        
        void getDescription() {
            cout << "This is a class for " << Name << " subject " << endl;
        }
};

class University: public AbstractAcademy {
    public:
        void teach() {
            cout << "Conducting a lecture" << endl;
        }
        
        void teach(Subject subject) {
            cout << "University is coductting a " << subject.Name << " lecture " << endl;
        }
        
        
        // Overriding getDescription
        void getDescription() {
            cout << "Name: " << Name << endl;
            cout << "Number of students: " << NumberOfStudents << endl;
            cout << "Number of teachers: " << NumberOfTeachers << endl;
            
        }
};

class AbstractStudent {
    public:
        string FirstName;
        string LastName;
        int Age;
        
        virtual void attendLesson()=0;
        void getDescription() {
            cout << "This is a discription for abstract student" << endl;
        }
};

class UniversityStudent: public AbstractStudent {
    public:
        University university;
        Subject subject;
        
        void attendLesson() {
            cout << FirstName << " " << LastName <<" is attending " << subject.Name << " lecture " << endl;
        }
        
        void attendLesson(string subjectName) {
            cout << FirstName << " " << LastName << " " << " is attend a " << subjectName << " lecture " << endl;
        }
        
        void attendLesson(Subject subject) {
            cout << FirstName << " " << LastName << " " << " is attend a " << subject.Name << " lecture " << endl;
        }
        
        // Overridding getDescription
        void getDescription() {
            cout << "First Name: " << FirstName << endl;
            cout << "Last Name: " << LastName << endl;
            cout << "Age: " << Age << endl;
            cout << "University: " << university.Name << endl;
            cout << "Subject: " << subject.Name << endl;
            
        }
};


int main()
{
    University freeUni;
    freeUni.Name = " Free University";
    freeUni.NumberOfStudents = 2000;
    freeUni.NumberOfTeachers = 150;
    freeUni.IsFree = false;
    
    // freeUni.getDescription();
    // freeUni.teach();
    
    Subject math;
    math.Name = "Mathematics";
    math.PassingGrade = 70;
    
    Subject computerScience;
    computerScience.Name = "Computer Science";
    computerScience.PassingGrade = 51;
    
    UniversityStudent student1;
    student1.FirstName = "Gigi";
    student1.LastName = "Nadirashvili";
    student1.Age = 24;
    student1.university = freeUni;
    student1.subject = math;
    
    // student1.getDescription();
    // freeUni.teach(math);
    
    student1.attendLesson(computerScience);
