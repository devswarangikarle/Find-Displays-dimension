# Find-Displays-dimension
You are tasked with designing a new series of rectangular displays for a large company. The key requirement is that each display must contain exactly n pixels. Your objective is to determine the dimensions of these displays - specifically, the number of pixel rows (a) and the number of pixel columns (b)

def find_display_dimensions(n):
    best_diff = float('inf')
    best_a, best_b = 1, n

    for a in range(1, int(n**0.5) + 1):
        if n % a == 0:
            b = n // a
            if a <= b:
                if b - a < best_diff:
                    best_diff = b - a
                    best_a, best_b = a, b

    return best_a, best_b

n = int(input())
result = find_display_dimensions(n)
print(*result)
