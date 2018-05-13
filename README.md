/*
Problem: There would be some string/brackets to given and we need to decide whether it's symmetric or not.
*/

# BracketController
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;

namespace ConsoleApplication1
{
    class Program
    {
        static bool solution(string brackets)
        {
            bool result = false;
            int lastChar = 0;
            int firstChar = 0;
            int flag = 0;          
          
                char[] characters = new char[brackets.Length];
                for (int i = 0; i < brackets.Length; i++)
                {
                    characters[i] = brackets[i];
                    Console.WriteLine(characters[i].ToString());
                }

                lastChar = brackets.Length-1;

                for (int i = 1; i <= (brackets.Length / 2); i++)
                {
                    if (characters[firstChar] == characters[lastChar])
                    {
                        firstChar++;
                        lastChar--;
                        flag++;
                    }
                }

                if (flag >= brackets.Length / 2)
                {
                    result = true;
                }

            return result;
        }
        static void Main(string[] args)
        {
            string arg0 = Console.ReadLine();
            var returnVal = solution(arg0);
            Console.WriteLine(returnVal == true ? "true" : "false");
            Console.ReadLine();
        }
    }

}
