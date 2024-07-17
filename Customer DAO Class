import javax.swing.*;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.util.List;

public class CustomerSwing extends JFrame {
    private JLabel idLabel, lastNameLabel, firstNameLabel, phoneLabel;
    private JTextField idField, lastNameField, firstNameField, phoneField;
    private JButton nextButton, prevButton;
    private List<Customer> customers;
    private int currentIndex = 0;

    public CustomerSwing() {
        setTitle("Customer");
        setSize(300, 200);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLayout(new GridLayout(5, 2));

        idLabel = new JLabel("ID:");
        lastNameLabel = new JLabel("Last Name:");
        firstNameLabel = new JLabel("First Name:");
        phoneLabel = new JLabel("Phone:");

        idField = new JTextField();
        lastNameField = new JTextField();
        firstNameField = new JTextField();
        phoneField = new JTextField();

        idField.setEditable(false);
        lastNameField.setEditable(false);
        firstNameField.setEditable(false);
        phoneField.setEditable(false);

        nextButton = new JButton("Next");
        prevButton = new JButton("Previous");

        add(idLabel);
        add(idField);
        add(lastNameLabel);
        add(lastNameField);
        add(firstNameLabel);
        add(firstNameField);
        add(phoneLabel);
        add(phoneField);
        add(prevButton);
        add(nextButton);

        CustomerDAO customerDAO = new CustomerDAO();
        customers = customerDAO.getAllCustomers();
        showCustomer(0);

        nextButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                if (currentIndex < customers.size() - 1) {
                    currentIndex++;
                    showCustomer(currentIndex);
                }
            }
        });

        prevButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                if (currentIndex > 0) {
                    currentIndex--;
                    showCustomer(currentIndex);
                }
            }
        });
    }

    private void showCustomer(int index) {
        Customer customer = customers.get(index);
        idField.setText(String.valueOf(customer.getId()));
        lastNameField.setText(customer.getLastName());
        firstNameField.setText(customer.getFirstName());
        phoneField.setText(customer.getPhone());
    }

    public static void main(String[] args) {
        SwingUtilities.invokeLater(new Runnable() {
            @Override
            public void run() {
                new CustomerSwing().setVisible(true);
            }
        });
    }
}
