Quiz #1

Въпросите покриват материалите от WEEK_01.md и WEEK_02.md. Отговорите са скрити — опитайте се първо сами.

---

## Въпрос 1

```cpp
std::pair<int, std::string> p = {10, "C++"};
```

Кой ред ще изведе `C++`?

A) `cout << p.first;`
B) `cout << p.second;`
C) `cout << p;`
D) `cout << p.at();`

<details>
  <summary>Отговор</summary>

  **B) `cout << p.second;`** — `second` е достъп до втория елемент в двойката.

</details>

---

## Въпрос 2

Кое от следните НЕ е валидно създаване на `std::vector`?

A) `std::vector<int> v;`
B) `std::vector<int> v(5);`
C) `std::vector<int> v = {1, 2, 3};`
D) `std::vector<int> v(5, 10, 15);`

<details>
  <summary>Отговор</summary>

  **D)** — конструкторът приема или `(брой_елементи)` или `(брой_елементи, стойност)`, не три аргумента.

</details>

---

## Въпрос 3

```cpp
std::vector<int> v = {1, 2, 3, 4, 5};
v.pop_back();
v.pop_back();
std::println("{}", v.size());
```

Какъв е output-ът?

A) `5`
B) `3`
C) `4`
D) `2`

<details>
  <summary>Отговор</summary>

  **B) `3`** — `pop_back` маха последния елемент, два пъти → остават 3 елемента.

</details>

---

## Въпрос 4

```cpp
std::string s = "Hello World";
std::string part = s.substr(6);
```

Каква е стойността на `part`?

A) `Hello`
B) `World`
C) ` World`
D) `o World`

<details>
  <summary>Отговор</summary>

  **B) `World`** — `substr(6)` взима всичко от позиция 6 до края.

</details>

---

## Въпрос 5

```cpp
std::vector<int> v = {10, 20, 30};
for (int& x : v) {
    x = 0;
}
```

Какво е съдържанието на `v` след цикъла?

A) `{10, 20, 30}`
B) `{0, 0, 0}`
C) `{0, 20, 30}`
D) Компилаторна грешка

<details>
  <summary>Отговор</summary>

  **B) `{0, 0, 0}`** — `int& x` е референция към оригиналните елементи и позволява промени.

</details>

---

## Въпрос 6

```cpp
std::vector<int> v = {2, 0, 6};
std::sort(v.begin(), v.end());
std::reverse(v.begin(), v.end());
```

Какво се извежда?

A) `0 2 6`
B) `6 2 0`
C) `2 0 6`
D) `6 0 2`

<details>
  <summary>Отговор</summary>

  **B) `6 2 0`** — първо сортиране `{0, 2, 6}`, после реверсиране `{6, 2, 0}`.

</details>

---

## Въпрос 7

```cpp
void f(int N) {
    for(int i = 0; i < N; i++) {
        for(int j = 0; j < i; j++) {
            cout << i << j;
        }
    }
}
```

Каква е временната сложност на `f`?

A) $O(N)$
B) $O(N \log N)$
C) $O(N^2)$
D) $O(\log N)$

<details>
  <summary>Отговор</summary>

  **C) $O(N^2)$** — външният цикъл е N пъти, вътрешният средно N/2 → общо $\approx N^2/2$ → $O(N^2)$.

</details>

---

## Въпрос 8

```cpp
void f(int N) {
    for(int i = 1; i <= N; i *= 2) {
        cout << i;
    }
}
```

Каква е временната сложност на `f`?

A) $O(N)$
B) $O(\log N)$
C) $O(N^2)$
D) $O(1)$

<details>
  <summary>Отговор</summary>

  **B) $O(\log N)$** — `i` се удвоява на всяка стъпка, броят итерации е $\log_2 N$.

</details>

---

## Въпрос 9

```cpp
long long f(int N) {
    if (N <= 1) 
        return 1;
    return f(N - 1) + f(N - 1);
}
```

Каква е временната сложност на `f`?

A) $O(N)$
B) $O(N^2)$
C) $O(2^N)$
D) $O(\log N)$

<details>
  <summary>Отговор</summary>

  **C) $O(2^N)$** — всеки повик прави два рекурсивни повика → броят възли е $2^N$.

</details>

---

## Въпрос 10

```cpp
void f(int N) {
    for(int i = 0; i < N; i++) {
        g();
    }
}

void g() {
    for(int i = 0; i < 5; i++) {
        cout << i;
    }
}
```

Каква е временната сложност на `f`?

A) $O(1)$
B) $O(N)$
C) $O(N^2)$
D) $O(5^N)$

<details>
  <summary>Отговор</summary>

  **B) $O(N)$** — `g()` винаги изпълнява 5 операции (константа), повикан е N пъти → $5 \cdot N = O(N)$.

</details>

---

## Въпрос 11

```cpp
void f(int N) {
    for(int i = 0; i < N; i++) {
        for(int j = 1; j <= N; j *= 2) {
            cout << "sda";
        }
    }
}
```

Каква е временната сложност на `f`?

A) $O(N)$
B) $O(N^2)$
C) $O(N \log N)$
D) $O(\log N)$

<details>
  <summary>Отговор</summary>

  **C) $O(N \log N)$** — външният цикъл: N пъти, вътрешният: $\log N$ пъти → $N \cdot \log N$.

</details>

---

## Въпрос 12

Коя от следните функции на `std::vector` добавя елемент в края?

