# FILE-HANDLING-UTILITY

Name:SHEETHAL P V

Company:CODTECH IT SOLUTIONS 

ID:CT6WTDS627

DOMAIN:JAVA PROGRAMMING

DURATION-NOV 25th ,2024 to JAN 10th ,2025

MENTOR NAME-Neela Santhosh Kumar

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
