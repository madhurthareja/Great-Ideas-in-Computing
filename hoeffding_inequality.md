To combine the three code snippets into one cohesive script and then generate one-liner prompts for each part, you can follow these steps:

### Combined Code

```python
import random
import matplotlib.pyplot as plt
import time

def create_list(p_zero, n):
    L = []
    for _ in range(n):
        if random.random() < p_zero:
            L.append(0)  # Probability p_zero of appending 0
        else:
            L.append(1)  # Probability 1 - p_zero of appending 1
    return L

def cumulative_proportion_ones(L):
    cumulative_proportion = []
    cumulative_sum = 0
    for i in range(len(L)):
        cumulative_sum += L[i]
        cumulative_proportion.append(cumulative_sum / (i + 1))
    return cumulative_proportion

# Parameters
p_zero = 0.21  # Probability of 0
n = 1000000    # Length of the list for full plot
n_small = 5000 # Length of the list for error calculation
window_size = 10  # Number of errors to include in each average calculation

# Create the list
L = create_list(p_zero, n)

# Calculate the cumulative proportion of 1's
cumulative_ones = cumulative_proportion_ones(L)

# Plot the cumulative proportion of 1's over time
plt.figure(figsize=(12, 6))
plt.subplot(1, 2, 1)
plt.plot(cumulative_ones, label=f'Proportion of 1s (p_zero = {p_zero})')
plt.axhline(y=1 - p_zero, color='r', linestyle='--', label='Expected Proportion of 1s')
plt.xlabel('Number of Elements')
plt.ylabel('Cumulative Proportion of 1s')
plt.title('Cumulative Proportion of 1s Over Time')
plt.legend()

# Smaller list for error calculation
L_small = create_list(p_zero, n_small)

# Calculate the cumulative proportion of 1's
cumulative_ones_small = cumulative_proportion_ones(L_small)

# Expected proportion of 1's
expected_proportion = 1 - p_zero

# Calculate the error between the cumulative proportion and the expected proportion
error = [abs(cumulative_ones_small[i] - expected_proportion) for i in range(n_small)]

# Plot the error over time
plt.subplot(1, 2, 2)
plt.plot(error, label='Error between Cumulative Proportion and Expected Proportion', color='orange')
plt.xlabel('Number of Elements')
plt.ylabel('Error')
plt.title('Error Between Cumulative Proportion of 1s and Expected Value')
plt.legend()
plt.show()

# Display the average error for overlapping sets of errors
for start in range(0, len(error) - window_size + 1, 1):
    end = start + window_size
    current_window = error[start:end]
    average_error = sum(current_window) / len(current_window)
    print(f"Average error from {start + 1} to {end}: {average_error:.4f}")

# Display the first 10 errors with a time lag of 5 seconds
for i in range(min(10, len(error))):
    print(f"Iteration {i + 1}: Error = {error[i]}")
    time.sleep(5)
```

Here are function-wise one-liner prompts for Gemini to generate the code in Google Colab:

1. **`create_list(p_zero, n)`**: "Generate a Python function in Colab to create a list of length `n` where each element is either 0 or 1, with a given probability `p_zero` for zeros."

2. **`cumulative_proportion_ones(L)`**: "Create a Python function in Colab that takes a list of 0s and 1s and returns the cumulative proportion of 1s at each position."

3. **Plotting Cumulative Proportion**: "Write Python code in Colab to plot the cumulative proportion of 1s from a list generated with a specific zero probability using Matplotlib."

4. **Error Calculation**: "Generate Python code in Colab to calculate and plot the error between the cumulative proportion of 1s and the expected value over time."

5. **Sliding Window Average Error Calculation**: "Create Python code in Colab that computes and prints the average error of cumulative proportions in a sliding window from a list of binary values."

6. **Error Display with Delay**: "Write Python code in Colab to print the first few errors from a list of calculated errors with a delay between each print."

These prompts will help break down the code into individual functions and tasks.
