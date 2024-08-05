# Algorytmy

Algorytm - uporządkowany ciąg konkretnych kroków, które należy wykonać, aby rozwiązać dany problem lub osiągnąć określony cel.

## Algorytmy sortowania

Sposób układania rzeczy w określonym porządku.

### Insertion Sort (SORTOWANIE-PRZEZ-WSTAWIANIE) 
Najprostszym przykładem algorytmu sortowania jest Insertion Sort. Można go porównać do sposobu sortowania kart, które trzymacie w ręku. 

Pseudokod:
```
SORTOWANIE-PRZEZ-WSTAWIANIE(A) (INSERTION-SORT)
1  dla j = 2 do A.długość
2      klucz = A[j]
3      // Wstaw A[j] do posortowanego ciągu A[1..j-1].
4      i = j - 1
5      dopóki i > 0 i A[i] > klucz
6          A[i + 1] = A[i]
7          i = i - 1
8      A[i + 1] = klucz
```

1. Pętla "dla" przechodzi przez tablicę, zaczynając od drugiego elementu.
2. Zapamiętuje aktualny element jako "klucz".
3. Komentarz wyjaśniający cel następnych linii.
4. Ustawia indeks i na element poprzedzający aktualny.
5. Pętla "dopóki" przesuwa elementy większe od klucza w prawo.
6. Przesuwa element o jedną pozycję w prawo.
7. Przesuwa indeks i w lewo.
8. Wstawia klucz we właściwe miejsce.

Prxykład implementacji przy użyciu JavaScript:

```js
function insertionSort(arr) {
  const n = arr.length;
  
  for (let j = 1; j < n; j++) {
    let key = arr[j];
    let i = j - 1;
    
    while (i >= 0 && arr[i] > key) {
      arr[i + 1] = arr[i];
      i = i - 1;
    }
    
    arr[i + 1] = key;
  }
  
  return arr;
}

// Przykład użycia
let array = [5, 2, 4, 6, 1, 3];
insertionSort(array);
console.log("Po sortowaniu:", array);
```

TypeScript:

```ts
function insertionSort(arr: number[]): number[] {
  const n: number = arr.length;
  
  for (let j: number = 1; j < n; j++) {
    let key: number = arr[j];
    let i: number = j - 1;
    
    while (i >= 0 && arr[i] > key) {
      arr[i + 1] = arr[i];
      i = i - 1;
    }
    
    arr[i + 1] = key;
  }
  
  return arr;
}

// Przykład użycia
let array: number[] = [5, 2, 4, 6, 1, 3];
console.log("Przed sortowaniem:", array);
insertionSort(array);
console.log("Po sortowaniu:", array);

```
