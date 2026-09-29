using System; using System.Collections.Generic;

class Program { static void Main() { Dictionary<int, string> telebeler = new Dictionary<int, string>();

    telebeler.Add(1, "Ferda");
    telebeler.Add(2, "Amin");
    telebeler.Add(3, "Gulsum");
    telebeler.Add(4, "Nigar");
    telebeler.Add(5, "Ayten");

    int secim = 0;

    while (secim != 4)
    {
        Console.WriteLine("\n--- Telebe Qeydiyyat Sistemi ---");
        Console.WriteLine("1. Telebe elave et");
        Console.WriteLine("2. Telebeni ID ile axtar");
        Console.WriteLine("3. Butun telebeleri goster");
        Console.WriteLine("4. Cixis");
        Console.Write("Seciminizi daxil edin: ");

        secim = int.Parse(Console.ReadLine());

        switch (secim)
        {
            case 1:
                Console.Write("Telebe ID-si: ");
                int id = int.Parse(Console.ReadLine());

                Console.Write("Telebenin adi: ");
                string ad = Console.ReadLine();

                telebeler.Add(id, ad);

                Console.WriteLine("Telebe elave edildi.");
                break;

            case 2:
                Console.Write("Axtarilan telebenin ID-si: ");
                int axtarisId = int.Parse(Console.ReadLine());

                if (telebeler.ContainsKey(axtarisId))
                {
                    Console.WriteLine("Telebe: " + telebeler[axtarisId]);
                }
                else
                {
                    Console.WriteLine("Bu ID ile telebe tapilmadi.");
                }
                break;

            case 3:
                Console.WriteLine("\nButun telebeler:");

                foreach (var telebe in telebeler)
                {
                    Console.WriteLine("ID: " + telebe.Key + " - Ad: " + telebe.Value);
                }
                break;

            case 4:
                Console.WriteLine("Programdan cixilir...");
                break;

            default:
                Console.WriteLine("Yanlis secim!");
                break;
        }
    }
}
}
