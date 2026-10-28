4.using in, out, ref, params, and parameters by default values,
    * Ստեղծել static A(), B(), C() մեթոդները, համապատասխանաբար in, out, ref, մոդֆիկատորները փորձարկելու համար  
    * Ստեղծել նաև SumValues(parasm … ) մեթոդը որը կգումարի մուտքում եկած ամբողջ թվերը, թվերի քանակը ֆիքսված չէ
    * ցույց տալ թե ինչպես են աշխատում այս մեթոդները, Main() մեթոդում
```
using System;

class Program
{
    static void A(in int x)
    {
        Console.WriteLine(x);
    }

    static void B(out int x)
    {
        x = 10;
    }

    static void C(ref int x)
    {
        x += 5;
    }

    static int SumValues(params int[] numbers)
    {
        int sum = 0;
        foreach (var n in numbers)
        {
            sum += n;
        }
        return sum;
    }

    static void Main()
    {
        int a = 2;
        A(in a);

        int b;
        B(out b);

        int c = 10;
        C(ref c);

        int total = SumValues(1, 2, 3, 4);
        Console.WriteLine(total);
    }
}
