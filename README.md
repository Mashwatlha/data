using System;
using System.Windows.Forms;

namespace DataEntryApp
{
    public partial class MainForm : Form
    {
        // Declare UI controls
        private Label nameLabel;
        private TextBox nameTextBox;
        private Label ageLabel;
        private NumericUpDown ageNumericUpDown;
        private Button submitButton;

        public MainForm()
        {
            InitializeComponent();
        }

        private void InitializeComponent()
        {
            // Initialize UI controls
            nameLabel = new Label();
            nameLabel.Text = "Name:";
            nameLabel.Location = new System.Drawing.Point(10, 10);

            nameTextBox = new TextBox();
            nameTextBox.Location = new System.Drawing.Point(70, 10);

            ageLabel = new Label();
            ageLabel.Text = "Age:";
            ageLabel.Location = new System.Drawing.Point(10, 40);

            ageNumericUpDown = new NumericUpDown();
            ageNumericUpDown.Location = new System.Drawing.Point(70, 40);

            submitButton = new Button();
            submitButton.Text = "Submit";
            submitButton.Location = new System.Drawing.Point(10, 70);
            submitButton.Click += SubmitButton_Click;

            // Set up the main form
            Text = "Data Entry";
            AutoSize = true;
            Controls.Add(nameLabel);
            Controls.Add(nameTextBox);
            Controls.Add(ageLabel);
            Controls.Add(ageNumericUpDown);
            Controls.Add(submitButton);
        }

        private void SubmitButton_Click(object sender, EventArgs e)
        {
            string name = nameTextBox.Text;
            int age = (int)ageNumericUpDown.Value;

            // Process the entered data here, e.g., store it in a database or display it

            MessageBox.Show($"Name: {name}\nAge: {age}", "Data Submitted");
        }

        [STAThread]
        static void Main()
        {
            Application.EnableVisualStyles();
            Application.Run(new MainForm());
        }
    }
}
