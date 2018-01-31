#include "stdafx.h"
#include <iostream
#include <fstream>
#include <string>
using namespace std;

const int CLASS_SIZE = 10;

struct studentType {
    string studentFName,studentLName;
    int testScore;
    char grade; };

void getData(studentType students[CLASS_SIZE])
{
    ifstream inFile;
    inFile.open("Ch9_OutputData.txt");
    
    for (int i = 0; i < CLASS_SIZE; i++)
    {
        inFile >> students[i].studentFName >> students[i].studentLName >> students[i].testScore;
        cin >> students[i].studentFName >> students[i].studentLName >> students[i].testScore;
    }
}

void assignGrade(studentType students[CLASS_SIZE])
{
    for (i = 0; i < CLASS_SIZE)
    {
        if (students[i].testScore >= 900)
        {
            students[i].grade = 'A';
        }
        else if (students[i].testScore >= 800)
        {
            students[i].grade = 'B';
        }
        else if (students[i].testScore >= 700)
        {
            students[i].grade = 'C';
        }
        else if (students[i].testScore >= 600)
        {
            students[i].grade = 'D';
        }
        else if (students[i].testScore
        {
            students[i].grade = 'F';
        }
    }
}

void findHighest(studentType students[CLASS_SIZE])
{
    int highest = 0;
    int counter = 0;
    
    for (i = 0; i < CLASS_SIZE; i++)
    {
        if (students[i].testScore > counter;)
        {
            highest = students[i].testScore;
            counter = i;
        }
    }
    fout.open("Ch9_OutputData.txt");
    fout << students[counter].studentFName << " " << students[counter].studentLName << " " << students[counter].testScore;
    cout << students[counter].studentFName << " " << students[counter].studentLName << " " << students[counter].testScore;
    fout.close("Ch9_OutputData.txt");
}

void printResults (studentType students[CLASS_SIZE])
{
    ofstream fout;
    fout.open("Ch9_OutputData.txt");
    cout << "Student Name   Test Score  Grade";
    
    for (i = 0; i < CLASS_SIZE; i++)
    {
        
            << students[counter].studentFName << " " << students[counter].studentLName << " " << students[i].testScore << students[i].Grade;
        cout << students[counter].studentFName << " " << students[counter].studentLName << " " << students[i].testScore << students[i].Grade;
    }
    fout.close("Ch9_OutputData.txt");
}

int main() {
    studentType students[CLASS_SIZE];
    
    getData(students);
    assignGrade(studentType students[CLASS_SIZE]);
    printResults (studentType students[CLASS_SIZE]);
    findHighest(studentType students[CLASS_SIZE])
    
    system("pause");
    return 0;
}
