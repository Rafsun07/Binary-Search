# Binary-Search

This project demonstrates the performance comparison between two search algorithms: Naive Search and Binary Search. It evaluates the time complexity and efficiency of these algorithms using a large sorted list of random integers.

## Features

- Implements Naive Search algorithm.
- Implements Binary Search algorithm.
- Generates a large sorted list of random integers.
- Compares the performance of Naive Search and Binary Search.

## Installation

1. **Clone the repository:**

    ```
    git clone https://github.com/Rafsun07/Binary-Search.git
    cd binary-search
    ```

2. **Run the game:**

    ```
    python binary-search.py
    ```

## Usage

1. **Start the game:**

    Run the `binary-search.py` script to start the Mad Libs game.

    ```
    python binary-search.py
    ```

2. **Output:**

    This script generates a large sorted list of random integers and measures the time taken to find each element in the list using both Naive Search and Binary Search.


## How the Code Works

1. **Importing Libraries:**

    ```
    import random
    import time

    ```
    
    The script uses the `random` library to generate random integers and the `time` library to measure the execution time of the search algorithms.
   
2. **Naive Search Function:**

    ```
    def naive_search(l, target):
        for i in range(len(l)):
            if l[i] == target:
                return i
        return -1

    ```
    
    This function performs a linear search on the list `l`. It iterates through each element in the list and returns the index of the target element if found. If the target element is not found, it returns -1.
    
3. **Binary Search Function:**

    ```
    def binary_search(l, target, low=None, high=None):
        if low is None:
            low = 0
        if high is None:
            high = len(l) - 1

        if high < low:
            return -1

        midpoint = (low + high) // 2

        if l[midpoint] == target:
            return midpoint
        elif target < l[midpoint]:
            return binary_search(l, target, low, midpoint-1)
        else:
            return binary_search(l, target, midpoint+1, high)
    ```

    This function performs a binary search on the sorted list `l`. It uses recursion to repeatedly divide the search interval in half until the target element is found or the interval is empty. The function returns the index of the target element if found, otherwise it returns -1.

4. **Main Execution Block:**

    ```
    if __name__=='__main__':
        length = 10000
        sorted_list = set()
        while len(sorted_list) < length:
            sorted_list.add(random.randint(-3*length, 3*length))
        sorted_list = sorted(list(sorted_list))
    ```

    This function performs a binary search on the sorted list `l`. It uses recursion to repeatedly divide the search interval in half until the target element is found or the interval is empty. The function returns the index of the target element if found, otherwise it returns -1.

5. **Timing Naive Search:**

    ```
    start = time.time()
    for target in sorted_list:
        naive_search(sorted_list, target)
    end = time.time()
    print("Naive search time: ", (end - start), "seconds")
    ```

    The script measures the total time taken to search for each element in `sorted_list` using the Naive Search algorithm and prints the result.

5. **Timing Binary Search:**

    ```
    start = time.time()
    for target in sorted_list:
        binary_search(sorted_list, target)
    end = time.time()
    print("Binary search time: ", (end - start), "seconds")

    ```

    Similarly, the script measures the total time taken to search for each element in `sorted_list` using the Binary Search algorithm and prints the result.

## Key Points

- Naive Search: A simple linear search algorithm with a time complexity of O(n), where n is the number of elements in the list. It checks each element sequentially until it finds the target.
- Binary Search: A more efficient search algorithm with a time complexity of O(log n), which repeatedly divides the search interval in half. This algorithm requires the list to be sorted.
- Performance Measurement: The script measures and compares the execution time of both search algorithms to highlight the difference in performance, especially for large datasets.
  
This code effectively demonstrates how Binary Search significantly outperforms Naive Search in terms of execution time, especially as the size of the dataset increases.

      
## FAQ

Q: What is the difference between Naive Search and Binary Search?

A: Naive Search checks each element in the list sequentially until it finds the target or reaches the end of the list, resulting in O(n) time complexity. Binary Search, on the other hand, repeatedly divides the search interval in half, resulting in O(log n) time complexity, but it requires the list to be sorted.

## Contributing

Contributions are welcome! Please fork the repository and create a pull request with your changes. Ensure that your code follows the project's coding standards and includes appropriate tests.

## Contact

For questions, suggestions, or issues, please open an issue on GitHub or contact the project maintainer at [rafsun.eram@gmail.com](mailto:rafsun.eram@gmail.com).

## Acknowledgements

- Developed using Python.
- Proof that Binary search is more efficient than Naive search

---
