using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.IO;
using Display;

namespace Life
{
    class Program
    {
        /// <summary>
        /// Checks the parameters the user has input for the dimensions of the simulation
        /// </summary>
        /// <param name="args"></param>
        /// <param name="count"></param>
        /// <param name="Rows"></param>
        /// <param name="Columns"></param>
        /// <param name="CheckAllConditions"></param>
        static void CheckDimensions(ref string[] args, ref int count, ref int Rows ,
                                ref int Columns, ref bool CheckAllConditions )
        {
            
            if (args[count] == "--dimensions")
            {
                try
                {
                    if (int.Parse(args[count + 1]) >= 4 & int.Parse(args[count + 1]) <= 48)
                    {
                        Rows = int.Parse(args[count + 1]);
                    }
                    else
                    {
                        Console.WriteLine("Error in input for rows. Please enter a number between 4 and 48");
                        CheckAllConditions = false;
                    }

                    if (int.Parse(args[count + 2]) > 3 & int.Parse(args[count + 2]) < 49)
                    {
                        Columns = int.Parse(args[count + 2]);
                    }
                    else
                    {
                        Console.WriteLine("Error in input for columns. Please enter a number between 4 and 48");
                        CheckAllConditions = false;
                    }

                }
                catch
                {
                    Console.WriteLine("Error. Please enter numerical inputs");
                    CheckAllConditions = false;
                }
            }
        }

        /// <summary>
        /// Checks if the user has input if the simulation should behave periodically
        /// </summary>
        /// <param name="args"></param>
        /// <param name="count"></param>
        /// <param name="PeriodicBehaviour"></param>
        static void CheckPeriodic(ref string[] args, ref int count, ref bool PeriodicBehaviour)
        {
            
            if (args[count] == "--periodic")
            {
                PeriodicBehaviour = true;
            }
        }

        /// <summary>
        /// Checks the user input for the randomness of live cells in the simulation
        /// </summary>
        /// <param name="args"></param>
        /// <param name="count"></param>
        /// <param name="RandFactor"></param>
        /// <param name="CheckAllConditions"></param>
        static void CheckRandomFactor(ref string[] args, ref int count, ref double RandFactor,
                                                                    ref bool CheckAllConditions)
        {
            
            if (args[count] == "--random")
            {
                try
                {
                    if (double.Parse(args[count + 1]) >= 0 & double.Parse(args[count + 1]) <= 1)
                    {
                        RandFactor = double.Parse(args[count + 1]);
                    }
                    else
                    {
                       Console.WriteLine("Error in input. Please enter a value between 0 and 1 for the random factor");
                       CheckAllConditions = false;
                    }
                }
                catch
                {
                    Console.WriteLine("Error in input. Please enter a number as the random factor");
                    CheckAllConditions = false;
                }
            }
        }

        /// <summary>
        /// Checks the seed file given by the user.
        /// </summary>
        /// <param name="args"></param>
        /// <param name="count"></param>
        /// <param name="InputFile"></param>
        /// <param name="CheckAllConditions"></param>
        static void CheckSeedfile(ref string[] args, ref int count, ref string InputFile, ref bool CheckAllConditions)
        {
            
            if (args[count] == "--seed")
            {

                if (args[count + 1].EndsWith(".seed"))
                {
                    InputFile = args[count + 1];

                }
                else
                {
                    Console.WriteLine("The input needs to be a seed file. Please check again");
                    CheckAllConditions = false;
                }

            }
        }


        /// <summary>
        /// Checking the new seed files
        /// Get help from Godwin!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        /// </summary>
        static bool NewCheckSeedFile(ref int[,] GameArrray, ref bool CheckAllConditions, StreamReader streamReader)
        {
            string ReadFile = streamReader.ReadToEnd().Trim(); // To read the entire seed file

            string[] Lines = ReadFile.Split('\n');
            string[] ASplit = new string[Lines.Length];

            int[] XCoordinate = new int[Lines.Length];
            int[] YCoordinate = new int(Lines.Length);
            string[] CurrentState = new string[Lines.Length];
            int[] Height = new int[Lines.Length];
            int[] Width = new int[Lines.Length];



        }


