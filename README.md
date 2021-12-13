# Project-5
/*
 * Class: CMSC140 CRN 20433_22867
 * Instructor: Grigoriy A. Grinberg
 * Project 5
 * Description: This program asks the user to enter 9 numbers and calculates whether or not it is 
 * a Lo Shu magic square.
 * Due Date: 12/06/21
 * I pledge that I have completed the programming assignment independently.
   I have not copied the code from a student or any source.
   I have not given my code to any student.
   Print your Full Name here: Hannah Menghis
*/

#include<iostream>
using namespace std;

// Global constants
const int ROWS = 3; 
const int COLS = 3; 
const int MIN = 1; 
const int MAX = 9; 

int main() 
{
	int first[COLS];
	int second[COLS];
	int third[COLS];
	char choice;
	string programmerName = "Hannah Menghis", dueDate = "12/06/21", projectNum = "5";

	//Asks for user to input values
	cout << "Enter the number for row 0 and column 0 :";
	cin >> first[0];
	cout << "Enter the number for row 0 and column 1 :";
	cin >> first[1];
	cout << "Enter the number for row 0 and column 2 :";
	cin >> first[2];
	cout << "Enter the number for row 1 and column 0 :";
	cin >> second[0];
	cout << "Enter the number for row 1 and column 1 :";
	cin >> second[1];
	cout << "Enter the number for row 1 and column 2 :";
	cin	>> second[2];
	cout << "Enter the number for row 2 and column 0 :";
	cin >> third[0];
	cout << "Enter the number for row 2 and column 1 :";
	cin >> third[1];
	cout << "Enter the number for row 2 and column 2 :";
	cin	>> third[2];

	cout << first[0] << " " << first[1] << " " << first[2] << endl;
	cout << second[0] << " " << second[1] << " " << second[2] << endl;
	cout << third[0] << " " << third[1] << " " << third[2] << endl;

	for (int i = 0; i < 3; i++) 
	{
		if (first[i] < MIN || first[i] > MAX ||
			second[i] < MIN || second[i] > MAX ||
			third[i] < MIN || third[i] > MAX) {
			cout << "Invalid input";
			return 0;
		}
	}
	int sum = first[0] + first[1] + first[2];

	int horSum[ROWS], verSum[COLS], diagSum1 = 0, diagSum2 = 0;
	for (int i = 0; i < ROWS; i++) 
	{
		horSum[i] = verSum[i] = 0;
	}

	for (int i = 0; i < COLS; i++) 
	{
		horSum[0] += first[i];
		horSum[1] += second[i];
		horSum[2] += third[i];
	}
	for (int i = 0; i < COLS; i++) 
	{
		verSum[i] = first[i] + second[i] + third[i];
	}
	diagSum1 = first[0] + second[1] + third[2];
	diagSum2 = first[2] + second[1] + third[0];
	bool correct = true;
	for (int i = 0; i < ROWS; i++)
		if (horSum[i] != sum) correct = false;
	for (int i = 0; i < COLS; i++)
		if (verSum[i] != sum) correct = false;
	if (diagSum1 != sum || diagSum2 != sum)
		correct = false;

	if (correct)
	{
		cout << "This is a Lo Shu magic square.";
		cout << endl;
		cout << endl;
		cout << endl;
	}
	else
	{
		cout << "This is not a Lo Shu magic square.";
		cout << endl;
		cout << endl;
		cout << endl;
	}
	cout << "Do you want to try again?";
	cin >> choice;
	if (choice = 'y' || 'Y')
	{
		cout << "Enter the number for row 0 and column 0 :";
		cin >> first[0];
		cout << "Enter the number for row 0 and column 1 :";
		cin >> first[1];
		cout << "Enter the number for row 0 and column 2 :";
		cin >> first[2];
		cout << "Enter the number for row 1 and column 0 :";
		cin >> second[0];
		cout << "Enter the number for row 1 and column 1 :";
		cin >> second[1];
		cout << "Enter the number for row 1 and column 2 :";
		cin >> second[2];
		cout << "Enter the number for row 2 and column 0 :";
		cin >> third[0];
		cout << "Enter the number for row 2 and column 1 :";
		cin >> third[1];
		cout << "Enter the number for row 2 and column 2 :";
		cin >> third[2];

		cout << first[0] << " " << first[1] << " " << first[2] << endl;
		cout << second[0] << " " << second[1] << " " << second[2] << endl;
		cout << third[0] << " " << third[1] << " " << third[2] << endl;

		for (int i = 0; i < 3; i++)
		{
			if (first[i] < MIN || first[i] > MAX ||
				second[i] < MIN || second[i] > MAX ||
				third[i] < MIN || third[i] > MAX) {
				cout << "Invalid input";
				return 0;
			}
		}
		int sum = first[0] + first[1] + first[2];

		int horSum[ROWS], verSum[COLS], diagSum1 = 0, diagSum2 = 0;
		for (int i = 0; i < ROWS; i++)
		{
			horSum[i] = verSum[i] = 0;
		}

		for (int i = 0; i < COLS; i++)
		{
			horSum[0] += first[i];
			horSum[1] += second[i];
			horSum[2] += third[i];
		}
		for (int i = 0; i < COLS; i++)
		{
			verSum[i] = first[i] + second[i] + third[i];
		}
		diagSum1 = first[0] + second[1] + third[2];
		diagSum2 = first[2] + second[1] + third[0];
		bool correct = true;
		for (int i = 0; i < ROWS; i++)
			if (horSum[i] != sum) correct = false;
		for (int i = 0; i < COLS; i++)
			if (verSum[i] != sum) correct = false;
		if (diagSum1 != sum || diagSum2 != sum)
			correct = false;

		if (correct)
		{
			cout << "This is a Lo Shu magic square.";
			cout << endl;
			cout << endl;
			cout << endl;
		}
		else
		{
			cout << "This is not a Lo Shu magic square.";
			cout << endl;
			cout << endl;
			cout << endl;
		}
	}
	else
	{
		cout << "Name: " << programmerName << endl;
		cout << "Project #: " << projectNum << endl;
		cout << "Due date: " << dueDate << endl;
	}
}
