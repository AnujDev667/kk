# anuj project based on Training and Placement System on Java,swing deployed on NetBeans

#Connecting to database
import java.sql.*;
import javax.swing.*;

public class Connect {
    Connection con = null;

    public static Connection ConnectDB() {
        try {
            Class.forName("com.mysql.jdbc.Driver");
            Connection con = DriverManager.getConnection("jdbc:mysql://localhost/tps_db", "root", "");
            return con;
        } catch (ClassNotFoundException | SQLException e) {
            JOptionPane.showMessageDialog(null, e);
            return null;
        }
    }

    public static void main(String[] args) {
        // Call the ConnectDB method here or perform other tasks
        Connection connection = ConnectDB();
        if (connection != null) {
            JOptionPane.showMessageDialog(null, "Connection successful!");
            // Perform other database-related operations if needed
        } else {
            JOptionPane.showMessageDialog(null, "Connection failed!");
        }
    }
}