        /// <summary>
        /// Checks if user has inputted parameters for number of generations in the simulation
        /// </summary>
        /// <param name="args"></param>
        /// <param name="count"></param>
        /// <param name="Generations"></param>
        /// <param name="CheckAllConditions"></param>
        static void GenerationMethod(ref string[] args, ref int count, ref int Generations,ref bool CheckAllConditions)
        {
            
            if (args[count] == "--generations")
            {
                try
                {
                    if (int.Parse(args[count + 1]) > 0)
                    {
                        Generations = int.Parse(args[count + 1]);
                    }
                    else
                    {
                        Console.WriteLine("Error in input. Please enter a non zero positive integer");
                        CheckAllConditions = false;
                    }
                }
                catch
                {
                    Console.WriteLine("Error in input please enter a number as the value for generations");
                    CheckAllConditions = false;
                }
            }
        }

        /// <summary>
        /// Checks the update rate given by the user.
        /// </summary>
        /// <param name="args"></param>
        /// <param name="count"></param>
        /// <param name="MaxUpdateRate"></param>
        /// <param name="CheckAllConditions"></param>
        static void MaxUpdaterate(ref string[] args,ref int count,ref double MaxUpdateRate,ref bool CheckAllConditions)
        {
            
            if (args[count] == "--max-update")
            {
                try
                {
                    if (double.Parse(args[count + 1]) >= 1 & double.Parse(args[count + 1]) <= 30)
                    {
                        MaxUpdateRate = double.Parse(args[count + 1]);
                    }
                    else
                    {
                        Console.WriteLine("Error in input. Please enter a number between 1 and 30");
                        CheckAllConditions = false;
                    }
                }
                catch
                {
                    Console.WriteLine("Error in input. Please enter a proper value for max update rate");
                    CheckAllConditions = false;
                }
            }
        }

        /// <summary>
        /// Checks if step mode needs to be enabled
        /// </summary>
        /// <param name="args"></param>
        /// <param name="count"></param>
        /// <param name="StepMode"></param>
        static void StepModeMethod(ref string[] args, ref int count, ref bool StepMode)
        {
            
            if (args[count] == "--step")
            {
                StepMode = true;
            }
        }

        /// <summary>
        /// Allocates seed file into array and checks the seed file. Unless
        /// coordinate size is oo big or file doesnt existi that case random assigning is done.
        /// </summary>
        /// <param name="InputFile"></param>
        /// <param name="Columns"></param>
        /// <param name="Rows"></param>
        /// <param name="GameArray"></param>
        /// <param name="RandFactor"></param>
        static void RandomnessMethod(ref string InputFile, ref int Columns, ref int Rows, 
            ref int[,] GameArray, ref double RandFactor)
        {
            if (InputFile != "")
            {
                StreamReader Streamreader;
                string StreamValue = "";

                try
                {
                    Streamreader = new StreamReader(InputFile);
                    Streamreader.ReadLine();
                    StreamValue = Streamreader.ReadToEnd();
                }
                catch
                {
                    Console.WriteLine("File doenst exist. Please check");
                }


                string[] Contents = StreamValue.Split("\n");

                int rowsMax = 0;

                int columnsMax = 0;

                List<int> rowsList = new List<int>();

                List<int> columnsList = new List<int>();

                bool ExceedSize = false;

                for (int index = 0; index < Contents.Length - 1; index++)
                {
                    columnsList.Add(int.Parse(Contents[index].Split(' ')[1]));

                    rowsList.Add(int.Parse(Contents[index].Split(' ')[0]));

                    if (columnsList[index] > Columns && columnsList[index] > columnsMax)
                    {
                        //ExceedSize = true;

                        columnsMax = columnsList[index];
                    }

                    if (rowsList[index] > Rows && rowsList[index] > rowsMax)
                    {
                        //ExceedSize = true;

                        rowsMax = rowsList[index];
                    }


                }
                for (int itera = 0; itera < rowsList.Count; ++itera)
                {
                    GameArray[rowsList[itera], columnsList[itera]] = 1;

                }

                if (ExceedSize)
                {
                    Console.WriteLine("The size of it is to big. " +
                        "The appropriate values are {0}, {1}", rowsMax, columnsMax);
                }

                else
                {

                }

            }
            else
            {
                Random random = new Random();
                int R = 0;

                for (int i = 0; i < Rows; i++)
                {
                    for (int j = 0; j < Columns; j++)
                    {
                        R = random.Next(0, 100);
                        if (R < RandFactor * 100)
                        {
                            GameArray[i, j] = 1;

                        }
                    }

                }

            }
        }

