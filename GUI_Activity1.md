```java
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import javax.swing.*;

public class Main extends JFrame implements ActionListener
{
    private JLabel wLabel;
    private JLabel hLabel;
    private JLabel sLabel;
    private JTextField wField;
    private JTextField sField;
    private JTextField hField;

    Main()
    {
        GridBagConstraints layoutConst = null;

        setTitle("Salary");

        wLabel = new JLabel("Hourly wage:");
        hLabel = new JLabel("Hours:");
        sLabel = new JLabel("Yearly salary:");

        wField = new JTextField(15);
        wField.setEditable(true);
        wField.setText("");

        hField = new JTextField(15);
        hField.setEditable(true);
        hField.setText("");

        sField = new JTextField(15);
        sField.setEditable(false);

        setLayout(new GridBagLayout());

        layoutConst = new GridBagConstraints();
        layoutConst.gridx = 0;
        layoutConst.gridy = 0;
        layoutConst.insets = new Insets(10, 10, 10, 10);
        add(wLabel, layoutConst);

        layoutConst = new GridBagConstraints();
        layoutConst.gridx = 1;
        layoutConst.gridy = 0;
        layoutConst.insets = new Insets(10, 10, 10, 10);
        add(wField, layoutConst);

        layoutConst = new GridBagConstraints();
        layoutConst.gridx = 0;
        layoutConst.gridy = 1;
        layoutConst.insets = new Insets(10, 10, 10, 10);
        add(hLabel, layoutConst);

        layoutConst = new GridBagConstraints();
        layoutConst.gridx = 1;
        layoutConst.gridy = 1;
        layoutConst.insets = new Insets(10, 10, 10, 10);
        add(hField, layoutConst);

        layoutConst = new GridBagConstraints();
        layoutConst.gridx = 0;
        layoutConst.gridy = 2;
        layoutConst.insets = new Insets(10, 10, 10, 10);
        add(sLabel, layoutConst);

        layoutConst = new GridBagConstraints();
        layoutConst.gridx = 1;
        layoutConst.gridy = 2;
        layoutConst.insets = new Insets(10, 10, 10, 10);
        add(sField, layoutConst);

        layoutConst = new GridBagConstraints();
        JButton calculate = new JButton("Calculate");
        layoutConst.gridy = 3;
        layoutConst.insets = new Insets(10, 10, 10, 10);
        calculate.addActionListener(this);
        add(calculate, layoutConst);
    }
    public void actionPerformed(ActionEvent event)
    {
        String wageInput;
        String hourInput;
        int hours;
        int hourlyWage;

        wageInput = wField.getText();
        hourInput = hField.getText();

        hourlyWage = Integer.parseInt(wageInput);
        hours = Integer.parseInt(hourInput);

        sField.setText(Integer.toString(hourlyWage * hours * 52));
    }
    public static void main(String[] args)
    {
        Main myFrame = new Main();

        myFrame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        myFrame.pack();
        myFrame.setVisible(true);
    }
}
```
