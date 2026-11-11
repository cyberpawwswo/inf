# 1. Алгоритм сортировки
## 1.1 Пузырьковый


|0|1|2|3|4|
|-|-|-|-|-|
|5|1|2|0|9|
|1|2|3|5|4|
|1|2|3|5|4|

```Java
System.out.print("Привет, ");
System.out.print("мир!"); // Вывод: Привет, мир!
```


```mermaid
flowchart TD
    Start([Начало]) --> Input[/Ввод массива A длиной n/]
    Input --> OuterInit[i = 0]
    
    OuterInit --> OuterCond{i < n - 1?}
    OuterCond -- Нет --> Output[/Вывод отсортированного массива A/]
    Output --> End([Конец])
    
    OuterCond -- Да --> SwappedInit[swapped = false<br/>j = 0]
    SwappedInit --> InnerCond{j < n - i - 1?}
    
    InnerCond -- Да --> Compare{"A[j] > A[j + 1]?"}
    Compare -- Да --> Swap["Поменять местами<br/>A[j] и A[j + 1]<br/>swapped = true"]
    Compare -- Нет --> InnerInc[j = j + 1]
    Swap --> InnerInc
    
    InnerInc --> InnerCond
    
    InnerCond -- Нет --> CheckSwapped{swapped == false?}
    CheckSwapped -- Да --> Output
    CheckSwapped -- Нет --> OuterInc[i = i + 1]
    OuterInc --> OuterCond
```
