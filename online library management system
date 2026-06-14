import java.util.ArrayList;
import java.util.Scanner;

class Book {
    String title;
    boolean available;

    public Book(String title) {
        this.title = title;
        this.available = true;
    }
}

class Student {
    String name;
    ArrayList<Book> borrowedBooks;

    public Student(String name) {
        this.name = name;
        borrowedBooks = new ArrayList<>();
    }

    public void borrowBook(Book book) {
        if (borrowedBooks.size() >= 5) {
            System.out.println("Borrowing limit exceeded! Maximum is 5 books.");
            return;
        }

        if (book.available) {
            borrowedBooks.add(book);
            book.available = false;
            System.out.println("Book borrowed successfully.");
        } else {
            System.out.println("Book is currently unavailable.");
        }
    }

    public void returnBook(Book book, int daysLate) {
        if (borrowedBooks.contains(book)) {
            borrowedBooks.remove(book);
            book.available = true;

            double fine = calculateFine(daysLate);

            System.out.println("Book returned successfully.");

            if (fine > 0) {
                System.out.println("Late Fine: KES " + fine);
            } else {
                System.out.println("No fine charged.");
            }
        } else {
            System.out.println("This book was not borrowed by the student.");
        }
    }

    public double calculateFine(int daysLate) {
        double finePerDay = 10.0;

        if (daysLate > 0) {
            return daysLate * finePerDay;
        }

        return 0;
    }

    public void displayBorrowedBooks() {
        System.out.println("\nBooks borrowed by " + name + ":");

        if (borrowedBooks.isEmpty()) {
            System.out.println("No books borrowed.");
            return;
        }

        for (Book book : borrowedBooks) {
            System.out.println("- " + book.title);
        }
    }
}

public class LibraryManagementSystem {

    public static void main(String[] args) {

        Scanner input = new Scanner(System.in);

        Book book1 = new Book("Java Programming");
        Book book2 = new Book("Database Systems");
        Book book3 = new Book("Data Structures");
        Book book4 = new Book("Operating Systems");
        Book book5 = new Book("Computer Networks");

        Student student = new Student("Brian");

        int choice;

        do {
            System.out.println("\n===== LIBRARY MANAGEMENT SYSTEM =====");
            System.out.println("1. Borrow Book");
            System.out.println("2. Return Book");
            System.out.println("3. Check Book Availability");
            System.out.println("4. Display Borrowed Books");
            System.out.println("5. Exit");
            System.out.print("Enter choice: ");

            choice = input.nextInt();

            switch (choice) {

                case 1:
                    System.out.println("\nAvailable Books:");
                    System.out.println("1. " + book1.title);
                    System.out.println("2. " + book2.title);
                    System.out.println("3. " + book3.title);
                    System.out.println("4. " + book4.title);
                    System.out.println("5. " + book5.title);

                    System.out.print("Select book: ");
                    int borrowChoice = input.nextInt();

                    switch (borrowChoice) {
                        case 1:
                            student.borrowBook(book1);
                            break;
                        case 2:
                            student.borrowBook(book2);
                            break;
                        case 3:
                            student.borrowBook(book3);
                            break;
                        case 4:
                            student.borrowBook(book4);
                            break;
                        case 5:
                            student.borrowBook(book5);
                            break;
                        default:
                            System.out.println("Invalid selection.");
                    }
                    break;

                case 2:
                    student.displayBorrowedBooks();

                    System.out.println("\nSelect Book to Return:");
                    System.out.println("1. Java Programming");
                    System.out.println("2. Database Systems");
                    System.out.println("3. Data Structures");
                    System.out.println("4. Operating Systems");
                    System.out.println("5. Computer Networks");

                    int returnChoice = input.nextInt();

                    System.out.print("Enter days late: ");
                    int daysLate = input.nextInt();

                    switch (returnChoice) {
                        case 1:
                            student.returnBook(book1, daysLate);
                            break;
                        case 2:
                            student.returnBook(book2, daysLate);
                            break;
                        case 3:
                            student.returnBook(book3, daysLate);
                            break;
                        case 4:
                            student.returnBook(book4, daysLate);
                            break;
                        case 5:
                            student.returnBook(book5, daysLate);
                            break;
                        default:
                            System.out.println("Invalid selection.");
                    }
                    break;

                case 3:
                    System.out.println("\nBook Availability Status:");

                    System.out.println(book1.title + " : " +
                            (book1.available ? "Available" : "Borrowed"));

                    System.out.println(book2.title + " : " +
                            (book2.available ? "Available" : "Borrowed"));

                    System.out.println(book3.title + " : " +
                            (book3.available ? "Available" : "Borrowed"));

                    System.out.println(book4.title + " : " +
                            (book4.available ? "Available" : "Borrowed"));

                    System.out.println(book5.title + " : " +
                            (book5.available ? "Available" : "Borrowed"));
                    break;

                case 4:
                    student.displayBorrowedBooks();
                    break;

                case 5:
                    System.out.println("Exiting system...");
                    break;

                default:
                    System.out.println("Invalid choice.");
            }

        } while (choice != 5);

        input.close();
    }
}