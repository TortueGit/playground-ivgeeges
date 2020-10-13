# Welcome!

This C# template lets you get started quickly with a simple one-page playground.

```C# runnable
using System;

class Hello 
{
    static void Main() 
    {
        Tuple<int, int> pos1 = new Tuple<int, int>(1, 1);
        Tuple<int, int> pos2 = new Tuple<int, int>(1, 1);
        int mvmt = 1000;

        Tools.PrintMove(Tools.MoveToPosition(pos1, pos2, mvmt));
    }
}

static class Tools
{
    public static float GetDistance(Tuple<int, int> pos1, Tuple<int, int> pos2)
    {
        double distance;
        var distX = 0;
        var distY = 0;

        distX = pos1.Item1 - pos2.Item1;
        distY = pos1.Item2 - pos2.Item2;

        distance = Math.Sqrt(Math.Pow(distX, 2) + Math.Pow(distY, 2));

        return (float)distance;
    }

    public static Tuple<int, int> MoveToPosition(Tuple<int, int> posStart, Tuple<int, int> posEnd, int mouvement)
    {
        float distance = Tools.GetDistance(posStart, posEnd);
        float t = mouvement / distance;
        return new Tuple<int, int>(
                (int)Math.Floor(posStart.Item1 + (t * (posEnd.Item1 - posStart.Item1))),
                (int)Math.Floor(posStart.Item2 + (t * (posEnd.Item2 - posStart.Item2)))
            );
    }
    
    public static void PrintMove(Tuple<int, int> move)
    {
        Console.WriteLine($"{move.Item1} {move.Item2}");
    }
}
```

# Advanced usage

If you want a more complex example (external libraries, viewers...), use the [Advanced C# template](https://tech.io/select-repo/386)
