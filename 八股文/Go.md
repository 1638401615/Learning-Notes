* string类型不可修改，是只读的二进制 byte slice，如果真要修改字符串中的字符，将 string 转为 []byte 修改后，再转为 string 即可。

  ```go
  // 修改字符串的错误示例
  func main() {
   x := "text"
   x[0] = "T"  // error: cannot assign to x[0]
   fmt.Println(x)
  }
  
  
  // 修改示例
  func main() {
   x := "text"
   xBytes := []byte(x)
   xBytes[0] = 'T' // 注意此时的 T 是 rune 类型
   x = string(xBytes)
   fmt.Println(x) // Text
  }
  ```

* switch 语句中的 case 代码块会默认带上 break，但可以使用 `fallthrough` 来强制执行下一个 case 代码块。

* 在 encode/decode JSON 数据时，Go 默认会将数值当做 float64 处理。

简短声明的变量

- 简短声明的变量只能在函数内部使用
- struct 的变量字段不能使用 := 来赋值
- 不能用简短声明方式来单独为一个变量重复声明， := 左侧至少有一个新变量，才允许多变量的重复声明



* recover 必须在 defer 函数中运行。recover 捕获的是**祖父级调用时的异常**，直接调用时无效。

  ```go
  func main() {
      defer func() {
          recover()
      }()
      panic(1)
  }
  ```

  直接defer调用也无效

  ```go
  func main() {
      defer recover()
      panic(1)
  }
  ```

  