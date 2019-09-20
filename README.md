# -Algo-TargetSum
Given a list of n sorted distinct integers, find integers k and m whose sum is q.

```
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


ACM VERSION




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
            return false;
        }
        static void Main(string[] args)
        {
            List<int> numbers = new List<int>();
            List<string> str = new List<string>();
            string s = Console.ReadLine();
            str = s.Split(' ').ToList();
            numbers = str.Select(int.Parse).ToList();
            Console.WriteLine(" ");
            int sum = Convert.ToInt32(Console.ReadLine());
            if(!TargetSum(numbers.Count, sum, numbers))
            {
                Console.WriteLine("None.");
            }
            Console.ReadLine();
        }
    }
}




Knapsack


using System;
using System.Collections;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Knapsack
{
    class Program
    {
        public static bool Knapsack(int n, int sum, List<int> numbers)
        {
            int current_index = 0;
            //Algorithm -1 0 2 5 8 12 22 31
            for (int k = 0; k <= n - 1; k++)
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
                        Console.WriteLine(numbers[k] + " + " + numbers[m - 1] + " is " + sum);
                        return true;
                    }
                    current_index = numbers[k] + numbers[m];
                }
            }
            return false;
        }
        static void Main(string[] args)
        {
            int auto = 1;
            List<int> numbers = new List<int>();
            List<string> str = new List<string>();
            List<string> parsed = new List<string>();
            Dictionary<int, Tuple<int,int>> Items = new Dictionary<int, Tuple<int, int>>();
            Console.WriteLine(" ");

            Console.WriteLine("What is the maximum load? (W): ");
            Console.WriteLine("How many items? (N): ");
            Console.WriteLine("Type a continuous string with items seperated by commas and item-values seperated by a colon.");
            Console.WriteLine("Hit enter when you are done.");
            string s = Console.ReadLine();
            str = s.Split(',').ToList();
            for (int i = 0; i <= str.Count; i++)
            {
                Tuple<int, int> keynvalue;
                
                keynvalue = new Tuple<int, int>(Convert.ToInt32(str[i].Split(':').First()), Convert.ToInt32(str[i].Split(':').Last()));
                Items.Add(auto, keynvalue);
                auto++;
            }
            numbers = str.Select(int.Parse).ToList();
            int sum = Convert.ToInt32(Console.ReadLine());
            if (!Knapsack(numbers.Count, sum, numbers))
            {
                Console.WriteLine("None.");
            }
            Console.ReadLine();
        }
    }
}

```

