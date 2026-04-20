```java
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import javax.swing.*;

public class Main extends JFrame implements ActionListener
{
    private JLabel dLabel;
    private JLabel kmLabel;
    private JLabel mLabel;
    private JLabel fLabel;
    private JTextField dField;
    private JTextField kmField;
    private JTextField mField;
    private JTextField fField;

    Main()
    {
        GridBagConstraints layoutConst = null;

        setTitle("Distance");

        dLabel = new JLabel("Distance(Miles):");
        kmLabel = new JLabel("Distance(Kilometers):");
        mLabel = new JLabel("Distance(Meters):");
        fLabel = new JLabel("Distance(Feet):");

        dField = new JTextField(15);
        dField.setEditable(true);
        dField.setText("");

        kmField = new JTextField(15);
        kmField.setEditable(false);

        mField = new JTextField(15);
        mField.setEditable(false);

        fField = new JTextField(15);
        fField.setEditable(false);

        setLayout(new GridBagLayout());

        layoutConst = new GridBagConstraints();
        layoutConst.gridx = 0;
        layoutConst.gridy = 0;
        layoutConst.insets = new Insets(10, 10, 10, 10);
        add(dLabel, layoutConst);

        layoutConst = new GridBagConstraints();
        layoutConst.gridx = 1;
        layoutConst.gridy = 0;
        layoutConst.insets = new Insets(10, 10, 10, 10);
        add(dField, layoutConst);

        layoutConst = new GridBagConstraints();
        layoutConst.gridx = 0;
        layoutConst.gridy = 1;
        layoutConst.insets = new Insets(10, 10, 10, 10);
        add(kmLabel, layoutConst);

        layoutConst = new GridBagConstraints();
        layoutConst.gridx = 1;
        layoutConst.gridy = 1;
        layoutConst.insets = new Insets(10, 10, 10, 10);
        add(kmField, layoutConst);

        layoutConst = new GridBagConstraints();
        layoutConst.gridx = 0;
        layoutConst.gridy = 2;
        layoutConst.insets = new Insets(10, 10, 10, 10);
        add(mLabel, layoutConst);

        layoutConst = new GridBagConstraints();
        layoutConst.gridx = 1;
        layoutConst.gridy = 2;
        layoutConst.insets = new Insets(10, 10, 10, 10);
        add(mField, layoutConst);

        layoutConst = new GridBagConstraints();
        layoutConst.gridx = 0;
        layoutConst.gridy = 3;
        layoutConst.insets = new Insets(10, 10, 10, 10);
        add(fLabel, layoutConst);

        layoutConst = new GridBagConstraints();
        layoutConst.gridx = 1;
        layoutConst.gridy = 3;
        layoutConst.insets = new Insets(10, 10, 10, 10);
        add(fField, layoutConst);

        layoutConst = new GridBagConstraints();
        JButton calculate = new JButton("Calculate");
        layoutConst.gridy = 4;
        layoutConst.insets = new Insets(10, 10, 10, 10);
        calculate.addActionListener(this);
        add(calculate, layoutConst);
    }
    public void actionPerformed(ActionEvent event)
    {
        String distanceInput;
        double distance;

        distanceInput = dField.getText();

        distance = Double.parseDouble(distanceInput);

        kmField.setText(String.format("%.2f", distance * 1.60934));
        mField.setText(String.format("%.2f", distance * 1.60934 * 1000));
        fField.setText(String.format("%.2f", distance * 5279.98687656));
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
