import javax.swing.*;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class ColorfulLoginPage {
    public static void main(String[] args) {
        // Create the frame
        JFrame frame = new JFrame("Login Page");
        frame.setSize(400, 300);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setLayout(null);

        // Add a header panel
        JPanel headerPanel = new JPanel();
        headerPanel.setBounds(0, 0, 400, 50);
        headerPanel.setBackground(new Color(34, 139, 34)); // Green header
        frame.add(headerPanel);

        JLabel headerLabel = new JLabel("Welcome to the Login Page");
        headerLabel.setForeground(Color.WHITE);
        headerLabel.setFont(new Font("Arial", Font.BOLD, 16));
        headerPanel.add(headerLabel);

        // Username label
        JLabel usernameLabel = new JLabel("Username:");
        usernameLabel.setBounds(50, 80, 100, 30);
        usernameLabel.setForeground(new Color(25, 25, 112)); // Dark blue text
        usernameLabel.setFont(new Font("Arial", Font.PLAIN, 14));
        frame.add(usernameLabel);

        // Username text field
        JTextField usernameField = new JTextField();
        usernameField.setBounds(150, 80, 180, 30);
        usernameField.setBackground(new Color(240, 255, 255)); // Light cyan background
        frame.add(usernameField);

        // Password label
        JLabel passwordLabel = new JLabel("Password:");
        passwordLabel.setBounds(50, 130, 100, 30);
        passwordLabel.setForeground(new Color(178, 34, 34)); // Firebrick red text
        passwordLabel.setFont(new Font("Arial", Font.PLAIN, 14));
        frame.add(passwordLabel);

        // Password field
        JPasswordField passwordField = new JPasswordField();
        passwordField.setBounds(150, 130, 180, 30);
        passwordField.setBackground(new Color(255, 228, 225)); // Misty rose background
        frame.add(passwordField);

        // Login button
        JButton loginButton = new JButton("Login");
        loginButton.setBounds(150, 190, 80, 30);
        loginButton.setBackground(new Color(70, 130, 180)); // Steel blue button
        loginButton.setForeground(Color.WHITE);
        frame.add(loginButton);

        // Action listener for login button
        loginButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                String username = usernameField.getText();
                String password = new String(passwordField.getPassword());

                if (username.equals("admin") && password.equals("password")) {
                    JOptionPane.showMessageDialog(frame, "Login Successful!", "Success", JOptionPane.INFORMATION_MESSAGE);
                } else {
                    JOptionPane.showMessageDialog(frame, "Invalid Username or Password", "Error", JOptionPane.ERROR_MESSAGE);
                }
            }
        });

        // Set the frame visible
        frame.setVisible(true);
    }
}
