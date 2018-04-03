## 繼承 new / override

```c#
public class TextLine{

    public string text;
    
    //建構子
    public TextLine(string text) {
        this.text = text;
    }

    public string GetWord() {...}
    public virtual string GetText() {...}
}

public class MyLine : TextLine {

    //隱藏方法
    public new string GetWord() {...}

    //複寫方法，須對應父類別visual函數
    public override string GetText() {...}
}
```


