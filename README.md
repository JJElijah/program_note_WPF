## 動態新增按鈕

```c#
public partial class MainWindow : Window
    {
        Button[] b_arr = new Button[16];

        public MainWindow()
        {
            InitializeComponent();

            /初始化BUTTON陣列
            for (int i = 0; i < b_arr.Length; i++) {
                Button empty = new Button();
                empty.Name = "empty"+Convert.ToString(i);//設定陣列內按鈕名稱
                b_arr[i] = empty;
            }
        }

        public Button setbutton(Button bt,int height,int width,String name,String content) {
            bt.Height = height;
            bt.Width = width;
            bt.Name = name;
            bt.Content = content;
            return bt;
        }

        private void bt_add_Click(object sender, RoutedEventArgs e)
        {
            Button b1 = new Button();
            
            b1.VerticalAlignment = VerticalAlignment.Top;
            b1.HorizontalAlignment = HorizontalAlignment.Left;

            //新增按鈕，存進陣列
            for (int i = 0; i < b_arr.Length; i++) {
                if (b_arr[i].Name=="empty"+Convert.ToString(i)) {
                    b1 = setbutton(b1,100,100, "bt" + Convert.ToString(i), "按鈕" + (i + 1));
                    b1.Click += new RoutedEventHandler(remove);//按鈕事件=>移除按鈕
                    b_arr[i] = b1;
                    b1.Margin = new Thickness(35 + 115 * (i % 4), 130 + 120 * (i / 4), 0, 0);
                    break;
                }
            }
            gr1.Children.Add(b1);//將按鈕加進GRID
        }


        private void remove(object sender, RoutedEventArgs e) {

            Button b2 = (Button)sender;

            //將被移除的按鈕陣列位置還原
            for (int i = 0; i < b_arr.Length; i++) {
                if (b_arr[i].Name == b2.Name) {
                    b_arr[i].Name = "empty" + Convert.ToString(i);
                }
            }
            gr1.Children.Remove(((Button) sender));//Button sender表被移除的按鈕
        }
    }
}

```




