# classes-and-objects-hackerrank-solution
This is a program for use of classes and objects determining how many students have a greater marks than a particular student.


#include <stdio.h>
#include <iostream>
using namespace std;

class Student
{
private:
    int sum;
    int Score[5];

public:
    Student() : sum(0) {}
    void input()
    {
        std::cout << "Enter marks of all 5 semesters: " << std::endl;
        for (int i = 0; i < 5; i++)
        {
            cin >> Score[i];
            sum += Score[i];
        }
    }
    int CalculateTotalScore()
    {
        return sum;
    }
};
int main()
{
    int n, count = 0;
    std::cout << "Enter number of students: " << std::endl;
    cin >> n;
    Student s[n];
    for (int i = 0; i < n; i++)
    {
        s[i].input();
    }
    std::cout << "Total Score of Ketan is " << s[0].CalculateTotalScore() << std::endl;
    for (int i = 1; i < n; i++)
    {
        s[i].CalculateTotalScore();
        if (s[i].CalculateTotalScore() > s[0].CalculateTotalScore())
        {
            count++;
        }
    }
    std::cout << "Number of students having total marks more than Ketan is: " << count << std::endl;

    return 0;
}
