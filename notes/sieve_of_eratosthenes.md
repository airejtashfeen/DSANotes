# Sieve of Eratosthenes

The **Sieve of Eratosthenes** is an efficient algorithm to find all prime numbers up to a specified integer. It works by iteratively marking the multiples of each prime number starting from 2. Here's a step-by-step explanation of the algorithm:

## Algorithm Steps

1. **Initialization**:
   - Create a boolean array `prime[0..n]` and initialize all entries as `true`. Each index represents whether that number is prime. For simplicity, `prime[i]` will be `true` if `i` is a prime number, and `false` otherwise.

2. **Mark Non-Primes**:
   - Starting from the first prime number (2), mark all of its multiples as `false` in the array.
   - Move to the next number that is still marked as `true` and mark all its multiples as `false`.
   - Continue this process up to the square root of `n`. This is because any composite number `n` must have at least one factor less than or equal to `sqrt(n)`.

3. **Print Primes**:
   - After processing, the indices of the array that remain `true` correspond to prime numbers.

## Complexity

- **Time Complexity**: \(O(n \log \log n)\), where `n` is the upper limit. This is because each number is marked as non-prime at most once, and each marking operation is proportional to the number of multiples of the prime.
- **Space Complexity**: \(O(n)\) for the boolean array.

## Example

To find all primes less than or equal to 30:

1. **Initialize**:
   - `prime = [true, true, true, true, ..., true]` for indices 0 to 30.

2. **Marking Non-Primes**:
   - Start with `p = 2`. Mark all multiples of 2 (4, 6, 8, ...) as `false`.
   - Move to `p = 3`. Mark all multiples of 3 (9, 12, 15, ...) as `false`.
   - Continue with `p = 5`. Mark all multiples of 5 (25, 30, ...) as `false`.
   - No need to mark multiples of 7 as it is greater than `sqrt(30)`.

3. **Output Primes**:
   - The indices still marked as `true` are 2, 3, 5, 7, 11, 13, 17, 19, 23, and 29.

## Code Example

- [SIEVE OF ERATOSTHENES ](https://github.com/airejtashfeen/DSA/blob/main/sieve_of_eratosthenes.cpp)