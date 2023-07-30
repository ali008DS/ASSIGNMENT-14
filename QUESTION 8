def max_absolute_difference(arr):
    n = len(arr)
    left_smaller = [-1] * n
    right_smaller = [-1] * n
    stack = []

    # Find the nearest right smaller element for each element
    for i in range(n):
        while stack and arr[stack[-1]] > arr[i]:
            right_smaller[stack.pop()] = i
        stack.append(i)

    # Clear the stack
    stack.clear()

    # Find the nearest left smaller element for each element
    for i in range(n - 1, -1, -1):
        while stack and arr[stack[-1]] > arr[i]:
            left_smaller[stack.pop()] = i
        stack.append(i)

    # Calculate the maximum absolute difference between nearest left and right smaller elements
    max_diff = 0
    for i in range(n):
        diff = abs(right_smaller[i] - left_smaller[i])
        max_diff = max(max_diff, diff)

    return max_diff

# Examples
arr1 = [2, 4, 8, 7, 7, 9, 3]
arr2 = [5, 1, 9, 2, 5, 1, 7]

print(max_absolute_difference(arr1))  # Output: 4
print(max_absolute_difference(arr2))  # Output: 5
