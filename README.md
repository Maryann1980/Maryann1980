Converting numbers to words and words to number

using System;

namespace NumberConverter
{
    internal class Program


    {
        static void Main(string[] args)
        {
            Console.WriteLine("Number and Word Converter");
            while (true)
            {
                Console.WriteLine("\nChoose an option:");
                Console.WriteLine("1. Number to Words");
                Console.WriteLine("2. Words to Number");
                Console.WriteLine("3. Finish");

                string choice = Console.ReadLine();

                switch (choice)
                {
                    case "1":
                        ConvertNumberToWords();
                        break;

                    case "2":
                        ConvertWordsToNumber();
                        break;

                    case "3":
                        Console.WriteLine("Finishing the program!");
                        return;

                    default:
                        Console.WriteLine("Invalid option. Please choose again.");
                        break;
                }
            }
        }

        // Function to convert a number to words
        static void ConvertNumberToWords()
        {
            Console.Write("Enter a number: ");
            string input = Console.ReadLine();

            if (int.TryParse(input, out int number))
            {
                string words = NumberToWords(number);
                Console.WriteLine($"Words: {words}");
            }
            else
            {
                Console.WriteLine("Invalid input. Please enter a valid number.");
            }
        }

        // Function to convert words to a number
        static void ConvertWordsToNumber()
        {
            Console.Write("Enter words: ");
            string words = Console.ReadLine();

            int number = WordsToNumber(words);
            Console.WriteLine($"Number: {number}");
        }

        // Function to convert a number to words
        static string NumberToWords(int number)
        {
            // Add logic here to convert the number to words
            // For simplicity, let's consider only positive integers within the range of 0 to 999
            // You can extend this logic for a wider range and include negative numbers if needed

            // Placeholder logic - replace with your implementation
            string[] units = { "Zero", "One", "Two", "Three", "Four", "Five", "Six", "Seven", "Eight", "Nine" };
            string[] teens = { "", "Eleven", "Twelve", "Thirteen", "Fourteen", "Fifteen", "Sixteen", "Seventeen", "Eighteen", "Nineteen" };
            string[] tens = { "", "Ten", "Twenty", "Thirty", "Forty", "Fifty", "Sixty", "Seventy", "Eighty", "Ninety" };

            if (number >= 0 && number <= 9)
            {
                return units[number];
            }
            else if (number >= 11 && number <= 19)
            {
                return teens[number - 10];
            }
            else if (number >= 20 && number <= 99)
            {
                return $"{tens[number / 10]} {units[number % 10]}";
            }
            else if (number >= 100 && number <= 999)
            {
                return $"{units[number / 100]} Hundred {NumberToWords(number % 100)}";
            }
            else
            {
                return "Number out of range";
            }
        }

        // Function to convert words to a number
        static int WordsToNumber(string words)
        {
            switch (words.ToLower())
            {
                case "zero":
                    return 0;

                case "one":
                    return 1;

                case "two":
                    return 2;

                case "three":
                    return 3;

                case "four":
                    return 4;

                case "five":
                    return 5;

                case "six":
                    return 6;

                case "seven":
                    return 7;

                case "eight":
                    return 8;

                case "nine":
                    return 9;

                case "ten":
                    return 10;

                // Add more cases for other numbers

                default:
                    return 408; // no number found
            }
        }
    }
}

<!---
Maryann1980/Maryann1980 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
