
# GTK+ Coding Convention


# Bảng Quy Ước Đặt Tên Biến

Dưới đây là bảng thể hiện cách đặt tên biến theo các quy ước **camelCase** và **snake_case** cho mỗi loại biến trong GTK+.

| Loại Biến             | Quy Ước Đặt Tên | Ví Dụ                         |
|-----------------------|-----------------|-------------------------------|
| **Biến cục bộ**       | snake_case      | `int my_variable;`            |
| **Tham số hàm**       | snake_case      | `void process_data(int data_value);` |
| **Biến toàn cục**     | snake_case      | `int global_counter;`         |
| **Tên hàm**           | mixed case      | `void gtk_button_new();`      |
| **Kiểu dữ liệu**      | mixed case      | `typedef struct _GtkWidget GtkWidget;` |
| **Hằng số**           | UPPER_CASE      | `#define GTK_MAJOR_VERSION 3` |

# Bảng Quy Ước Định Dạng Mã Nguồn

Dưới đây là bảng thể hiện cách định dạng mã nguồn trong GTK+.

| Quy Ước                     | Cách Thực Hiện                                         |
|-----------------------------|--------------------------------------------------------|
| **Thụt lề**                 | 4 khoảng trắng cho mỗi mức thụt lề, không sử dụng tab  |
| **Dấu ngoặc nhọn mở**       | Đặt ở cùng dòng với lệnh điều kiện hoặc hàm            |
| **Dấu ngoặc nhọn đóng**     | Đặt ở dòng riêng biệt                                  |
| **Chú thích kiểu C++**      | Sử dụng `//` cho chú thích một dòng                   |
| **Chú thích kiểu C**        | Sử dụng `/* ... */` cho chú thích nhiều dòng           |

# Chi tiết
## 1. Phong cách đặt tên
### Biến cục bộ và tham số hàm
```c
int my_variable;
void process_data(int data_value) {
    int local_variable = data_value;
}

### Biến và hàm

- **Biến cục bộ và tham số hàm**: Sử dụng **snake_case**.

  ```c
  int my_variable;
  void process_data(int data_value);
  ```

- **Biến toàn cục**: Cũng sử dụng **snake_case** nhưng có thể có tiền tố để dễ nhận biết.

  ```c
  int global_counter;
  ```

- **Tên hàm**: Sử dụng **mixed case** với tiền tố tên không gian (namespace) của thư viện hoặc module.

  ```c
  void gtk_button_new();
  ```

### Kiểu dữ liệu

- **Kiểu dữ liệu**: Sử dụng **mixed case** với tiền tố tên không gian.

  ```c
  typedef struct _GtkWidget GtkWidget;
  ```

### Hằng số

- **Hằng số**: Sử dụng **UPPER_CASE** và thường có tiền tố tên không gian.

  ```c
  #define GTK_MAJOR_VERSION 3
  ```

## 2. Quy ước về định dạng mã nguồn

### Thụt lề

- Sử dụng **4 khoảng trắng** cho mỗi mức thụt lề. Không sử dụng tab.

  ```c
  void function() {
      if (condition) {
          // Code block
      }
  }
  ```

### Dấu ngoặc nhọn

- Dấu ngoặc nhọn mở `{` đặt ở cùng dòng với lệnh điều kiện hoặc hàm, và dấu ngoặc nhọn đóng `}` đặt ở dòng riêng biệt.

  ```c
  if (condition) {
      // Code block
  } else {
      // Code block
  }
  ```

## 3. Quy ước về chú thích

- Sử dụng chú thích kiểu C (`/* ... */`) và C++ (`// ...`) một cách hợp lý để giải thích các đoạn mã phức tạp.

  ```c
  // This is a single line comment

  /*
   * This is a multi-line comment
   * explaining the following block of code
   */
  void function() {
      // Code block
  }
  ```

## 4. Quy ước khác

### Tổ chức tệp tin

- **Tệp tiêu đề** (`.h`): Chứa các khai báo kiểu, hàm và macro.

  ```c
  #ifndef GTK_WIDGET_H
  #define GTK_WIDGET_H

  typedef struct _GtkWidget GtkWidget;

  void gtk_widget_show(GtkWidget *widget);

  #endif /* GTK_WIDGET_H */
  ```

- **Tệp nguồn** (`.c`): Chứa định nghĩa hàm và các logic thực thi.

  ```c
  #include "gtk_widget.h"

  void gtk_widget_show(GtkWidget *widget) {
      // Function implementation
  }
  ```

### Định nghĩa macro

- Sử dụng macro một cách tiết chế và đảm bảo rằng tên macro là dễ hiểu và có ý nghĩa.

  ```c
  #define MAX_BUFFER_SIZE 1024
  ```

### Kiểm tra lỗi

- Luôn kiểm tra lỗi khi gọi các hàm và xử lý lỗi một cách thích hợp.

  ```c
  GtkWidget *widget = gtk_button_new();
  if (!widget) {
      // Handle error
  }
  ```

```
