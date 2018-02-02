#include "stdafx.h" 
#include <iostream> 
#include <string>
#include <fstream>
using namespace std;

const int CLASS_SIZE = 10;

struct studentType 
{ 
	string studentFName, studentLName; 
	int testScore; 
	char grade; 
};

void getData(studentType students[]) 
{	
	ifstream inFile; 
	inFile.open("Ch9_InputData.txt");

	for (int i = 0; i < CLASS_SIZE; i++)
	{
		inFile >> students[i].studentFName >> students[i].studentLName >> students[i].testScore;
	}
}

void assignGrade(studentType students[]) 
{ 
	for (int i = 0; i < CLASS_SIZE; i++) 
	{ 
		if (students[i].testScore >= 90) 
		{ 
			students[i].grade = 'A'; 
		}
		else if (students[i].testScore >= 80) 
		{ 
			students[i].grade = 'B'; 
		} 
		else if (students[i].testScore >= 70) 
		{ 
			students[i].grade = 'C'; 
		} 
		else if (students[i].testScore >= 60) 
		{ 
			students[i].grade = 'D'; 
		} 
		else if (students[i].testScore)
		{ 
			students[i].grade = 'F'; 
		} 
	} 
}

void findHighest(studentType students[]) {
	int highest = 0; 
	int counter = 0;
	fstream fout;

	for (int i = 0; i < CLASS_SIZE; i++)
	{
		if (students[i].testScore > counter)
		{
			highest = students[i].testScore;
			counter = i;
		}
	}
	fout.open("Ch9_OutputData.txt");
	fout << students[counter].studentFName << " " << students[counter].studentLName << " " << students[counter].testScore << endl;
	cout << students[counter].studentFName << " " << students[counter].studentLName << " " << students[counter].testScore << endl;
	fout.close();
}

void printResults(studentType students[]) {
	ofstream fout; 
	fout.open("Ch9_OutputData.txt"); 
	cout << "Student Name	Test Score		Grade";

	for (int i = 0; i < CLASS_SIZE; i++)
	{

		fout << students[i].studentFName << " " << students[i].studentLName << " " << students[i].testScore << " " << students[i].grade << endl;
		cout << students[i].studentFName << " " << students[i].studentLName << " " << students[i].testScore << " " <<  students[i].grade << endl;
	}
	fout.close();
}

int main() 
{
	studentType students[CLASS_SIZE];

	getData(students);
	assignGrade(students);
	printResults(students);
	findHighest(students);

	system("pause");
	return 0;
}
