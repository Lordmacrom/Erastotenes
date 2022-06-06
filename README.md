# Erastotenes

﻿using System;

public class Program
{
    public static void Main()
    { 
        bool[] liczby = new bool[1000001];
        int i, n = 0, j;

        for(i = 2; i < 1000001; i++)
        {
            liczby[i] = true;
        }

        for(i = 2; i < 1000; i++)
        {

            if (liczby[i] == true)
            {
                for (j = i+1; j < 1000001; j++)
                {
                    if (j % i == 0)
                    {
                        liczby[j] = false;
                    }
                }
            }
        }
        for (i = 2; i < 1000001; i++)
        {
            if(liczby[i])
            {
                Console.WriteLine(i);
                n++;
            }
        }
        Console.WriteLine("Znaleziono {0} liczb pierwszych do 1 000 000", n);
    }
}
