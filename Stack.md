## C#實現堆疊

stack類別

**備註**:
1. data[++top] => 先執行top+1，後執行data[top]
2. data[top--] => 先執行data[top]，後執行top-1
```c#
 public class stack
    {
        public int top = -1;
        public int[] data = new int[5];

        //push
        public void push(int num) {
            if (top < 5) {
                data[++top] = num;
            }
        }

        //pop
        public int pop() {
            if(top != -1) {
                int tmp = data[top--];
                return tmp;
            }
            else{ return -1; }
            
        }

        //檢查堆疊是否為空
        public bool isEmpty() {
            if (top == -1) { return true; }
            else return false;
        }
    }
```

BUTTON => push
```c#
private void Button_Click(object sender, RoutedEventArgs e)
        {
            int[] numArray ={Convert.ToInt32(txt1.Text),
                Convert.ToInt32(txt2.Text),
                Convert.ToInt32(txt3.Text),
                Convert.ToInt32(txt4.Text),
                Convert.ToInt32(txt5.Text)};

            for (int i = 0; i < numArray.Length; i++) {
                st1.push(numArray[i]);
            }
            MessageBox.Show("Sucessful", "hint", MessageBoxButton.OK);
        }
```

BUTTON => pop
```c#
private void Button_Click_1(object sender, RoutedEventArgs e)
        {
            while (!st1.isEmpty()) {
                txtOuput.Text += Convert.ToString(st1.pop()) + "\r\n";
            }
        }
```