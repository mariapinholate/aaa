int d, m, a;
int diasNoMes;

while (true)
{
    Console.WriteLine("Digite o dia de nascimento:");
    d = int.Parse(Console.ReadLine());

    Console.WriteLine("Digite o mês de nascimento:");
    m = int.Parse(Console.ReadLine());

    Console.WriteLine("Digite o ano de nascimento:");
    a = int.Parse(Console.ReadLine());

    if (a < 1906 || a > 2026)
    {
        Console.WriteLine("Ano inválido! Digite um ano entre 1906 e 2026.");
        continue;
    }

    if (m < 1 || m > 12)
    {
        Console.WriteLine("Mês inválido! Digite um mês entre 1 e 12.");
        continue;
    }

    switch (m)
    {
        case 1:
            diasNoMes = 31;
            break;

        case 2:
            if (a % 400 == 0 || (a % 4 == 0 && a % 100 != 0))
                diasNoMes = 29;
            else
                diasNoMes = 28;
            break;

        case 3:
            diasNoMes = 31;
            break;

        case 4:
            diasNoMes = 30;
            break;

        case 5:
            diasNoMes = 31;
            break;

        case 6:
            diasNoMes = 30;
            break;

        case 7:
            diasNoMes = 31;
            break;

        case 8:
            diasNoMes = 31;
            break;

        case 9:
            diasNoMes = 30;
            break;

        case 10:
            diasNoMes = 31;
            break;

        case 11:
            diasNoMes = 30;
            break;

        default:
            diasNoMes = 31;
            break;
    }

    if (d < 1 || d > diasNoMes)
    {
        Console.WriteLine("Dia inválido para o mês informado.");
        continue;
    }

    if (a == 2026 && (m > 8 || (m == 8 && d > 10)))
    {
        Console.WriteLine("Data inválida! A data não pode ser maior que 10/08/2026.");
        continue;
    }

    if (a == 1906 && (m < 8 || (m == 8 && d < 10)))
    {
        Console.WriteLine("Data inválida! A idade seria maior que 120 anos.");
        continue;
    }

    Console.WriteLine($"Data de nascimento válida: {d}/{m}/{a}");
    break;
}
