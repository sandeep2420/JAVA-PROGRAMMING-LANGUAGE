import java.sql.*;
import java.util.Scanner;

public class StudentCRUD {

    static final String URL = "jdbc:mysql://localhost:3306/college";
    static final String USER = "root";
    static final String PASSWORD = "root";   // Change to your password

    public static void main(String[] args) {

        Scanner scan = new Scanner(System.in);

        try {

            // Load driver (Optional in newer versions)
            Class.forName("com.mysql.cj.jdbc.Driver");

            Connection con = DriverManager.getConnection(URL, USER, PASSWORD);

            int choice;

            do {
                System.out.println("\n--- STUDENT CRUD MENU ---");
                System.out.println("1. Insert Student");
                System.out.println("2. View Students");
                System.out.println("3. Update Student");
                System.out.println("4. Delete Student");
                System.out.println("5. Exit");
                System.out.print("Enter choice: ");
                choice = scan.nextInt();

                switch (choice) {

                    case 1:
                        System.out.print("Enter Roll: ");
                        int roll = scan.nextInt();
                        scan.nextLine();

                        System.out.print("Enter Name: ");
                        String name = scan.nextLine();

                        System.out.print("Enter Marks: ");
                        int marks = scan.nextInt();

                        String insertQuery = "INSERT INTO student VALUES (?, ?, ?)";
                        PreparedStatement psInsert = con.prepareStatement(insertQuery);
                        psInsert.setInt(1, roll);
                        psInsert.setString(2, name);
                        psInsert.setInt(3, marks);

                        psInsert.executeUpdate();
                        System.out.println("Student inserted successfully.");
                        break;

                    case 2:
                        String selectQuery = "SELECT * FROM student";
                        Statement st = con.createStatement();
                        ResultSet rs = st.executeQuery(selectQuery);

                        System.out.println("\n--- Student Records ---");
                        while (rs.next()) {
                            System.out.println(
                                    rs.getInt("roll") + " " +
                                            rs.getString("name") + " " +
                                            rs.getInt("marks")
                            );
                        }
                        break;

                    case 3:
                        System.out.print("Enter Roll to update: ");
                        int uRoll = scan.nextInt();
                        System.out.print("Enter new Marks: ");
                        int newMarks = scan.nextInt();

                        String updateQuery = "UPDATE student SET marks=? WHERE roll=?";
                        PreparedStatement psUpdate = con.prepareStatement(updateQuery);
                        psUpdate.setInt(1, newMarks);
                        psUpdate.setInt(2, uRoll);

                        psUpdate.executeUpdate();
                        System.out.println("Student updated successfully.");
                        break;

                    case 4:
                        System.out.print("Enter Roll to delete: ");
                        int dRoll = scan.nextInt();

                        String deleteQuery = "DELETE FROM student WHERE roll=?";
                        PreparedStatement psDelete = con.prepareStatement(deleteQuery);
                        psDelete.setInt(1, dRoll);

                        psDelete.executeUpdate();
                        System.out.println("Student deleted successfully.");
                        break;

                    case 5:
                        System.out.println("Exiting...");
                        break;

                    default:
                        System.out.println("Invalid choice!");
                }

            } while (choice != 5);

            con.close();
            scan.close();

        } catch (Exception e) {
            System.out.println("Error: " + e);
        }
    }
}