        /// <summary>
        /// Contains the code displayed before simulation is started. This contains the inputs of the user
        /// </summary>
        /// <param name="CheckAllConditions"></param>
        /// <param name="InputFile"></param>
        /// <param name="Generations"></param>
        /// <param name="MaxUpdateRate"></param>
        /// <param name="PeriodicBehaviour"></param>
        /// <param name="Rows"></param>
        /// <param name="Columns"></param>
        /// <param name="StepMode"></param>
        /// <param name="RandFactor"></param>
        static void DispUserInput(ref bool CheckAllConditions, ref string InputFile, ref int Generations, 
            ref double MaxUpdateRate, ref bool PeriodicBehaviour, ref int Rows,
            ref int Columns, ref bool StepMode, ref double RandFactor)
        {
            if (CheckAllConditions == true)
            {
                Console.ForegroundColor = ConsoleColor.Green;
                Console.WriteLine("Success: Command line arguments processed.");
                Console.ForegroundColor = ConsoleColor.White;
            }
            else if (CheckAllConditions == false)
            {
                Console.WriteLine("Failed: One or more command line argments failed to " +
                    "implement therefore code will use the default values.");
            }
            Console.WriteLine("The program will use the following settings:\n");

            if (InputFile == "")
            {
                Console.WriteLine(String.Format("{0, 20} {1, -15}", "InputFile:", "N/A"));
            }
            else
            {
                Console.WriteLine(String.Format("{0,20} {1,-15}", "Input File:", InputFile));
            }

            Console.WriteLine(String.Format("{0, 20} {1, -15}", "Generations:", Generations));
            Console.WriteLine(String.Format("{0, 20} {1, -15}", "Refresh Rate:", MaxUpdateRate + " updates/s"));

            if (PeriodicBehaviour == true)
            {
                Console.WriteLine(String.Format("{0, 20} {1, -15}", "Periodic:","Yes"));
            }
            else
            {
                Console.WriteLine(String.Format("{0, 20} {1, -15}", "Periodic:","No"));
            }

            Console.WriteLine(String.Format("{0, 20} {1, -15}", "Rows:", Rows));
            Console.WriteLine(String.Format("{0, 20} {1, -15}", "Columns:", Columns));

            Console.WriteLine(String.Format("{0, 20} {1, -1} {2, 0}", "Random Factor:", RandFactor * 100.00,"%"));

            if (StepMode == false)
            {
                Console.WriteLine(String.Format("{0, 20} {1, -15}", "Step Mode:","No"));
            }
            else
            {
                Console.WriteLine(String.Format("{0, 20} {1, -15}", "Step Mode:","Yes"));
            }
        }
        
