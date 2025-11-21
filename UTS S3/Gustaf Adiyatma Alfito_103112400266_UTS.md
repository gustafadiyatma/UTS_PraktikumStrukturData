[UTS-Struktur data]

Identitas Pengumpul

Nama: [Gustaf Adiyatma Alfito]

NIM: [103112400266]

Kelas: [IF - 12 - 05]

1. Kode Program

Berikut adalah kode program untuk : Menambah, Menghapus, membalik data di list

(Silakan ganti bahasa dan kode di bawah ini sesuai tugas Anda)

File: Soal2.cpp
 * Author: [Gustaf Adiyatma Alfito]
 * NIM: [103112400266]
 * Deskripsi: program untuk Menambah, Menghapus, membalik data di list


```cpp
#include <iostream>

using namespace std;
 // buat doble linked list
struct Node {
    int data;
    Node* prev;
    Node*next;
};

Node* heag = NULL // node awal
Node* tail = NULL // node akhir

void insertEnd(int val) {
    Node* baru = new Node;   // bikin node baru
    baru->data = val;        // ngisi data
    baru->next = NULL;       
    baru->prev = tail;      

    if (head == NULL) {      // kalo list masih kosong
        head = tail = baru;  // node baru jadi head & tail
    } else {
        tail->next = baru;   // tail lama menunjuk ke node baru
        tail = baru;         
    }
}
void deleteLast() {
    if (head == NULL) return;       // kalo kosong, tidak ada yang dihapus

    if (head == tail) {             
        delete head;
        head = tail = NULL; 
    } else {
        Node* del = tail;           
        tail = tail->prev;          
        tail->next = NULL;         
        delete del;                 
    }
}

void viewForward() {
    Node* p = head;

    while (p != NULL) {            //  gerak dari head ke tail
        cout << p->data << " ";
        p = p->next;               // maju ke node selanjutnya
    }
    cout << endl;
}

void reverselist(){
    Node* curr = head;
    Node* temp = NULL;

while  (curr != NULL) {
    temp = curr->prev;
    curr->prev = curr->next;
    curr->next = temp;
    curr = curr->prev;
}
 if (temp != NULL) {
        head = temp->prev;
        
    }
}

int main() {
int pilih, nilai;

do {
    cout <<  "Menu: 1 insert (end), 2 delete (last), 3 view (depan), 4 reverse & view (depan), 0 exit" << endl;
    cin >> pilih;

    switch (pilih) {

    case : 1
        cout << "Masukan nilai: ";
        cin >> nilai;
        insertEnd(nilai);
        break;

    case : 2
    deleteLast();
    break;

    case : 3
    viewVorward();
    break;
    
    case : 4
    reverseList();
    cout << "List setelah direvers: ";
    viewVorward();
    break;

    case : 0
    break;

    default:
    cout << "Pilihan Tidak valid: " << endl;
    }
} while (pilih != 0);

   return 0;
}

```

2. Penjelasan Kode

Berikut adalah penjelasan alur logika dari kode program di atas:

Program buat Doubly Linked List yang bisa ditambah data di akhir, menghapus data terakhir, menampilkan isi list dari depan, serta membalik urutan list tanpa membuat node baru. Pengguna memilih operasi melalui menu, lalu program menjalankan fungsi yang sesuai dan kembali menampilkan menu sampai pengguna memilih keluar.


3. Output Program


Berikut adalah hasil eksekusi program (output) ketika dijalankan.
**-output-**

4. Penjelasan Lanjutan (Analisis Output)

Output menghasilkan hasil dari setiap operasi yang dipilih pengguna  Saat memasukkan nilai  list bertambah dan ketika memilih view  program menampilkan isi list dari depan ke belakang. Jika memilih delete last  elemen terakhir hilang dari tampilan  Saat memilih reverse  vdaniew  urutan list dibalik lalu ditampilkan hasilnya  Menu terus muncul kembali sampai pengguna memilih keluar.

5. Kesimpulan

Berdasarkan implementasi dan pengujian kode di atas, dapat disimpulkan bahwa:

Program ini Adalah implementasi Doubly Linked List yang memungkinkan pengguna menambah data  menghapus data terakhir  melihat isi list  serta membalik urutannya tanpa membuat node baru. Setiap operasi dilakukan melalui menu interaktif  dan hasilnya langsung terlihat di output sesuai pilihan user  Secara keseluruhan, program ini menunjukkan bagaimana struktur data linked list bekerja dalam mengelola data secara dinamis menggunakan pointer, serta bagaimana setiap operasi memengaruhi bentuk dan urutan list
