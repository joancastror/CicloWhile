programación bucles while
1)	Confeccionar un programa que, a partir de una secuencia de 10 números enteros, calcule y muestre la suma y el promedio aritmético de dichos números.

1)	namespace SumaYPromedioWhile
2)	{
3)	public class Calculadora
4)	{
5)	public void CalcularSumaYPromedio()
6)	{
7)	int suma = 0;
8)	int contador = 0;
9)	int numero;

10)	try
11)	{
12)	// Usar un bucle while para pedir 10 números
13)	while (contador < 10)
14)	{
15)	Console.WriteLine($"Ingrese el número {contador + 1}:");
16)	string entrada = Console.ReadLine();

17)	if (string.IsNullOrEmpty(entrada))
18)	{
19)	Console.WriteLine("El número es requerido.");
20)	return;
21)	}

22)	if (!int.TryParse(entrada, out numero))
23)	{
24)	Console.WriteLine("Entrada inválida, ingrese un número entero.");
25)	return;
26)	}

27)	suma += numero;
28)	contador++;
29)	}

30)	// Calcular el promedio aritmético
31)	double promedio = (double)suma / contador;

32)	// Mostrar la suma y el promedio
33)	Console.WriteLine($"\nLa suma de los 10 números es: {suma}");
34)	Console.WriteLine($"El promedio aritmético es: {promedio:F2}");
35)	}
36)	catch (Exception ex)
37)	{
38)	Console.WriteLine($"Ocurrió un error: {ex.Message}");
39)	}
40)	}
41)	}

42)	class Program
43)	{
44)	static void Main(string[] args)
45)	{
46)	Calculadora calculadora = new Calculadora();
47)	calculadora.CalcularSumaYPromedio();
48)	}
49)	}
50)	}


 

2) Crear un programa que cuente cuántas piezas de hierro de un lote, dentro de un rango específico de longitud, son aptas para fabricar perfiles.

namespace ControlDePiezas
{
    public class ControlPiezas
    {
        public void ContarPiezasAptas()
        {
            int totalPiezas = 0;
            int piezasAptas = 0;
            double longitudMinima = 0;
            double longitudMaxima = 0;
            double longitudPieza = 0;
            int contador = 0;

            try
            {
                // Solicitar el número total de piezas en el lote
                Console.WriteLine("Ingrese el número total de piezas en el lote:");
                if (!int.TryParse(Console.ReadLine(), out totalPiezas) || totalPiezas <= 0)
                {
                    Console.WriteLine("Número total de piezas inválido.");
                    return;
                }

                // Solicitar la longitud mínima y máxima del rango aceptable
                Console.WriteLine("Ingrese la longitud mínima aceptable:");
                if (!double.TryParse(Console.ReadLine(), out longitudMinima) || longitudMinima < 0)
                {
                    Console.WriteLine("Longitud mínima inválida.");
                    return;
                }

                Console.WriteLine("Ingrese la longitud máxima aceptable:");
                if (!double.TryParse(Console.ReadLine(), out longitudMaxima) || longitudMaxima < longitudMinima)
                {
                    Console.WriteLine("Longitud máxima inválida.");
                    return;
                }

                // Contar cuántas piezas están dentro del rango aceptable
                while (contador < totalPiezas)
                {
                    Console.WriteLine($"Ingrese la longitud de la pieza {contador + 1}:");
                    if (!double.TryParse(Console.ReadLine(), out longitudPieza) || longitudPieza < 0)
                    {
                        Console.WriteLine("Longitud de pieza inválida.");
                        return;
                    }

                    if (longitudPieza >= longitudMinima && longitudPieza <= longitudMaxima)
                    {
                        piezasAptas++;
                    }

                    contador++;
                }

                // Mostrar el resultado
                Console.WriteLine($"\nDe {totalPiezas} piezas en el lote, {piezasAptas} son aptas para fabricar perfiles.");
            }
            catch (Exception ex)
            {
                Console.WriteLine($"Ocurrió un error: {ex.Message}");
            }
        }
    }

    class Program
    {
        static void Main(string[] args)
        {
            ControlPiezas controlPiezas = new ControlPiezas();
            controlPiezas.ContarPiezasAptas();
        }
    }
}
 