        /// <summary>
        /// Contains code for the rules of life, checking the neighbours and code checking for periodic behaviour
        /// </summary>
        /// <param name="Rows"></param>
        /// <param name="Columns"></param>
        /// <param name="GameArray"></param>
        /// <param name="ThreeCount"></param>
        /// <param name="PeriodicBehaviour"></param>
        /// <param name="TempArray"></param>
        static void ActualGame(ref int Rows, ref int Columns, ref int[,] GameArray, ref int ThreeCount,
            ref bool PeriodicBehaviour, ref int[,] TempArray)
        {
            for (int i = 0; i < Rows; i++)
            {
                for (int j = 0; j < Columns; j++)
                {
                    ThreeCount = 0;
                    //FOR CENTER
                    if (i > 0 && j > 0 && i < (Rows - 1) && j < (Columns - 1))
                    {
                        ThreeCount += (GameArray[i - 1, j]);

                        ThreeCount += (GameArray[i + 1, j]);

                        ThreeCount += (GameArray[i, j - 1]);

                        ThreeCount += (GameArray[i, j + 1]);

                        ThreeCount += (GameArray[i + 1, j + 1]);

                        ThreeCount += (GameArray[i + 1, j - 1]);

                        ThreeCount += (GameArray[i - 1, j + 1]);

                        ThreeCount += (GameArray[i - 1, j - 1]);
                    }

                    //FOR SIDE (Left Vertical)
                    if ((i > 0) && (i < Rows - 1) && j == 0)
                    {
                        ThreeCount += (GameArray[i - 1, j]);

                        ThreeCount += (GameArray[i + 1, j]);

                        ThreeCount += (GameArray[i, j + 1]);

                        ThreeCount += (GameArray[i + 1, j + 1]);

                        ThreeCount += (GameArray[i - 1, j + 1]);

                        if (PeriodicBehaviour == true)
                        {
                            ThreeCount += (GameArray[i, GameArray.GetLength(1) - 1]);

                            ThreeCount += (GameArray[i + 1, GameArray.GetLength(1) - 1]);

                            ThreeCount += (GameArray[i - 1, GameArray.GetLength(1) - 1]);
                        }
                    }

                    //FOR SIDE (Top Horizontal)
                    if ((j > 0) && (j < Columns - 1) && i == 0)
                    {
                        ThreeCount += (GameArray[i + 1, j]);

                        ThreeCount += (GameArray[i, j - 1]);

                        ThreeCount += (GameArray[i, j + 1]);

                        ThreeCount += (GameArray[i + 1, j + 1]);

                        ThreeCount += (GameArray[i + 1, j - 1]);

                        if (PeriodicBehaviour == true)
                        {
                            ThreeCount += (GameArray[GameArray.GetLength(0) - 1, j]);

                            ThreeCount += (GameArray[GameArray.GetLength(0) - 1, j - 1]);

                            ThreeCount += (GameArray[GameArray.GetLength(0) - 1, j + 1]);
                        }
                    }


                    //FOR SIDE (Right Vertical)
                    if ((i > 0) && (i < Rows - 1) && j == Columns - 1)
                    {
                        ThreeCount += (GameArray[i - 1, j]);

                        ThreeCount += (GameArray[i + 1, j]);

                        ThreeCount += (GameArray[i, j - 1]);

                        ThreeCount += (GameArray[i + 1, j - 1]);

                        ThreeCount += (GameArray[i - 1, j - 1]);

                        if (PeriodicBehaviour == true)
                        {
                            ThreeCount += (GameArray[i, 0]);

                            ThreeCount += (GameArray[i + 1, 0]);

                            ThreeCount += (GameArray[i - 1, 0]);
                        }
                    }

                    //FOR SIDE (Bottom Horizontal)
                    if ((j > 0) && (j < Columns - 1) && i == Rows - 1)
                    {
                        ThreeCount += (GameArray[i - 1, j]);

                        ThreeCount += (GameArray[i, j - 1]);

                        ThreeCount += (GameArray[i, j + 1]);

                        ThreeCount += (GameArray[i - 1, j + 1]);

                        ThreeCount += (GameArray[i - 1, j - 1]);

                        if (PeriodicBehaviour == true)
                        {
                            ThreeCount += (GameArray[0, j]);

                            ThreeCount += (GameArray[0, j + 1]);

                            ThreeCount += (GameArray[0, j - 1]);
                        }
                    }


                    //FOR EDGE (Top Left)
                    if (i == 0 && j == 0)
                    {
                        ThreeCount += (GameArray[i + 1, j]);

                        ThreeCount += (GameArray[i, j + 1]);

                        ThreeCount += (GameArray[i + 1, j + 1]);

                        if (PeriodicBehaviour == true)
                        {
                            ThreeCount += (GameArray[GameArray.GetLength(0) - 1, j]);

                            ThreeCount += (GameArray[i, GameArray.GetLength(1) - 1]);

                            ThreeCount += (GameArray[i + 1, GameArray.GetLength(1) - 1]);

                            ThreeCount += (GameArray[GameArray.GetLength(0) - 1, j + 1]);

                            ThreeCount += (GameArray[GameArray.GetLength(0) - 1, GameArray.GetLength(1) - 1]);
                        }

                    }

                    //FOR EDGE (Top Right)
                    if (i == 0 && j == Columns - 1)
                    {
                        ThreeCount += (GameArray[i + 1, j]);

                        ThreeCount += (GameArray[i, j - 1]);

                        ThreeCount += (GameArray[i + 1, j - 1]);

                        if (PeriodicBehaviour == true)
                        {
                            ThreeCount += (GameArray[GameArray.GetLength(0) - 1, j]);

                            ThreeCount += (GameArray[i, 0]);

                            ThreeCount += (GameArray[i + 1, 0]);

                            ThreeCount += (GameArray[GameArray.GetLength(0) - 1, 0]);

                            ThreeCount += (GameArray[GameArray.GetLength(0) - 1, j - 1]);
                        }
                    }

                    //FOR EDGE (Bottom Left)
                    if (i == Rows - 1 && j == 0)
                    {
                        ThreeCount += (GameArray[i - 1, j]);

                        ThreeCount += (GameArray[i, j + 1]);

                        ThreeCount += (GameArray[i - 1, j + 1]);

                        if (PeriodicBehaviour == true)
                        {
                            ThreeCount += (GameArray[0, j]);

                            ThreeCount += (GameArray[i, GameArray.GetLength(1) - 1]);

                            ThreeCount += (GameArray[0, j + 1]);

                            ThreeCount += (GameArray[0, GameArray.GetLength(1) - 1]);

                            ThreeCount += (GameArray[i - 1, GameArray.GetLength(1) - 1]);
                        }
                    }

                    //FOR EDGE (Bottom Right)
                    if (i == Rows - 1 && j == Columns - 1)
                    {
                        ThreeCount += (GameArray[i - 1, j]);

                        ThreeCount += (GameArray[i, j - 1]);

                        ThreeCount += (GameArray[i - 1, j - 1]);

                        if (PeriodicBehaviour == true)
                        {
                            ThreeCount += (GameArray[0, j]);

                            ThreeCount += (GameArray[i, 0]);

                            ThreeCount += (GameArray[0, 0]);

                            ThreeCount += (GameArray[0, j - 1]);

                            ThreeCount += (GameArray[i - 1, 0]);
                        }
                    }

                    //If cell was already alive
                    if (GameArray[i, j] == 1)
                    {
                        //Check if neighbours 2 or 3
                        if (ThreeCount == 2 || ThreeCount == 3)
                        {
                            TempArray[i, j] = 1;
                        }
                    }
                    else
                    {
                        if (ThreeCount == 3)
                        {
                            TempArray[i, j] = 1;
                        }
                    }

                }
            }
        }

