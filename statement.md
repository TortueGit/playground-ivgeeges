# Welcome!

This C# template lets you get started quickly with a simple one-page playground.

```C# runnable
using System;

class Hello 
{
    static void Main() 
    {
        Console.WriteLine("Hello World!");
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

    public static void PrintMove(Tuple<int, int> move)
    {
        Console.WriteLine($"{move.Item1} {move.Item2}");
    }
}
```

# Advanced usage

If you want a more complex example (external libraries, viewers...), use the [Advanced C# template](https://tech.io/select-repo/386)
