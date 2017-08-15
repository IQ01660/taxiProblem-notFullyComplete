# taxiProblem-notFullyComplete
``` C#
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace taxiProblem_15._08._2017
{
    class Program
    {
        static void Main(string[] args)
        {   // checking taxi
            double minDist = 100000000;
            Taxi first = new Taxi(4, 3);
            if(first.distance < minDist)
            {
                minDist = first.distance;
            }
            Taxi second = new Taxi(8, 3);
            if (second.distance < minDist)
            {
                minDist = second.distance;
            }
            Taxi someTaxi = new Taxi(10, 1);
            if (someTaxi.distance < minDist)
            {
                minDist = someTaxi.distance;
            }
            Taxi third = new Taxi(2,4);
            if (third.distance < minDist)
            {
                minDist = third.distance;
            }
            var ikram = new Customer(0, 0);
            
            Console.WriteLine("The nearest taxi is {0} m away it will cost you {1} $", ikram.CallTaxi(minDist),3*ikram.CallTaxi(minDist)/10);
           
        }
    }
    class Taxi
    {
        public int xCoorTaxi;
        public int yCoorTaxi;
        public double distance;
        public Taxi(int _xTaxi, int _yTaxi)
        {
            this.xCoorTaxi = _xTaxi;
            this.yCoorTaxi = _yTaxi;
            this.distance = this.EstimateDistance();
        }
        public double EstimateDistance()
        {
            var ikram = new Customer(0,0);
            
            return Math.Floor(Math.Sqrt(((this.xCoorTaxi-ikram.xCoorCust) * (this.xCoorTaxi - ikram.xCoorCust)) + ((this.yCoorTaxi - ikram.yCoorCust) * (this.yCoorTaxi - ikram.yCoorCust))));
        }
    }
    class Customer
    {
        public int xCoorCust;
        public int yCoorCust;
        
        public Customer(int _xCust, int _yCust)
        {
            this.xCoorCust = _xCust;
            this.yCoorCust = _yCust;
        }
        public double CallTaxi(double _mindist)
        {
            return _mindist;
        }
    }
}

```
