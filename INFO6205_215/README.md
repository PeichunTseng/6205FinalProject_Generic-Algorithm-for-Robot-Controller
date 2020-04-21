# INFO6205_215

INFO6205 Final Project: Robotic Controllers

Problems: The problem is to design the robot controller to walk through the maze and arrive the destination in the end without crashing into the wall. The robot can be controlled by six different direction sensors, three on the front, one on the left, one on the right and one on the back. Each route can be one solution and can be scored, our purpose is to find the fittest solution by comparing the scores until it reaches the termination we set. We choose the highest fitness solution in each generation and change it by crossover and mutate for the next generation. The final solution will be found until the number of generations reach the maximum we set.

Genotype: In individual class (Phenotype), we have one chromosome and its type is int[] with binary value 0 and 1. We call 0 and 1 value as gene.

Fitness: The fitness of each solution is calculated by the route. We initially set the route we want and calculate the route provided by chromosomes. In each route, we calculate whether this route passes through the route we set, and it will be scored.

Initialization: The maze object we’ve created uses integers to represent different terrain types: 1 defines a wall; 2 is the starting position, 3 traces the best route through the maze, 4 is the goal position and 0 is an empty position that the robot can travel over but isn’t on the route to the goal. The calcRoute method in the is the most significant method in the Maze class; it evaluates a route taken by the robot and returns a fitness score based on the number of correct tiles it stepped on. The score returned by this calcRoute method is what we’ll use as the individual’s fitness score in the GeneticAlgorithm class’ calcFitness method. When robot enter position 3 or position 4, it can score one point (fitness).

Expression: We define one chromosome as one solution. Each solution indicates a series of possible actions by binary code, such as 10011110...11. The definition of actions shows below. 00: do nothing, 01: move forward, 10: turn right, 11: turn left

Phenotype: We dedicate Individual class as Phenotype, which contains one genotype.

Code GeneticAlgorithm class: The main GA implements. Individual class: Details about individuals, including chromosome and fitness. It means one route solution in this problem. Population class: Details about populations, including individuals array. Maze class: Define the maze that contains the route and score the fitness. Robot class: Details about all sensors and make the decision of the actions.

Execution In this project, we use eclipse as our IDE and we put codes into different package separately, including helper, main, controller, objects and test. The main function is in the Main.java in main package, Controller.java is in controller package, all the test cases are in the test package and all the class we create, including abstract class, are in objects package. To execute, just run the Main.java and it will use the Controller.java (in controller package) to run our whole GA program. It will print the fittest value and fittest chromosome for each generation. In the end, it will print the route of final fittest solution.
