# 🧬 Genetic Algorithm Engine

**Genetic Algorithm Engine** is a general-purpose evolutionary computation framework built in Scala. It provides a modular foundation for solving optimization problems using biologically inspired mechanics such as mutation, crossover, and natural selection.

Tested on polynomial and linear regression, this engine can be extended to a wide variety of problem domains—from data fitting to symbolic reasoning.

> “Not all those who wander are lost. Some are evolving.”  
> — _On watching a fitness score rise_

---

## 📦 Features

- **Generic Genetic Algorithm Framework** – Reusable and adaptable to multiple problem domains.
- **Fitness-Driven Evolution** – Population members are scored, selected, and mutated over generations.
- **Polynomial & Linear Regression** – Demonstrated success fitting noisy data.
- **Modular Design** – Plug in new fitness functions, gene decoders, and chromosome layouts.
- **Extensible & Elegant** – Clean Scala implementation ready for expansion.

---

## 🧠 How It Works

1. **Initialization**  
   A population of individuals (chromosomes composed of `Gene` objects) is randomly generated.

2. **Evaluation**  
   Each individual is decoded into a potential solution and scored by a fitness function.

3. **Selection & Mutation**  
   Top individuals are cloned and mutated to populate the next generation.

4. **Iteration**  
   This process continues for 90,000 generations by default, evolving better solutions over time.

---

## 🧪 Example: Linear Regression

The following code uses the genetic algorithm to evolve a line that best fits a given set of 2D points:

```scala
val input: List[Point] = List(Point(1,1), Point(2,2))
val answer = linearRegression(input)
println(answer.slope + " " + answer.yIntercept)
```

---

## ⚙️ Core API

### `geneticAlgorithm`

```scala
geneticAlgorithm[T](
  fitnessFunction: T => Double,
  chromosomeDecoder: List[Gene] => T,
  sampleChromosome: List[Gene]
): T
```

- Evolves a solution of type `T` using genetic techniques
- Accepts user-defined fitness and decoding logic

---

## 🧬 Example Components

### Fitness Function

```scala
def linearReg1stParam(scatterPlot: Array[Point]): Line => Double
```

Computes fitness based on vertical distance from points to a candidate line.

---

### Gene Decoder

```scala
def linearReg2ndParam(): List[Gene] => Line
```

Converts genes into a `Line` object using scaled tangent functions for range diversity.

---

### Chromosome Template

```scala
def linearReg3rdParam(): List[Gene]
```

Provides an example chromosome layout for the regression use case.

---

## 📂 Project Structure

```
genetics/
├── genes/             # Gene and chromosome utilities
├── geometry/          # Points and Lines in 2D space
└── GeneticAlgorithm.scala  # Main engine and regression logic
```

---

## 🚀 Getting Started

Make sure you have Scala installed (2.13 or newer):

```bash
scalac GeneticAlgorithm.scala
scala genetics.GeneticAlgorithm
```

---

## 🔮 Future Enhancements

- Multi-objective optimization
- Custom crossover strategies
- Visual evolution inspector
- Symbolic expression generation

---

## 📄 License

MIT License. Use freely, fork boldly, and evolve responsibly.

