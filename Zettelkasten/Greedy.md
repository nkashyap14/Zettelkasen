# Greedy

## Summary

- A greedy algorithm makes locally optimal choices at each step, hoping these choices lead to a globally optimal solution. It picks the best immediate option without looking ahead or backtracking.

## Key Characteristics

- Makes the locally optimal choice at each step
- Never reconsiders previous choices
- Usually simpler and more efficient than dynamic programming or backtracking
- Does not guarantee global optimum for all problems
## When to Use Greedy

Greedy algorithms work when a problem has these properties:

1. **Optimal Substructure**: Optimal solution contains optimal solutions to its subproblems
2. **Greedy Choice Property**: Locally optimal choices lead to globally optimal solution

## Common Problem Indicators

- Finding minimum/maximum values
- Optimization problems involving sequences or selections
- Problems involving scheduling or intervals
- Tasks involving resource allocation
- Questions asking for "minimum steps" or "maximum profit" where local choices don't affect future choices

## Classic Examples

1. **Interval Scheduling**: Choose non-overlapping intervals to maximize count
    - Sort by end time, always pick earliest ending interval
2. **Fractional Knapsack**: Fill knapsack with items for maximum value
    - Sort by value/weight ratio, take highest ratio items first
3. **Coin Change (with specific coin sets)**: Make change with minimum coins
    - Always pick largest possible coin
    - Note: Only works with specific coin systems (like US currency)

## Code Template

```
def greedy_solution(input):
    # Often starts with sorting
    input.sort()  # Or custom sort key
    
    result = initialize_result()
    
    for element in input:
        # Make locally optimal choice
        if is_valid_choice(element):
            add_to_solution(result, element)
    
    return result
```


## How to Recognize

1. Can you make a locally optimal choice without reconsidering it?
2. Does the problem ask for optimization (min/max)?
3. Can you sort the input to help make decisions?
4. Is there a clear "best choice" at each step?

## Common Mistakes to Avoid

1. Applying greedy to problems requiring global view
2. Not proving greedy choice property
3. Assuming greedy works just because it's simpler
4. Missing edge cases where local optimum ≠ global optimum

Type :: #topic #algorithm
Links :: [[Computer Science]] [[Algorithm]] [[Algorithmic Technique]]
Creator ::
Date ::  2025-01-05 20:07