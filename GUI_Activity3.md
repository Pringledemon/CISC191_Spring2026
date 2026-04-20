```java
import java.awt.GridBagConstraints;
import java.awt.GridBagLayout;
import java.awt.Insets;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JTextField;
import javax.swing.JSpinner;
import javax.swing.SpinnerNumberModel;
import javax.swing.event.ChangeEvent;
import javax.swing.event.ChangeListener;

public class Main extends JFrame implements ChangeListener
{
    private JLabel dLabel;
    private JLabel kmLabel;
    private JSpinner dField;
    private JTextField kmField;

    Main()
    {
        double intDistance = 0;
        double minDistance = 0;
        double maxDistance = 1000;
        double stepVal = 1;

        GridBagConstraints layoutConst = null;
        SpinnerNumberModel spinnerModel = null;

        setTitle("Distance");

        dLabel = new JLabel("Distance(Miles):");
        kmLabel = new JLabel("Distance(Kilometers):");

        spinnerModel = new SpinnerNumberModel(intDistance, minDistance, maxDistance, stepVal);
        dField = new JSpinner(spinnerModel);
        dField.addChangeListener(this);

        kmField = new JTextField(15);
        kmField.setEditable(false);

        setLayout(new GridBagLayout());

        layoutConst = new GridBagConstraints();
        layoutConst.gridx = 0;
        layoutConst.gridy = 0;
        layoutConst.insets = new Insets(10, 10, 10, 10);
        add(dLabel, layoutConst);

        layoutConst = new GridBagConstraints();
        layoutConst.gridx = 1;
        layoutConst.gridy = 0;
        layoutConst.fill = GridBagConstraints.HORIZONTAL;
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
    }
    public void stateChanged(ChangeEvent event)
    {
        double distance;

        distance = (Double) dField.getValue();

        kmField.setText(String.format("%.2f", distance * 1.60934));
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