A) `push_back`
B) `pop_back`
C) `emplace`
D) `insert`

<details>
  <summary>Отговор</summary>

  **A) `push_back`** — добавя елемент в края на вектора.

</details>

---

## Въпрос 13

```cpp
std::vector<int> v;
std::println("{}", v.empty());
```

Какъв е output-ът?

A) `false`
B) `true`
C) `0`
D) Грешка — векторът е празен

<details>
  <summary>Отговор</summary>

  **B) `true`** — `empty()` връща `true`, когато векторът няма елементи.

</details>

---

## Въпрос 14

Коя е НАЙ-ДОБРАТА (best case) сложност на bubble sort с оптимизацията `swapped`?

A) $O(1)$
B) $O(N)$
C) $O(N \log N)$
D) $O(N^2)$

<details>
  <summary>Отговор</summary>

  **B) $O(N)$** — ако масивът вече е сортиран, един пас без размяна прекратява изпълнението → $N-1$ сравнения.

</details>

---

## Въпрос 15

Коя е best case сложност на selection sort?

A) $O(1)$
B) $O(N)$
C) $O(N \log N)$
D) $O(N^2)$

<details>
  <summary>Отговор</summary>

  **D) $O(N^2)$** — selection sort винаги прави $N(N-1)/2$ сравнения, независимо от подредбата на елементите.

</details>

---

## Въпрос 16

Коя от следните сортировки е **стабилна**?

A) Selection sort
B) Quick sort
C) Insertion sort
D) Heap sort

<details>
  <summary>Отговор</summary>

  **C) Insertion sort** — стабилна е, защото елементи с еднаква стойност запазват относителния си ред. Selection sort и quick sort не са стабилни.

</details>

---

## Въпрос 17

Каква е средната (average case) сложност на merge sort?

A) $O(N)$
B) $O(N \log N)$
C) $O(N^2)$
D) $O(\log N)$

<details>
  <summary>Отговор</summary>

  **B) $O(N \log N)$** — масивът се разделя на $\log N$ нива, на всяко ниво се прави $O(N)$ работа по сливането.

</details>

---

## Въпрос 18

Каква е пространствената (memory) сложност на merge sort?

A) $O(1)$
B) $O(\log N)$
C) $O(N)$
D) $O(N^2)$

<details>
  <summary>Отговор</summary>

  **C) $O(N)$** — сливането изисква допълнителен временен масив с размер N.

</details>

---

## Въпрос 19

Коя е worst case сложност на quick sort (Lomuto partition, пивот = последен елемент)?

A) $O(N \log N)$
B) $O(N^2)$
C) $O(N)$
D) $O(\log N)$

<details>
  <summary>Отговор</summary>

  **B) $O(N^2)$** — ако пивотът винаги е най-малкият или най-големият елемент (напр. вече сортиран масив), partition-ът разделя много неравномерно.

</details>

---

## Въпрос 20

Каква е средната сложност на quick sort?

A) $O(N)$
B) $O(N \log N)$
C) $O(N^2)$
D) $O(\log N)$

<details>
  <summary>Отговор</summary>

  **B) $O(N \log N)$** — при случайно разпределение partition-ът разделя масива приблизително на половина.

</details>

---

## Въпрос 21

Коя от следните сортировки е подходяща за сортиране на големи цели числа с малък диапазон (напр. числа от 0 до 100)?

A) Bubble sort
B) Merge sort
C) Counting sort
D) Quick sort

<details>
  <summary>Отговор</summary>

  **C) Counting sort** — ако диапазонът $K$ е малък, counting sort работи за $O(N + K)$, което е линейно.

</details>

---

## Въпрос 22

Каква е сложността на counting sort (нека $K$ е максималната стойност)?

A) $O(N)$
B) $O(N + K)$
C) $O(N \cdot K)$
D) $O(K)$

<details>
  <summary>Отговор</summary>

  **B) $O(N + K)$** — обхождаме масива веднъж ($O(N)$) и масива с броячи ($O(K)$).

</details>

---

## Въпрос 23

Каква е сложността на radix sort (нека $d$ е броят цифри, $k = 10$ за десетична бройна система)?

A) $O(N \log N)$
B) $O(N^2)$
C) $O(d \cdot (N + k))$
D) $O(N)$

<details>
  <summary>Отговор</summary>

  **C) $O(d \cdot (N + k))$** — правим $d$ паса, всеки е counting sort върху цифрата.

</details>

---

## Въпрос 24

Коя сортировка е **нестабилна**?

A) Merge sort
B) Bubble sort
C) Insertion sort
D) Selection sort

<details>
  <summary>Отговор</summary>

  **D) Selection sort** — размяната на минимума с първия елемент може да размести елементи с еднаква стойност. (Quick sort също е нестабилен.)

</details>

---

## Въпрос 25

Коя от следните твърдения е **вярно**?

A) Merge sort винаги е по-бърз от quick sort
B) Counting sort работи за всяко множество от числа
C) std::sort използва комбинация от алгоритми (интросортиране) и е стабилен
D) Bubble sort с оптимизация има best case $O(N)$

<details>
  <summary>Отговор</summary>

  **D)** — bubble sort с `swapped` оптимизация прекратява при вече сортиран масив → $O(N)$. A) е невярно (quick sort обикновено е по-бърз), B) е невярно (изисква малък диапазон $K$), C) е невярно (std::sort е нестабилен).

</details>
