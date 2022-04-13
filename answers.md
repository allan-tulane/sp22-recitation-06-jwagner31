# CMPS 2200 Reciation 6
## Answers

**Name:** Joe Wagner and Luke Albright


Place all written answers from `recitation-06.md` here for easier grading.


- Note: Input sizes larger than 999 would generate errors everytime which I assume is due to memory, so I could only run tests up to n=900.
- **1b.**

|n (sorted) |   qsort-fixed-pivot |   qsort-random-pivot |
|-----|---------------------|----------------------|
|  50 |               0.750 |                0.402 |
| 100 |               3.110 |                0.595 |
| 200 |               9.920 |                1.204 |
| 300 |              60.082 |                2.064 |
| 400 |              84.377 |                3.373 |
| 500 |             109.910 |                3.803 |
| 600 |             189.422 |                8.115 |
| 700 |             215.192 |                5.977 |
| 800 |             308.304 |               49.916 |
| 900 |             340.258 |               55.435 |

|n (shuffled) |   qsort-fixed-pivot |   qsort-random-pivot |
|-----|---------------------|----------------------|
|  50 |               0.111 |                0.143 |
| 100 |               0.197 |                0.267 |
| 200 |               0.503 |                0.684 |
| 300 |               0.787 |                0.874 |
| 400 |               1.045 |                1.249 |
| 500 |               1.347 |                1.621 |
| 600 |               1.573 |                1.956 |
| 700 |               2.169 |                2.367 |
| 800 |               2.048 |                2.552 |
| 900 |              49.484 |                5.917 |

- How do the running times compare to the asymptotic bounds? The running times when the list is sorted do not reflect the asymptotic bounds as well as when the list is shuffled. This is because we choose the first element for the fixed pivot, and thus an ordered list will be our worst-case runtime every time. This is why the runtime of fixed pivot are far higher before the lists are shuffled. Both functions resembled the asymptotic bound, as the random pivot consistently did the best and had expected increases over input sizes. Fixed pivot was similar, except the runtime grew faster than the random pivot. Additional machine time not accounted for also should be considered.

- How does changing the type of input list change the relative performance of these algorithms? Changing the type of input list vastly affects the performance of these algorithms. Fixed pivot is much, much faster when the list is not ordered, as is expected with choosing the first element. We want to balance the recursion tree as much as possible so that we can have a lower worst-case runtime, and this depends on the input list. Random performs similarly regardless of the list ordering, and can actually be made faster in some cases by taking the median of multiple random numbers, although you must worry abvout this additional cost before choosing too many additional random numbers.

- **1c.**

|n (sorted) |   time-sort |   qsort-random-pivot |
|-----|-------------|----------------------|
|  50 |       0.001 |                0.126 |
| 100 |       0.001 |                0.365 |
| 200 |       0.003 |                0.549 |
| 300 |       0.004 |                0.958 |
| 400 |       0.005 |               12.929 |
| 500 |       0.014 |                3.685 |
| 600 |       0.013 |                4.663 |
| 700 |       0.013 |                5.263 |
| 800 |       0.014 |               34.820 |
| 900 |       0.021 |                8.211 |

|n (shuffled) |   time-sort |   qsort-random-pivot |
|-----|-------------|----------------------|
|  50 |       0.008 |                0.331 |
| 100 |       0.026 |                0.610 |
| 200 |       0.035 |                1.419 |
| 300 |       0.052 |                1.812 |
| 400 |       0.074 |               21.264 |
| 500 |       0.126 |                6.180 |
| 600 |       0.287 |               12.160 |
| 700 |       0.159 |               10.479 |
| 800 |       0.398 |                7.989 |
| 900 |       0.201 |               13.470 |

- The timsort algorithm does much better than quicksort, especially as the input sizes grow. Random pivot varies due to the pivot choice varying in effectiveness between runs. 