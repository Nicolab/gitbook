# Send files

Send a file, force-download to the client
```go
// You can define your own "Content-Type" header also, after this function call
// for example: ctx.Response.Header.Set("Content-Type","thecontent/type")
SendFile(filename string, destinationName string) error
```

```go
package main

import "github.com/kataras/iris"

func main() {

	iris.Get("/servezip", func(c *iris.Context) {
		file := "./files/first.zip"
		err := c.SendFile(file, "saveAsName.zip")
		if err != nil {
			println("error: " + err.Error())
		}
	})

	iris.Listen(":8080")
}


```