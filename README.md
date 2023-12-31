the video:
https://www.youtube.com/watch?v=35pbs0gytwg&t=22s

the sources I used 
https://www.programiz.com/cpp-programming/online-compiler/
https://stackoverflow.com/
chat GPT
Note: include.docx has the code 
the code :
#include <iostream>
#include <cstdlib>
void mergesort(int num, float a[], float b[]) {
    for (int k = 1; k < num; k *= 2) {
        for (int left = 0; left + k < num; left += k * 2) {
            int rght = left + k;    
            int last = rght + k;     
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
    float a[num] = {7,1,6,5,8,3,2,4};
    float b[num];
    std::cout << "Unsorted array:" << std::endl;
    for (int i = 0; i < num; ++i) {
        std::cout << a[i] << " ";
     }
     std::cout << std::endl;
    mergesort(num, a, b);
    std::cout << "Sorted array:" << std::endl;
    for (int i = 0; i < num; ++i) {
        std::cout << a[i] << " ";
    }
    std::cout << std::endl;

    return 0;
}



