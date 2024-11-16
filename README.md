package com.mycompany.registrationform;

import javax.swing.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class RegistrationForm {
    public static void main(String[] args) {
        // Create frame
        JFrame frame = new JFrame("Registration Form");
        frame.setSize(400, 400);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setLayout(null);

        // Name Label and TextField
        JLabel nameLabel = new JLabel("Name:");
        nameLabel.setBounds(50, 50, 100, 30);
        frame.add(nameLabel);

        JTextField nameField = new JTextField();
        nameField.setBounds(150, 50, 200, 30);
        frame.add(nameField);

        // Mobile Label and TextField
        JLabel mobileLabel = new JLabel("Mobile:");
        mobileLabel.setBounds(50, 100, 100, 30);
        frame.add(mobileLabel);

        JTextField mobileField = new JTextField();
        mobileField.setBounds(150, 100, 200, 30);
        frame.add(mobileField);

        // Gender Label and Radio Buttons
        JLabel genderLabel = new JLabel("Gender:");
        genderLabel.setBounds(50, 150, 100, 30);
        frame.add(genderLabel);

        JRadioButton maleButton = new JRadioButton("Male");
        maleButton.setBounds(150, 150, 70, 30);
        frame.add(maleButton);

        JRadioButton femaleButton = new JRadioButton("Female");
        femaleButton.setBounds(230, 150, 100, 30);
        frame.add(femaleButton);

        ButtonGroup genderGroup = new ButtonGroup();
        genderGroup.add(maleButton);
        genderGroup.add(femaleButton);

        // Address Label and TextArea
        JLabel addressLabel = new JLabel("Address:");
        addressLabel.setBounds(50, 200, 100, 30);
        frame.add(addressLabel);

        JTextArea addressArea = new JTextArea();
        addressArea.setBounds(150, 200, 200, 50);
        frame.add(addressArea);

        // Terms and Conditions Checkbox
        JCheckBox termsCheckBox = new JCheckBox("Accept Terms and Conditions.");
        termsCheckBox.setBounds(50, 270, 300, 30);
        frame.add(termsCheckBox);

        // Submit and Reset Buttons
        JButton submitButton = new JButton("Submit");
        submitButton.setBounds(50, 320, 100, 30);
        frame.add(submitButton);

        JButton resetButton = new JButton("Reset");
        resetButton.setBounds(200, 320, 100, 30);
        frame.add(resetButton);

        // Action listener for the Submit button
        submitButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                // Collect the data from the fields
                String name = nameField.getText();
                String mobile = mobileField.getText();
                String gender = maleButton.isSelected() ? "Male" : "Female";
                String address = addressArea.getText();
                boolean termsAccepted = termsCheckBox.isSelected();

                // Display the results in a new window
                JFrame resultFrame = new JFrame("Registration Details");
                resultFrame.setSize(300, 300);
                resultFrame.setDefaultCloseOperation(JFrame.DISPOSE_ON_CLOSE);
                resultFrame.setLayout(null);

                // Create labels to display the collected data
                JLabel resultLabel = new JLabel("<html><b>Name:</b> " + name + "<br><b>Mobile:</b> " + mobile + 
                                                "<br><b>Gender:</b> " + gender + "<br><b>Address:</b> " + address + 
                                                "<br><b>Terms Accepted:</b> " + (termsAccepted ? "Yes" : "No") + "</html>");
                resultLabel.setBounds(20, 20, 250, 200);
                resultFrame.add(resultLabel);

                // Make the result frame visible
                resultFrame.setVisible(true);
            }
        });

        // Make Frame Visible
        frame.setVisible(true);
    }
}
