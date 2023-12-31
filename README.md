the video:
https://www.youtube.com/watch?v=35pbs0gytwg&t=22s

the sources I used 
https://www.programiz.com/cpp-programming/online-compiler/
https://stackoverflow.com/
chat GPT

#include <iostream>
#include <cstdlib>

// Function to perform merge sort on array a[]
void mergesort(int num, float a[], float b[]) {
    for (int k = 1; k < num; k *= 2) {
        for (int left = 0; left + k < num; left += k * 2) {
            int rght = left + k;     //1
            int last = rght + k;     //1
            int m = left, i = left, j = rght;

            while (i < rght && j < last) {
                if (a[i] <= a[j]) {
                    b[m] = a[i];
                    i++;
                } else {
                    b[m] = a[j];
                    j++;
                }
                m++;
            }

            while (i < rght) {
                b[m] = a[i];
                i++;
                m++;
            }

            while (j < last) {
                b[m] = a[j];
                j++;
                m++;
            }

            for (m = left; m < last; m++) {
                a[m] = b[m];
            }
        }
    }
}
int main() {
    const long num = 8;
    // Initialize arrays with random values for demonstration purposes
    float a[num] = {7,1,6,5,8,3,2,4};
    float b[num];
    // Print the unsorted array (optional)
    std::cout << "Unsorted array:" << std::endl;
    for (int i = 0; i < num; ++i) {
        std::cout << a[i] << " ";
     }
     std::cout << std::endl;

    // Perform merge sort
    mergesort(num, a, b);

    // Print the sorted array
    std::cout << "Sorted array:" << std::endl;
    for (int i = 0; i < num; ++i) {
        std::cout << a[i] << " ";
    }
    std::cout << std::endl;

    return 0;
}