        /// <summary>
        /// 
        /// </summary>
        /// <param name="XCoord"></param>
        /// <param name="YCoord"></param>
        /// <param name="GameArray"></param>
        /// <param name="Value"></param>
        static void CellStructure(int XCoord, int YCoord, int[,] GameArray, int Value)
        {
            GameArray[XCoord, YCoord] = Value;
        }

        /// <summary>
        /// 
        /// </summary>
        /// <param name="XCoord"></param>
        /// <param name="YCoord"></param>
        /// <param name="Width"></param>
        /// <param name="Height"></param>
        /// <param name="Value"></param>
        /// <param name="GameArray"></param>
        static void RectangleStructure(int XCoord, int YCoord, int Width, int Height, int Value, int[,] GameArray)
        {
            for(int X = XCoord; X <= Height; X++)
            {
                for (int Y = YCoord; Y<= Width; Y++)
                {
                    GameArray[X, Y] = Value;
                }
            }
        }

        /// <summary>
        /// 
        /// </summary>
        /// <param name="XCoord"></param>
        /// <param name="YCoord"></param>
        /// <param name="Width"></param>
        /// <param name="Height"></param>
        /// <param name="Value"></param>
        /// <param name="GameArray"></param>
        public static void EllipseStructure(int XCoord, int YCoord, int Width, int Height, int Value, int[,] GameArray)
        {
            double XMiddle = (double)(Height + XCoord) / 2;
            double YMiddle = (double)(Width + YCoord) / 2;

            for(int i = 0; i < GameArray.GetLength(0); i++)
            {
                for(int j = 0; j < GameArray.GetLength(1); j++)
                {
                    double SomethingForX = Math.Pow(i - XMiddle, 2);
                    double nancyX = 4 * SomethingForX;
                    double donkeyX = Math.Pow(Height - XCoord + 1, 2);

                    double SomethingForY = Math.Pow(j - YMiddle, 2);
                    double nancyY = 4 * SomethingForY;
                    double donkeyY = Math.Pow(Width - YCoord + 1, 2);

                    double FinalResult = ((nancyX / donkeyX) + (nancyY / donkeyY));

                    if(FinalResult <= 1)
                    {
                        GameArray[i, j] = Value;
                    }
                }
            }
        }




