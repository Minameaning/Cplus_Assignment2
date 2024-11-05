#include <iostream>
#include <string>
#include <limits> // For numeric_limits
using namespace std;

int main() {
    const int MAX_STUDENTS = 100;
    int numStudents = 0;

    string studentNames[MAX_STUDENTS];
    int mathGrades[MAX_STUDENTS];
    int scienceGrades[MAX_STUDENTS];
    int englishGrades[MAX_STUDENTS];
    double averages[MAX_STUDENTS];
    char choice;

    do {
        // Ask user to enter their name
        cout << "Enter name for student " << numStudents + 1 << ": ";
        cin >> studentNames[numStudents];

        // Input Math grade with error handling
        while (true) {
            try {
                cout << "Enter Math grade: ";
                if (!(cin >> mathGrades[numStudents])) {
                    throw invalid_argument("Invalid input for Math grade.");
                }
                break; // Exit loop if input is valid
            } catch (const invalid_argument& e) {
                cout << "Error: " << e.what() << endl;
                cin.clear(); // Clear the error flag
                cin.ignore(numeric_limits<streamsize>::max(), '\n'); // Ignore invalid input
            }
        }

        // Input Science grade with error handling
        while (true) {
            try {
                cout << "Enter Science grade: ";
                if (!(cin >> scienceGrades[numStudents])) {
                    throw invalid_argument("Invalid input for Science grade.");
                }
                break; // Exit loop if input is valid
            } catch (const invalid_argument& e) {
                cout << "Error: " << e.what() << endl;
                cin.clear(); // Clear the error flag
                cin.ignore(numeric_limits<streamsize>::max(), '\n'); // Ignore invalid input
            }
        }

        // Input English grade with error handling
        while (true) {
            try {
                cout << "Enter English grade: ";
                if (!(cin >> englishGrades[numStudents])) {
                    throw invalid_argument("Invalid input for English grade.");
                }
                break; // Exit loop if input is valid
            } catch (const invalid_argument& e) {
                cout << "Error: " << e.what() << endl;
                cin.clear(); // Clear the error flag
                cin.ignore(numeric_limits<streamsize>::max(), '\n'); // Ignore invalid input
            }
        }

        // Find an average of all grades
        averages[numStudents] = (mathGrades[numStudents] + scienceGrades[numStudents] + englishGrades[numStudents]) / 3.0;

        // Display student information
        cout << endl << "Student Information:" << endl;
        cout << "Name: " << studentNames[numStudents] << endl;
        cout << "Math grade: " << mathGrades[numStudents] << endl;
        cout << "Science grade: " << scienceGrades[numStudents] << endl;
        cout << "English grade: " << englishGrades[numStudents] << endl;
        cout << "Average Grade: " << averages[numStudents] << endl;
        cout << (averages[numStudents] >= 60 ? "Result: Passed" : "Result: Failed") << endl;

        // Find the highest grade
        int highestGrade = max(mathGrades[numStudents], max(scienceGrades[numStudents], englishGrades[numStudents]));
        // Find the lowest grade
        int lowestGrade = min(mathGrades[numStudents], min(scienceGrades[numStudents], englishGrades[numStudents]));

        cout << "Highest Grade: " << highestGrade << endl;
        cout << "Lowest Grade: " << lowestGrade << endl;

        if (averages[numStudents] > 85) {
            cout << "Congratulations! Excellent performance!" << endl;
        }
        cout << "-----------------------------" << endl;

        numStudents++;

        cout << "Do you want to enter another student? (y/n): ";
        cin >> choice;
    } while (choice == 'y' || choice == 'Y');

    // Calculate and display class average
    double classAverage = 0;
    for (int i = 0; i < numStudents; ++i) {
        classAverage += averages[i];
    }
    classAverage /= numStudents;
    cout << "Class Average Grade: " << classAverage << endl;

    // Find and display top-performing student
    int topStudent = 0;
    for (int i = 1; i < numStudents; ++i) {
        if (averages[i] > averages[topStudent]) {
            topStudent = i;
        }
    }
    cout << "Top Performing Student: " << studentNames[topStudent] << endl;

    return 0;
}
