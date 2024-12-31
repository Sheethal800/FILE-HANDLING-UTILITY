# FILE-HANDLING-UTILITY-TASK 1

Name:SHEETHAL P V

Company:CODTECH IT SOLUTIONS 

ID:CT6WTDS627

DOMAIN:JAVA PROGRAMMING

DURATION-NOV 25th ,2024 to JAN 10th ,2025

MENTOR NAME-Neela Santhosh Kumar

###Objectives:
1 File Management:
Demonstrate basic file handling in Java by performing operations like reading, writing, and modifying text files.
2 Reading from Files:
Read the content of an existing file line by line and print it on the console to ensure that the file is being accessed correctly.
3 Writing to Files:
Write new content to a file. The program should overwrite any existing content when writing

###Key Features:
BufferedReader: Used to read characters from a file efficiently, one line at a time.
BufferedWriter: Used to write characters to a file efficiently, including the ability to append data by enabling true in the FileWriter constructor.
FileWriter: A convenient class for writing characters to files.

import java.io.*;
import java.nio.file.*;
import java.util.Scanner;

public class FileOperations {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // File path to read/write
        String filePath = "example.txt";

        // Write to file
        writeToFile(filePath);

        // Read from file
        readFromFile(filePath);

        // Modify file (append text to the file)
        modifyFile(filePath);

        // Read the file again after modification
        readFromFile(filePath);
    }

    // Method to write data to the file
    public static void writeToFile(String filePath) {
        try (BufferedWriter writer = new BufferedWriter(new FileWriter(filePath))) {
            writer.write("This is the first line in the file.\n");
            writer.write("This is the second line in the file.\n");
            System.out.println("Data written to the file successfully.");
        } catch (IOException e) {
            System.out.println("An error occurred while writing to the file.");
            e.printStackTrace();
        }
    }

    // Method to read data from the file
    public static void readFromFile(String filePath) {
        try (BufferedReader reader = new BufferedReader(new FileReader(filePath))) {
            String line;
            System.out.println("Reading from file:");
            while ((line = reader.readLine()) != null) {
                System.out.println(line);
            }
        } catch (IOException e) {
            System.out.println("An error occurred while reading from the file.");
            e.printStackTrace();
        }
    }

    // Method to modify (append) data to the file
    public static void modifyFile(String filePath) {
        try (BufferedWriter writer = new BufferedWriter(new FileWriter(filePath, true))) {
            writer.write("This is an additional line appended to the file.\n");
            System.out.println("Data appended to the file successfully.");
        } catch (IOException e) {
            System.out.println("An error occurred while modifying the file.");
            e.printStackTrace();
        }
    }
}
#OUTPUT OF THE TASK
![Sheethal800](https://github.com/user-attachments/assets/3b7c2cbe-205c-4d12-bf43-8337141f069c)

