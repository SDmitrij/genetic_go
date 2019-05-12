# Implementation of genetic algorithm in golang
***
* This implementation use ***Goga package*** that provides some API to work with genetic algorithm, it building simple shapes and contours of original photo using primitive geometry figures.

***Goga*** is a genetic algorithm solution written in Golang. It is used and configured by injecting different behaviours into the main genetic algorithm object. The main injectable components are the simulator, selector and mater.

The simulator provides a function that accepts a single genome and assigns a fitness score to it. The higher the fitness, the better the genome has done in the simulation. A genome can be simulated by however the application sees fit as long as it can be encoded into a bitset of 0s and 1s. A simulator also provides a function to tell the algorithm when to stop.

The selector object takes a popualtion of genomes and the total fitness and returns a genome from the population that it has chosen. A common implementation is roulette in which a random value between 0..totalFitness is generated and the genomes are cycled through subtracting their fitness away from this random number. Then this number goes below 0 then a genome has been 'selected'. The idea is that a genome with a higher fitness will be more likely to be chosen.

A mater accepts two genomes from the selector and combines them to produce two others. There are some common predefined mating algorithms but the user is also free to define their own.

As genomes that have a fitness are more likely to mate, the program will slowly work its way towards what it thinks is an optimal solution.
***
### Examples of image-building: 
![vintage](https://github.com/SDmitrij/genetic_go/blob/master/2019-05-12_20-43-12.png)
![vintage_orig](https://github.com/SDmitrij/genetic_go/blob/master/2019-05-12_20-43-36.png)
***
![sea](https://github.com/SDmitrij/genetic_go/blob/master/2019-05-12_20-58-03.png)
![sea_orig](https://github.com/SDmitrij/genetic_go/blob/master/2019-05-12_20-57-51.png)
***
![sepia](https://github.com/SDmitrij/genetic_go/blob/master/2019-05-12_20-58-47.png)
![sepia_orig](https://github.com/SDmitrij/genetic_go/blob/master/2019-05-12_20-58-38.png)
