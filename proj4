using System;

class Program
{
    static void Main(string[] args)
    {
        Console.Write("Enter total students: ");
        int totalStudents = int.Parse(Console.ReadLine());

        string[] studentNames = new string[totalStudents];
        int[][] studentGrades = new int[totalStudents][];

        int choice;
        do
        {
            Console.WriteLine("\nWelcome to the Student Grades System!");
            Console.WriteLine("[1] Enroll Students");
            Console.WriteLine("[2] Enter Student Grades");
            Console.WriteLine("[3] Show Student Grades");
            Console.WriteLine("[4] Show Top Student");
            Console.WriteLine("[5] Exit");
            Console.Write("Enter Choice: ");
            choice = int.Parse(Console.ReadLine());

            switch (choice)
            {
                case 1:
                    EnrollStudents(studentNames);
                    break;
                case 2:
                    EnterStudentGrades(studentNames, studentGrades);
                    break;
                case 3:
                    ShowStudentGrades(studentNames, studentGrades);
                    break;
                case 4:
                    ShowTopStudent(studentNames, studentGrades);
                    break;
                case 5:
                    Console.WriteLine("Bye!");
                    break;
                default:
                    Console.WriteLine("Invalid choice. Please enter again.");
                    break;
            }
        } while (choice != 5);
    }


    static void EnrollStudents(string[] studentNames)
    {
        Console.WriteLine("\nEnroll Students");
        for (int i = 0; i < studentNames.Length; i++)
        {
            Console.Write("Enter student name: ");
            studentNames[i] = Console.ReadLine();
        }
    }

    static void EnterStudentGrades(string[] studentNames, int[][] studentGrades)
    {
        Console.WriteLine("\nEnter Student Grades");
        for (int i = 0; i < studentNames.Length; i++)
        {
            Console.WriteLine($"Student: {studentNames[i]}");
            studentGrades[i] = new int[3];
            for (int j = 0; j < 3; j++)
            {
                bool validGrade = false;
                do
                {
                    Console.Write($"Enter grade for {(j == 0 ? "Science" : j == 1 ? "Math" : "English")}: ");
                    string input = Console.ReadLine();
                    if (int.TryParse(input, out int grade))
                    {
                        studentGrades[i][j] = grade;
                        validGrade = true;
                    }
                    else
                    {
                        Console.WriteLine("Invalid input. Please enter an integer.");
                    }
                } while (!validGrade);
            }
        }
    }

    static void ShowStudentGrades(string[] studentNames, int[][] studentGrades)
    {
        Console.WriteLine("\nStudent Grades");
        Console.WriteLine("Name\t\tScience\t\tMath\t\tEnglish\t\tAve.");
        for (int i = 0; i < studentNames.Length; i++)
        {
            int scienceGrade = studentGrades[i][0];
            int mathGrade = studentGrades[i][1];
            int englishGrade = studentGrades[i][2];
            double averageGrade = (scienceGrade + mathGrade + englishGrade) / 3.0;
            Console.WriteLine($"{studentNames[i]}\t\t{scienceGrade}\t\t{mathGrade}\t\t{englishGrade}\t\t{averageGrade}");
        }
    }

    static void ShowTopStudent(string[] studentNames, int[][] studentGrades)
    {
        int topStudentIndex = 0;
        double topStudentAverage = 0;

        for (int i = 0; i < studentNames.Length; i++)
        {
            int[] grades = studentGrades[i];
            double averageGrade = (grades[0] + grades[1] + grades[2]) / 3.0;

            if (averageGrade > topStudentAverage)
            {
                topStudentIndex = i;
                topStudentAverage = averageGrade;
            }
        }

        Console.WriteLine($"\nTop Student: {studentNames[topStudentIndex]}");
    }
}
