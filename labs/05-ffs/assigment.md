## Preparation tasks (done before the lab at home)

1. Write characteristic equations and complete truth tables for D, JK, T flip-flops where `q(n)` represents main output value before the clock edge and `q(n+1)` represents output value after the clock edge.

![image](https://user-images.githubusercontent.com/99811894/158454787-a52ed962-4545-40a9-97ce-e9fd83b9aa24.png)

   **D-type FF**
   | **clk** | **d** | **q(n)** | **q(n+1)** | **Comments** |
   | :-: | :-: | :-: | :-: | :-- |
   | R | 0 | 0 | 0 | `q(n+1)` has the same level as `d` and `q(n)`|
   | R | 0 | 1 | 0 | `q(n+1)` has the same level as `d` and invert `q(n)`|
   | R | 1 | 0 | 1 | `q(n+1)` has the same level as `d` and invert `q(n)`|
   | R | 1 | 1 | 1 | `q(n+1)` has the same level as `d` and `q(n)` |

   **JK-type FF**
   | **clk** | **j** | **k** | **q(n)** | **q(n+1)** | **Comments** |
   | :-: | :-: | :-: | :-: | :-: | :-- |
   | R | 0 | 0 | 0 | 0 | Output did not change |
   | R | 0 | 0 | 1 | 1 | Output did not change |
   | R | 0 | 1 | 0 | 0 | reset |
   | R | 0 | 1 | 1 | 0 | reset |
   | R | 1 | 0 | 0 | 1 | set |
   | R | 1 | 0 | 1 | 1 | set |
   | R | 1 | 1 | 0 | 1 | toggle |
   | R | 1 | 1 | 1 | 0 | toggle |

   **T-type FF**
   | **clk** | **t** | **q(n)** | **q(n+1)** | **Comments** |
   | :-: | :-: | :-: | :-: | :-- |
   | R | 0 | 0 | 0 | Output did not change |
   | R | 0 | 1 | 1| not change |
   | R | 1 | 0| 1| invert (toggle) |
   | R | 1 | 1| 0| invert (toggle) |

<a name="part1"></a>
