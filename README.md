// BakhietIbrahimCH9A.cpp : Defines the entry point for the console application.
//

#include "stdafx.h"
#include <iostream>
#include <fstream>
using namespace std;

const int CLASS_SIZE = 10;

struct studentType
{
	string studentFName, studentLName;
	int testScore;
	char grade;
};


void getData(studentType students[CLASS_SIZE])
{
	ifstream inFile;
	inFile.open("Ch9_OutputData.txt");
	cout << "Enter first name, last name, and score: ";
	
	for (int i = 0; i < CLASS_SIZE; i++)
	{
		inFile >> students[i].studentFName >> students[i].studentLName >> students[i].testScore;
		cin >> students[i].studentFName >> students[i].studentLName >> students[i].testScore;
	}
}

char assignGrade(studentType students[CLASS_SIZE])
{
}

int main()
{
	studentType students[CLASS_SIZE];

	getData(students);

	system("pause");
	return 0;
}


