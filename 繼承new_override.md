## 繼承 new / override

```c#
public class TextLine{
    
    public string GetWord(){
        return "這是父類別的GetWord方法";
    }
    
    public virtual string GetText(){
            return "這是父類別的GetText方法";
    }
}

public class MyLine : TextLine {

    public new string GetWord() {
        return "這是子類別的GetWord方法";
    }

    public override string GetText() {
        return "這是子類別的GetText方法";
    }
}

static void Main(string[] args){

    MyLine m1 = new MyLine();

    Console.WriteLine(m1.GetWord());
    Console.WriteLine(m1.GetText());

    Console.ReadKey();
}
```


