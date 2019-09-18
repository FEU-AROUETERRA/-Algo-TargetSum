# -Algo-TargetSum
Given a list of n sorted distinct integers, find integers k and m whose sum is q.


using System;
using System.Collections;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace TargetSum
{
    class Program
    {
        public static bool TargetSum(int n, int sum, List<int> numbers)
        {
            int current_index = 0;
            //Algorithm -1 0 2 5 8 12 22 31
            for (int k = 0; k <= n-1; k++)
            {
                current_index = numbers[k];
                for (int m = k + 1; m < n; m++)
                {
                    if ((numbers[k] == numbers[m]))
                    {
                        //skip duplicates
                        continue;
                    }
                    if (current_index == sum)
                    {
                        Console.WriteLine("Found Target Addends at index: " + k + " and " + (m - 1));
                        Console.WriteLine(numbers[k] + " + " + numbers[m-1] + " is " + sum);
                        return true;
                    }
                    current_index = numbers[k] + numbers[m];
                }
            }
            Console.WriteLine("No valid addends!");
            return false;
        }
        static void Main(string[] args)
        {
            //initialize
            Console.WriteLine("Input limit: ");
            int n = Convert.ToInt32(Console.ReadLine());
            List<int> numbers = new List<int>();
            Console.WriteLine("Input n numbers: ");
            //input n
            for (int i = 0; i < n; i++)
            {
                numbers.Add(Convert.ToInt32(Console.ReadLine()));
            }
            //input target
            Console.WriteLine("Input target: ");
            int sum = Convert.ToInt32(Console.ReadLine());
            if(!TargetSum(n, sum, numbers))
            {
                Console.WriteLine("None.");
            }
            Console.ReadLine();
        }
    }
}
