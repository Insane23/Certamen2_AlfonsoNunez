# Certamen2_AlfonsoNunez
--Adjunto Codigo Principal "Main" del proyecto--

using System;

namespace Certamen2_TLP_AlfonsoNuñez
{
    class Program
    {
        static void Main(string[] args)
        {
            int[] numero = new int[5];
            int valor, contador = 1;

            String[,] matriz1 = new string[10, 10];
            int size1 = matriz1.GetLength(0), size2 = matriz1.GetLength(1);


            ////////////////////// Ejercicio 1 \\\\\\\\\\\\\\\\\\\\\\\\\
            for (int i = 0; i < 5; i++)
            {
                Console.WriteLine("Ingrese valor del " + contador + "° número");
                numero[i] = int.Parse(Console.ReadLine());
                contador++;
            }
            Console.Clear();

            Console.WriteLine("Ingrese un valor a calcular");
            valor = int.Parse(Console.ReadLine());
            Console.Clear();
            Console.WriteLine("Valor: " + valor + "\nMayores al valor:");
            for (int i = 0; i < 5; i++)
            {
                if (numero[i] > valor)
                {
                    Console.Write(numero[i] + "\t");
                }
                contador++;
            }
            Console.ReadKey();
            Console.Clear();

            ///////////////////// Ejercicio 2 \\\\\\\\\\\\\\\\\\\\\\\\


            for (int i = 0; i < matriz1.GetLength(0); i++)
            {
                for (int j = 0; j < matriz1.GetLength(1); j++)
                {
                    if (i == size1 / 2 || i == size1/2-1 || j == size2/2 || j == size2/2-1)
                    {
                        matriz1[i, j] = "1";
                    }
                    else
                    {
                        matriz1[i, j] = "0";
                    }
                }
            }
            imprimir(matriz1);
            Console.WriteLine();
            Console.WriteLine("EJERCICIOS REALIZADOS CON EXITO !!!");
            Console.Write("PRESIONE CUALQUIER TECLA PARA TERMINAR");
            Console.ReadKey();

            static void imprimir(string[,] matriz1)
            {
                for (int i = 0; i < matriz1.GetLength(0); i++)
                {
                    for (int j   = 0; j < matriz1.GetLength(0); j++)
                    {
                        Console.Write(matriz1[i, j] +" ");
                    }
                    Console.WriteLine();
                }
            }

            ////////////////////// Ejercicio 3 \\\\\\\\\\\\\\\\\\\\\\\\
            int[] numeros = new int[10];

            Random rand = new Random();
            int aleatorio, n = 0, n1 = 0, n2 = 0, cont = 0;
            for (int i = 0; i < 10; i++)
            {
                aleatorio = rand.Next(50, 200);
                n = 0;
                while (n < i)
                {
                    if (aleatorio == numeros[n])
                    {
                        aleatorio = rand.Next(50, 200);
                        n = 0;
                    }
                    else
                    {
                        n++;
                    }
                }
                if (i == 0)
                {
                    n1 = aleatorio;
                    n2 = aleatorio;
                }
                if (aleatorio > n1)
                {
                    n1 = aleatorio;
                }
                if (aleatorio < n2)
                {
                    n2 = aleatorio;
                }
                numeros[i] = aleatorio;

                cont++;
            }
            for (int i = 0; i < 10; i++)
            {
                Console.Write(numeros[i] + "\t");
            }
            Console.Write("\nEl numero mayor es: " + n1);
            Console.WriteLine("\nEl numero menor es: " + n2);
            Console.ReadKey();
            Console.Clear();
        }
    }
}