        /// <summary>
        /// Main Function which contains all code that wasn't put into methods
        /// </summary>
        /// <param name="args"></param>
        static void Main(string[] args)
        {
         
         // Declaring the variables
            int Rows = 16; // Default: 16. Change as required for testing. 
            int Columns = 16; // Default: 16. Change as required for testing.
            bool PeriodicBehaviour = false; // Default: false. Change as required for testing
            double RandFactor = 0.5; // Default: 0.5. Change as required for testing
            string InputFile = ""; // Default: NO input. Change as required for testing
            int Generations = 50; // Default: 50. Change as required fo testing
            double MaxUpdateRate = 5; // Default: 5. Change as required for testing
            bool StepMode = false; // Default: NOT step mode. Change as required for testing
            bool CheckAllConditions = true; //Checking all the parameters

            //To count the number of generations
            int GenCount = 0;

            Stopwatch watch = new Stopwatch();

         
         // Checking the user input
            for (int count = 0; count < args.Length; count++)
            {
                //Checking the dimensions of the game
                CheckDimensions(ref args, ref count, ref Rows, ref Columns, ref CheckAllConditions);

                //Checking if the game will have periodic behaviour
                CheckPeriodic(ref args, ref count, ref PeriodicBehaviour);

                //Checking Random factor
                CheckRandomFactor(ref args, ref count, ref RandFactor, ref CheckAllConditions);

                //Checking the input file
                CheckSeedfile(ref args, ref  count, ref  InputFile, ref  CheckAllConditions);

                //Checking the generations
                GenerationMethod(ref args, ref count, ref Generations, ref CheckAllConditions);

                //Checking the max update rate
                MaxUpdaterate(ref args, ref count, ref  MaxUpdateRate, ref  CheckAllConditions);

                //Checking step mode
                StepModeMethod(ref args, ref count, ref StepMode);


            } 

            //Game array which stores the cell coordinates
            int[,] GameArray = new int[Rows, Columns];

            //Temporary Array to store the neighbours
            int[,] TempArray = new int[Rows, Columns];

            // Construct grid...
            Grid grid = new Grid(Rows, Columns);


            //Checking randomness
            RandomnessMethod(ref InputFile, ref Columns, ref Rows, ref GameArray, ref RandFactor);

            //Displaying user uput
            DispUserInput(ref CheckAllConditions, ref InputFile, ref Generations, ref MaxUpdateRate, ref PeriodicBehaviour,
                                                                 ref Rows, ref Columns, ref StepMode, ref RandFactor);

            // Wait for user to press a key...
            Console.WriteLine("Press any key to start...");
            Console.ReadKey();

         
         // Game
            // Initialize the grid window (this will resize the window and buffer
            grid.InitializeWindow();

            // Set the footnote (appears in the bottom left of the screen).
            grid.SetFootnote("Life "+GenCount);

            // Declaring variable to see if neighbouring cells are active for next generation
            int ThreeCount = 0;

            // For each of the cells...
            for (int i = 0; i < GameArray.GetLength(0); i++)
            {
                for (int j = 0; j < GameArray.GetLength(1); j++)
                {
                    if (GameArray[i, j] == 1)
                    {
                        // Update grid with a new cell...
                        grid.UpdateCell(i, j, CellState.Full);
                    }
                    else
                    {
                        grid.UpdateCell(i, j, CellState.Blank);
                    }
                }
            }

            // Timer for Life game
            watch.Restart();
            while (watch.ElapsedMilliseconds < (1000/ MaxUpdateRate)) ;

            grid.Render();

            //Increasing the generations
            while (Generations >= GenCount)
            {

                //Checking the neighbours of the cells
                ActualGame(ref Rows, ref Columns, ref GameArray, ref ThreeCount, ref PeriodicBehaviour, ref TempArray);

                //Step function holding answer till space is pressed
                if (StepMode == true)
                {
                    while (Console.ReadKey().Key != ConsoleKey.Spacebar) ;
                }
                grid.SetFootnote("Life " + GenCount);

                // For each of the cells...
                for (int i = 0; i < GameArray.GetLength(0); i++)
                {
                    for (int j = 0; j < GameArray.GetLength(1); j++)
                    {
                        if (TempArray[i, j] == 1)
                        {
                            // Update grid with a new cell...
                            grid.UpdateCell(i, j, CellState.Full);
                            GameArray[i, j] = TempArray[i, j];
                        }
                        else
                        {
                            grid.UpdateCell(i, j, CellState.Blank);
                            GameArray[i, j] = 0;

                        }
                        TempArray[i, j] = 0;

                    }
                }

                // Timer for Life Game
                watch.Restart();
                while (watch.ElapsedMilliseconds < (1000 / MaxUpdateRate)) ;
                // Render updates to the console window...
                grid.Render();
                GenCount++;
            } 

            // Set complete marker as true
            grid.IsComplete = true;

            grid.Render();

            Console.ReadKey();

            grid.RevertWindow();
        }
    }
}
